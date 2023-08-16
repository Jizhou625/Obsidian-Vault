### 1. 为什么初始化很重要
1. 不正确的初始化权重会导致梯度消失或梯度爆炸问题, 从而对训练过程产生负面影响
2. 从统计的角度而言, 初始化具有某种regularization的作用, 初始化值越接近0, 正则化效果越明显; 但从优化的角度而言, 全0或全等初始化会导致unidentified的对称性问题

### 2. Xavier初始化
[Understanding the difﬁculty of training deep feedforward neural networks](zotero://select/library/items/SQXG25FN)

**模型设定**: 
1. 所有的weights都是独立初始化的, 且均值为$0$, 偏置bias初始化为0. 
2. 输入的features的方差是相等的, 都为$\mathrm{Var}(x)$, 且进行了中心化. 
3. Activation function $f$具有对称性, 且在$0$附近近似恒等变换, 即$f^{\prime}(0)=1$.  此外进一步假设网络在初始化时处于线性条件<details> <summary><font color=  #9400D3>解释</summary> 网络权重的初始化是独立同方差的, 且均值为0. 并且输入的各个features方差相等. 因此对于初始化的权重, 线性层的输出应该非常接近于0. 而我们假设了activation function在0附近近似恒等变换</font> </details>
4. 设第$i$层的size为$n_i$, 设$\boldsymbol{x}$是神经网络的输入, 第$i$层到第$i+1$层通过线性层和激活层的表达式为
  $$
  \boldsymbol{s}_{i} = W_i\boldsymbol{z}_i+\boldsymbol{b}_i,\quad \boldsymbol{z}_{i+1} = f(\boldsymbol{s}_i) 
  $$
  这里$\boldsymbol{s}_i$是线性层的输出, $\boldsymbol{z}_{i+1}$是激活层的输出, 同时是下一线性层的输入

**方差推导**: 
对于中心化的独立随机变量$X_1,\cdots, X_n$, 他们乘积的方差可以写成
$$
\begin{align}
\mathrm{Var}(X_1X_2\cdots X_n) &= \mathbb{E}(X_1^2\cdots X_n^2) -\mathbb{E}^2(X_1X_2\cdots X_n)  \\
&= \mathrm{Var}(X_1\cdots X_{n-1})\cdot \mathrm{Var}(X_n)  \\
& = \mathrm{Var}(X_1) \mathrm{Var}(X_2) \cdots \mathrm{Var}(X_n)
\end{align}
$$
则我们可以计算出(这里, $\mathrm{Var}(\boldsymbol{z}_i)$和$\mathrm{Var}(W_j)$都是标量. 可以这样简写是因为我们假设了所有元素是同方差的)
$$
\mathrm{Var}(\boldsymbol{z}_i)=\mathrm{Var}(\boldsymbol{x})\prod\limits_{j=0}^{i-1}n_j \mathrm{Var}(W_j) 
$$
对于一个有$d$层隐藏层的神经网络, 根据[全连接神经网络的梯度计算](../机器学习/Book%202.%20深度学习/Lecture%203.%20CNN#5.1.%20全连接神经网络的梯度计算)中的结果, 我们可以得到
$$
\mathrm{Var}\left(\dfrac{\partial \mathrm{Cost} }{\partial W_i^{\top} } \right) = \mathrm{Var}(\boldsymbol{z}_i)\mathrm{Var}\left(\dfrac{\partial \mathrm{Cost} }{\partial \boldsymbol{s}^{\top}_i } \right) =  \mathrm{Var}(\boldsymbol{z}_i)\mathrm{Var}\left(\dfrac{\partial \mathrm{Cost} }{\partial \boldsymbol{s}_d^{\top} } \right)\prod\limits_{j=i}^{d-1}n_{j+2} \mathrm{Var}(W_{j+1}) 
$$

**保持方差**:
从forward propagation的角度, 我们希望每个线性层输入的方差保持不变
$$
\forall i\neq j, \quad \mathrm{Var}(\boldsymbol{z}_i) = \mathrm{Var}(\boldsymbol{z}_j)
$$
从back propagation的角度, 我们希望对每一层权重$W$的梯度的方差保持不变, 即
$$
\forall i\neq j, \quad \mathrm{Var}\left(\dfrac{\partial \mathrm{Cost} }{\partial W^{\top}_i } \right) = \mathrm{Var}\left(\dfrac{\partial \mathrm{Cost} }{\partial W^{\top}_j } \right)
$$
又因为已经假设了$\forall i\neq j, \mathrm{Var}(\boldsymbol{z}_i) = \mathrm{Var}(\boldsymbol{z}_j)$, 因此只需要
$$
\forall i\neq j, \quad \mathrm{Var}\left(\dfrac{\partial \mathrm{Cost} }{\partial \boldsymbol{s}^{\top}_i } \right) = \mathrm{Var}\left(\dfrac{\partial \mathrm{Cost} }{\partial \boldsymbol{s}^{\top}_j } \right)
$$
合并起来有
$$
\forall i,\quad n_i\mathrm{Var}(W_i)=1,\quad n_{i+1}\mathrm{Var}(W_i)=1
$$
两相权衡
$$
\forall i,\quad \mathrm{Var}(W_i)=\frac{2}{n_i+n_{i+1}}
$$
如果初始化分布取均匀分布, 我们有
$$
W_j \sim \mathcal{U}\left[- \frac{\sqrt{ 6 }}{\sqrt{ n_j+n_{j+1} }}, \frac{\sqrt{ 6 }}{\sqrt{ n_j+n_{j+1} }}\right]
$$


### 3. He Kaiming初始化(pytorch Conv默认初始化方法)
[Delving Deep into Rectifiers: Surpassing Human-Level Performance on ImageNet Classification](zotero://select/library/items/UWZN4K8C)

**模型描述**: 
对于CNN网络, 设$\boldsymbol{x}$是神经网络的输入, 第$i$层到第$i+1$层卷积层和激活层的表达式为
$$
  \boldsymbol{s}_i = W_i\boldsymbol{z}_{i}+ b_i,\quad \boldsymbol{z}^{\prime}_{i+1} = f(\boldsymbol{s}_i) 
$$
  这里$\boldsymbol{z}_{i}$是$k_i^2c_i\times1$的向量 用$n_i=k_i^2c_i$表示卷积层的连接数, $W_i$是一个$d_i\times n_i$的矩阵, $d_i$表示第$i$层滤波器的数量. 显然我们有$c_l = d_{l-1}$. 这里$\boldsymbol{z}^{\prime}_{i+1}$仅仅只是第$i+1$层一个像素上$d_{i+1}$个通道的值. 和前述表达式中提到的$\boldsymbol{z}_{i}$并不完全等价. 我们用${}^{\prime}$符号表示区分.  

**Forward Propagation**: ReLU不能保证卷积层输入的均值为0, 因此我们有
$$
\mathrm{Var}(\boldsymbol{s}_i) = n_i\mathrm{Var}(W_i)\mathbb{E}\boldsymbol{z}_i^2
$$
而ReLU会使得$\mathbb{E}\boldsymbol{z}_i^2 =\dfrac{1}{2}\mathrm{Var}(\boldsymbol{s}_{i-1})$, 这就意味着
$$
\mathrm{Var}(\boldsymbol{s}_i) = n_i\mathrm{Var}(W_i)\mathbb{E}\boldsymbol{z}_i^2 = \frac{1}{2}n_i\mathrm{Var}(W_i)\mathrm{Var}(\boldsymbol{s}_{i-1})
$$
$$
\mathrm{Var}(\boldsymbol{s}_d)=\mathrm{Var}(\boldsymbol{s}_1)\prod\limits_{j=2}^{d} \left(\frac{1}{2 }n_j \mathrm{Var}(W_j)\right) 
$$
$$
\mathrm{Var}(W_j) = \frac{2}{n_j} 
$$
**Backward Propagation**: 显式计算卷积的梯度比较复杂不便于分析, 
$$
\mathrm{Var}(W_j)=\frac{2}{n_{j+1}}
$$
是否像Xavier Initialization一样进行权衡是无关紧要的, 因为衰减的幅度不过是$\dfrac{c_2}{c_{d+1}}$,这在现代网络中是可以忽略的. 
对于PReLU, 激活函数为 $f(x)=\begin{cases}x, \quad & x>0 \\ ax, & x\le 0\end{cases}$
$$
\mathrm{Var}(W_j)=\frac{2}{n_{j+1}(1+a^2)}
$$
$$
\mathrm{Var}(W_j)=\frac{2}{n_{j}(1+a^2)}
$$

### 4. 正交初始化(RNN)
[RNN 中学习长期依赖的三种机制 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/34490114)

考虑RNN的梯度的计算[RNN梯度的计算](../机器学习/Book%202.%20深度学习/Lecture%204.%20RNN#1.3.%20RNN梯度的计算)
$$
\prod\limits_{j=k+1}^t \dfrac{\partial \boldsymbol{h}^{(j)}}{\partial \boldsymbol{h}^{(j-1)\top} } = \prod\limits_{j=k+1}^t\mathrm{diag}\left\{g^{\prime}\left(\boldsymbol{b} + W\boldsymbol{h}^{(j-1)} + U \boldsymbol{x}^{(j)} \right) \right\} W
$$
当$W$为正交矩阵时, 其特征值都是$1$, 因此不容易发生梯度爆炸或梯度消失. 

可以给$W$增加一个始终为正交矩阵的约束. 在更新时先梯度下降得到矩阵$W^{*(n)}$, 再把$W^{*(n)}$投影到正交矩阵空间中得到$W^{(n+1)}$. 

​				
​					
​				
​				
​						
​				
​			




​				
