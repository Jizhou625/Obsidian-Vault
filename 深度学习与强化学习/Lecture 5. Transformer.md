## 1. 注意力机制

### 1.1. Intuition
从本质上理解，Attention是从大量信息中有筛选出少量重要信息，并聚焦到这些重要信息上，忽略大多不重要的信息。

![img](./Lecture%205.%20Transformer.assets/v2-a9bf4f074f460a501ecbe4e5c68a7aff_r.jpg)

至于Attention机制的具体计算过程，如果对目前大多数方法进行抽象的话，可以将其归纳为两个过程：第一个过程是根据Query和Key计算权重系数，第二个过程根据权重系数对Value进行加权求和

![image-20230408110359763](./Lecture%205.%20Transformer.assets/image-20230408110359763.png)

### 1.2. 注意力评分函数

假设有一个查询函数$\boldsymbol{q}\in \mathbb{R}^q$和$m$个键值对$(\boldsymbol{k}_1, \boldsymbol{v}_1), \cdots, (\boldsymbol{k}_m, \boldsymbol{v}_m)$, 其中$\boldsymbol{k}_i\in \mathbb{R}^k, \boldsymbol{v}_i\in \mathbb{R}^v$. 注意力汇聚函数可以写成核估计的形式
$$
f\left(\boldsymbol{q},\left(\boldsymbol{k}_1, \boldsymbol{v}_1\right), \ldots,\left(\boldsymbol{k}_m, \boldsymbol{v}_m\right)\right)=\sum_{i=1}^m \alpha\left(\boldsymbol{q}, \boldsymbol{k}_i\right) \boldsymbol{v}_i \in \mathbb{R}^v
$$
常用的注意力评分函数有
**加性注意力**: 
$$
a(\boldsymbol{q}, \boldsymbol{k})=\boldsymbol{w}_v^{\top} \tanh \left(W_q \boldsymbol{q}+W_k \boldsymbol{k}\right) \in \mathbb{R}
$$
$$
\alpha(\boldsymbol{q}, \boldsymbol{k})=\mathrm{softmax}(a(\boldsymbol{q}, \boldsymbol{k}))
$$
**缩放点积注意力**: 
使用点积可以得到计算效率更高的评分函数, 但是点积操作要求查询和键具有相同的长度 $d$ 。假设查询和键的所有元素都是独立的随机变量, 并且都满足零均值和单位方差, 那么两个向量的点积的均值为 0 , 方差为 $d$, 则缩放点积注意力 (scaled dot-product attention）评分函数为:
$$
a(\boldsymbol{q}, \boldsymbol{k})=\dfrac{\boldsymbol{q}^{\top} \boldsymbol{k} }{\sqrt{d}} 
$$
在实践中, 我们从小批量的角度来考虑提高效率, 例如, 基于$n$个查询和$m$个键值对计算注意力, 其中查询和键的长度为$d$, 值的长度为$v$, 查询$Q\in \mathbb{R}^{n\times d}$, 键$K\in \mathbb{R}^{m\times d}$和值$V\in \mathbb{R}^{m\times v}$的缩放点积注意力评分函数为:
$$
\operatorname{softmax}\left(\frac{QK^{\top}}{\sqrt{d}}\right) V \in \mathbb{R}^{n \times v} .
$$

### 1.3. 多头注意力机制
给定查询$\boldsymbol{q}\in \mathbb{R}^{d_q}$, 键$\boldsymbol{k}\in \mathbb{R}^{d_k}$和值$\boldsymbol{v}\in \mathbb{R}^{d_v}$. 每个注意力头$\boldsymbol{h}_i(i=1,\cdots, h)$的计算方法
$$
\boldsymbol{h}_i=\boldsymbol{f}\left(W_i^{(q)}\boldsymbol{q}, W_i^{(k)}\boldsymbol{k}, W_i^{(v)}\boldsymbol{v}\right) \in \mathbb{R}^{p_v}
$$
其中, 可学习的参数包括$W_i^{(q)}\in \mathbb{R}^{p_q\times d_q}$, $W_i^{(k)}\in \mathbb{R}^{p_k\times d_k}$, $W_i^{(v)}\in \mathbb{R}^{p_v\times d_v}$. 以及代表注意力的函数$\boldsymbol{f}$. 多头注意力的输出需要经过另一个转换, 它对应着$h$个头连接后的结果, 因此可学习参数是$W_o\in \mathbb{R}^{p_o\times hp_v}$
$$
W_o\left[\begin{array}{c}
\boldsymbol{h}_1 \\
\vdots \\
\boldsymbol{h}_h
\end{array}\right] \in \mathbb{R}^{p_o}
$$
**自注意力机制**: 在self-attention中, 查询, 键值$\boldsymbol{q}, \boldsymbol{k}, \boldsymbol{v}$都来源于$\boldsymbol{x}$, 每个注意力头$\boldsymbol{h}_i(i=1,\cdots, h)$的计算方法
$$
\boldsymbol{h}_i=\boldsymbol{f}\left(W_i^{(q)}\boldsymbol{x}, W_i^{(k)}\boldsymbol{x}, W_i^{(v)}\boldsymbol{x}\right) \in \mathbb{R}^{p_v}
$$



## 2. Transformer
### 2.1. Transformer的架构

![image-20230405112246287](./Lecture%205.%20Transformer.assets/image-20230405112246287.png)

### 2.2. 编码器
1. **Input**: Positional Encoding 和 word embedding 相加
2. **Sublayer 1**: Multi-head self-attention + residual connection + layer normalization
3. **Sublayer 2**: position-wise feed-forward network + residual connection + layer normalization

由于需要使用残差连接, 因此 输入序列对应的每个位置, Transformer编码器都将输出一个 $d$ 维表示向量。

### 2.3. 解码器
1. **Masked multi-head self attention**:  防止看到未来信息 + residual connection + layer normalization
2. **Encoder-decoder attention**: **Query** from Masked multi-head self attention layer, **Key-Value** from encoder(用到encoder的所有信息) + residual connection + layer normalization
3. **position-wise feed-forward network**: 2 layer MLP with activation function ReLU. 
4. **Fully connected layer**

