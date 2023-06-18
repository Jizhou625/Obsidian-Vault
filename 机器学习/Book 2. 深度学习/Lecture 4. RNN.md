## 1. 循环神经网络的构建

### 1.1. 展开计算图

很多循环神经网络使用下式或类似的公式定义隐藏单元的值。为了表明状态是网络的隐藏单元, 我们使用变量 $\boldsymbol{h}$ 代表状态

$$
\boldsymbol{h}^{(t)}=f\left(\boldsymbol{h}^{(t-1)}, \boldsymbol{x}^{(t)} ; \boldsymbol{\theta}\right)
$$

![image-20230401112350952](Lecture%204.%20RNN.assets/image-20230401112350952.png)

我们可以用一个函数 $g^{(t)}$ 代表经 $t$ 步展开后的循环:
$$
\begin{aligned}
\boldsymbol{h}^{(t)} & =g^{(t)}\left(\boldsymbol{x}^{(t)}, \boldsymbol{x}^{(t-1)}, \boldsymbol{x}^{(t-2)}, \ldots, \boldsymbol{x}^{(2)}, \boldsymbol{x}^{(1)}\right) \\
& =f\left(\boldsymbol{h}^{(t-1)}, \boldsymbol{x}^{(t)} ; \boldsymbol{\theta}\right) .
\end{aligned}
$$
函数 $g^{(t)}$ 将全部的过去序列 $\left(\boldsymbol{x}^{(t)}, \boldsymbol{x}^{(t-1)}, \boldsymbol{x}^{(t-2)}, \ldots, \boldsymbol{x}^{(2)}, \boldsymbol{x}^{(1)}\right)$ 作为输人来生成当前状 态, 但是展开的循环架构允许我们将 $g^{(t)}$ 分解为函数 $f$ 的重复应用。因此, 展开过程引入两个主要优点:
1. **模型输入大小不变**: 无论序列的长度，学成的模型始终具有相同的输入大小，因为它指定的是从一 种状态到另一种状态的转移，而不是在可变长度的历史状态上操作。
2. **参数共享和泛化**: 我们可以在每个时间步使用相同参数的相同转移函数$f$(参数共享)

学习单一的共享模型允许泛化到没有见过的序列长度(没有出现在训练集中), 并且估计模型所需的训练样本远远少于不带参数共享的模型。

###1.2.  循环神经网络的设计模式

1. 每个时间步都有输出, 并且隐藏单元之间有循环连接的循环神经网络

   ![image-20230401113259698](Lecture%204.%20RNN.assets/image-20230401113259698.png)

   **更新方程**:

   $$
   \begin{aligned}
   \boldsymbol{o}^{(t)} &= g(V \boldsymbol{h}^{(t)} + \boldsymbol{b}) \\ 
   \boldsymbol{h}^{(t)} &= f(W \boldsymbol{h}^{(t-1)} + U \boldsymbol{x}^{(t)} + \boldsymbol{c})
   \end{aligned}
   $$

   **图灵完备性**: 可以证明, 任何图灵可计算的函数都可以通过这样的一个有限维的循环网络计算, 在这个意义上上面这种形式的循环神经网络是万能的.

   **学习过程**: 与 $\boldsymbol{x}$ 序列配对的 $\boldsymbol{y}$ 的总损失就是所有时间步的损失之和。例如, $L^{(t)}$ 为 给定的 $\boldsymbol{x}^{(1)}, \cdots, \boldsymbol{x}^{(t)}$ 后 $\boldsymbol{y}^{(t)}$ 的负对数似然, 则
   $$
   \begin{aligned}
   & \mathscr{L}\left(\left\{\boldsymbol{x}^{(1)}, \ldots, \boldsymbol{x}^{(\tau)}\right\},\left\{\boldsymbol{y}^{(1)}, \ldots, \boldsymbol{y}^{(\tau)}\right\}\right)=\sum_t \mathscr{L}^{(t)} =-\sum_t \log p_{\text {model }}\left(y^{(t)} \mid\left\{\boldsymbol{x}^{(1)}, \ldots, \boldsymbol{x}^{(t)}\right\}\right),
   \end{aligned}
   $$
   其中 $p_{\text {model }}\left(y^{(t)} \mid\left\{\boldsymbol{x}^{(1)}, \ldots, \boldsymbol{x}^{(t)}\right\}\right)$ 需要读取模型输出向量 $\hat{\boldsymbol{y}}^{(t)}$ 中对应于 $y^{(t)}$ 的项。 这意味着梯度计算的成本是$O(\tau)$的且无法通过并行化来降低. 

2. 每个时间步都产生一个输出, 只有当前时刻的输出到下个时刻的隐藏单元之间有循环连接的循环网络

   ![image-20230401113417853](Lecture%204.%20RNN.assets/image-20230401113417853.png)

   **更新方程**:

   $$
   \begin{aligned}
   \boldsymbol{o}^{(t)} &= g(V \boldsymbol{h}^{(t)} + \boldsymbol{b}) \\ 
   \boldsymbol{h}^{(t)} &= f(W \boldsymbol{o}^{(t-1)} + U \boldsymbol{x}^{(t)} + \boldsymbol{c})
   \end{aligned}
   $$

   **学习过程**: 我们可以通过检查两个时间步的序列。条件最大似然准则是
   $$
   \begin{aligned}
   & \log p\left(\boldsymbol{y}^{(1)}, \boldsymbol{y}^{(2)} \mid \boldsymbol{x}^{(1)}, \boldsymbol{x}^{(2)}\right) \\
   & =\log p\left(\boldsymbol{y}^{(2)} \mid \boldsymbol{y}^{(1)}, \boldsymbol{x}^{(1)}, \boldsymbol{x}^{(2)}\right)+\log p\left(\boldsymbol{y}^{(1)} \mid \boldsymbol{x}^{(1)}, \boldsymbol{x}^{(2)}\right) .
   \end{aligned}
   $$
   因此最大似然在训练时指定正确反馈，而不是将自己的输出反馈到模型, 如下图所示。这意味着任何基于比较时刻$t$的预测和时刻$t$的训练目标的损失函数中的所有时间步都解耦了。可以通过并行化进行训练
   
   ![image-20230401184854100](Lecture%204.%20RNN.assets/image-20230401184854100.png)
   
   **缺点**: 不能模拟通用图灵机。因为输出单元明确地训练成匹配训练集的目标，它们不太能捕获关于过去输入历史的必要信息，除非用户知道如何描述系统的全部状态，并将它作为训练目标的一部分。
3. 隐藏单元之间存在循环连接，但读取整个序列后产生单个输出的循环网络

   ![image-20230401113454486](Lecture%204.%20RNN.assets/image-20230401113454486.png)

### 1.3. RNN梯度的计算

考虑如下所示的RNN结构, 假设损失是迄今为止给定了输人后的真实目标 $y^{(t)}$ 的负对数似然
$$
\begin{aligned}
& \boldsymbol{a}^{(t)}=\boldsymbol{b}+W\boldsymbol{h}^{(t-1)}+U \boldsymbol{x}^{(t)} \\
& \boldsymbol{h}^{(t)}= \tanh \left(\boldsymbol{a}^{(t)}\right) \\
& \boldsymbol{o}^{(t)}=\boldsymbol{c}+V \boldsymbol{h}^{(t)} \\
& \hat{\boldsymbol{y}}^{(t)}=\operatorname{softmax}\left(\boldsymbol{o}^{(t)}\right)
\end{aligned}
$$
![image-20230401113259698](Lecture%204.%20RNN.assets/image-20230401113259698.png)

对于每一个时间点$t$
$$
\frac{\partial L}{\partial L^{(t)}}=1
$$
对于所有$i, t$, 关于时间步$t$输出的梯度$\nabla_{\boldsymbol{o}^{(t)}} L$ 如下
$$
\nabla_{\boldsymbol{o}^{(t)}} L = \dfrac{\partial L}{\partial L^{(t)}} \dfrac{\partial L^{(t)}}{\partial \boldsymbol{o}^{(t)}} = \hat{\boldsymbol{y}}^{(t)}  - \boldsymbol{1}_{y^{(t)}}
$$
其中, $\boldsymbol{1}_{y^{(t)}}$表示第$y^{(t)}$位为$1$, 其他位为$0$的向量. 

我们从序列的末尾开始, 反向进行计算。在最后的时间步 $\tau, h^{(\tau)}$ 只有 $o^{(\tau)}$ 作为后续节点, 因此
$$
\nabla_{\boldsymbol{h}^{(\tau)}} L=V^{\top} \nabla_{\boldsymbol{o}^{(\tau)}} L
$$
注意到$\boldsymbol{h}^{(t)}(t<\tau)$ 同时具有 $\boldsymbol{o}^{(t)}$ 和 $\boldsymbol{h}^{(t+1)}$ 两个后续节点。因此, 它的梯度由下式计算
$$
\begin{aligned}
 \nabla_{\boldsymbol{h}^{(t)}} L& =\left(\frac{\partial \boldsymbol{h}^{(t+1)}}{\partial \boldsymbol{h}^{(t)}}\right)^{\top} \nabla_{\boldsymbol{h}^{(t+1)}} L+\left(\frac{\partial \boldsymbol{o}^{(t)}}{\partial \boldsymbol{h}^{(t)}}\right)^{\top}\nabla_{\boldsymbol{o}^{(t)}} L \\
& =W^{\top}\nabla_{\boldsymbol{h}^{(t+1)}} L \operatorname{diag}\left\{1-\left(\boldsymbol{h}^{(t+1)}\right)^2\right\}+V^{\top} \nabla_{\boldsymbol{o}^{(t)}} L
\end{aligned}
$$
关于剩下参数的梯度可以由下式给出(以$\boldsymbol{h}^{(t-1)} \to \boldsymbol{h}^{(t)}$的有向边为基础分解的版本)
$$
\begin{aligned}
\nabla_{\boldsymbol{c}} L & =\sum_t\left(\frac{\partial \boldsymbol{o}^{(t)}}{\partial \boldsymbol{c}}\right)^{\top} \nabla_{\boldsymbol{o}^{(t)}} L=\sum_t \nabla_{\boldsymbol{o}^{(t)}} L \\
\nabla_{\boldsymbol{b}} L & =\sum_t\left(\frac{\partial \boldsymbol{h}^{(t)}}{\partial \boldsymbol{b}^{(t)}}\right)^{\top} \nabla_{\boldsymbol{h}^{(t)}} L=\sum_t \operatorname{diag}\left(1-\left(\boldsymbol{h}^{(t)}\right)^2\right) \nabla_{\boldsymbol{h}^{(t)}} L \\
\nabla_V L & =\sum_t\left(\nabla_{\boldsymbol{o}^{(t)}} L\right) \boldsymbol{h}^{(t)^{\top}} \\
\nabla_W L &=\sum_t \operatorname{diag}\left(1-\left(\boldsymbol{h}^{(t)}\right)^2\right)\left(\nabla_{\boldsymbol{h}^{(t)}} L\right) \boldsymbol{h}^{(t-1)^{\top}} \\
\nabla_{U} L & =\sum_t \operatorname{diag}\left(1-\left(\boldsymbol{h}^{(t)}\right)^2\right)\left(\nabla_{\boldsymbol{h}^{(t)}} L\right) \boldsymbol{x}^{(t)^{\top}}
\end{aligned}
$$
我们可以考虑另一种可行的梯度表示(以$\boldsymbol{h}^{(t)}\to \boldsymbol{o}_{(t)}$的有向边为基础的分解)
$$
\frac{\partial L^{(t)}}{\partial \mathrm{vec}\left(W\right)^{\top}}=\sum_{k=0}^t \frac{\partial L^{(t)}}{\partial \boldsymbol{o}^{(t)\top}} \frac{\partial \boldsymbol{o}^{(t)}}{\partial \boldsymbol{h}^{(t)\top}}\left(\prod_{j=k+1}^t \frac{\partial \boldsymbol{h}^{(j)}}{\partial \boldsymbol{h}^{(j-1)\top} }\right) \frac{\partial \boldsymbol{h}^{(k)}}{\partial \mathrm{vec}\left(W\right)^{(k)\top}}
$$
则
$$
\frac{\partial L}{\partial \mathrm{vec}\left(W\right)^{\top}}=\sum\limits_{t}^{\tau} \sum_{k=0}^t \frac{\partial L^{(t)}}{\partial \boldsymbol{o}^{(t)\top}} \frac{\partial \boldsymbol{o}^{(t)}}{\partial \boldsymbol{h}^{(t)\top}}\left(\prod_{j=k+1}^t \frac{\partial \boldsymbol{h}^{(j)}}{\partial \boldsymbol{h}^{(j-1)\top} }\right) \frac{\partial \boldsymbol{h}^{(k)}}{\partial \mathrm{vec}\left(W\right)^{(k)\top}}
$$
这里用$W^{(k)}$表示第$k$时间步$\boldsymbol{h}^{(k)}$对$W$的形式导数. 这种连乘的表示方式比上面的递归的表示方式更适合用来分析RNN计算中的梯度

### 1.4. 长期依赖的挑战
考虑RNN对$W$的梯度函数
$$
\frac{\partial L^{(t)}}{\partial \mathrm{vec}\left(W\right)^{\top}}=\sum_{k=0}^t \frac{\partial L^{(t)}}{\partial \boldsymbol{o}^{(t)\top}} \frac{\partial \boldsymbol{o}^{(t)}}{\partial \boldsymbol{h}^{(t)\top}}\left(\prod_{j=k+1}^t \frac{\partial \boldsymbol{h}^{(j)}}{\partial \boldsymbol{h}^{(j-1)\top} }\right) \frac{\partial \boldsymbol{h}^{(k)}}{\partial \mathrm{vec}\left(W\right)^{(k)\top}}
$$
而根据
$$
\boldsymbol{h}^{(t)}=\tanh \left(\boldsymbol{b}+W\boldsymbol{h}^{(t-1)}+U \boldsymbol{x}^{(t)} \right) 
$$
可以得到
$$
\dfrac{\partial \boldsymbol{h}^{(t)}}{\partial \boldsymbol{h}^{(t-1)\top}} = \mathrm{diag}\left\{\tanh^{\prime}\left(\boldsymbol{b}+W\boldsymbol{h}^{(t-1)}+U \boldsymbol{x}^{(t)} \right) \right\} W
$$
于是连乘式
$$
\prod\limits_{j=k+1}^t \dfrac{\partial \boldsymbol{h}^{(j)}}{\partial \boldsymbol{h}^{(j-1)\top} } = \prod\limits_{j=k+1}^t\mathrm{diag}\left\{\tanh^{\prime}\left(\boldsymbol{b}+W\boldsymbol{h}^{(j-1)}+U \boldsymbol{x}^{(j)} \right) \right\} W
$$
因为$\tanh ^{\prime}\le 1$, 因此当$W$的特征值小于$1$并且$t-k$足够大时, 会出现$\dfrac{\partial \boldsymbol{h}^{(t)}}{\partial \boldsymbol{h}^{(t-1)\top}} \to 0$的情况. 显然, 这并不会导致$\dfrac{\partial L^{(t)}}{\partial \mathrm{vec}\left(W\right)^{\top}}$发生梯度消失(因为其梯度是加和的形式). 但是, 这会导致长期依赖关系难以被学习(因为其梯度以指数速度消失了, 很容易被短期依赖的微小扰动影响). 

即使使用ReLU作为激活函数, 也会出现类似的问题. 这是因为RNN的梯度消失来源于$W$的幂次而不是激活函数导数的幂次.

## 2. 其他RNN结构

### 2.1. 双向RNN

双向RNN结合时间上从序列起点开始移动的RNN和另一个时间上从序列末尾开始移动的RNN。

![image-20230401191944796](Lecture%204.%20RNN.assets/image-20230401191944796.png)

这个想法可以自然拓展到2维输入, 如图像, 可以用4个RNN组成, 每一个沿着4个方向中的一个计算.

### 2.2. 基于编码-解码的序列到序列架构

![image-20230401192832430](Lecture%204.%20RNN.assets/image-20230401192832430.png)

1. 编码器(encoder)RNN处理输入序列, 并输出上下文$C$, $C$通常是最终隐藏层的简单函数

2. 解码器(decoder)RNN以固定长度的向量$C$为条件产生输出序列$Y = \left(\boldsymbol{y}^{(1)}, \ldots, \boldsymbol{y}^{\left(n_y\right)}\right)$
  
   ![image-20230402181813599](Lecture%204.%20RNN.assets/image-20230402181813599.png)

这种架构的创新之处在于, 序列长度$n_x$和$n_y$可以彼此不同. 此架构的一个明显不足是, 编码器 RNN 输出的上下文 $C$ 的维度太小而难以适当地概括一个长序列。这种现象由Bahdanau et al. (2015) 在机器翻译中观察到。

## 3. 长短期记忆和其他门控RNN
### 3.1. 长短期记忆(LSTM)

![image-20230402235402584](Lecture%204.%20RNN.assets/image-20230402235402584.png)

LSTM块如上图所示, 相比于普通的RNN, LSTM增加了3个门控机制, 分别是输入门(input gate), 遗忘门(forget gate)和输出门(output gate). 这些门控机制可以控制信息的流动, 从而解决了梯度消失和梯度爆炸的问题. 我们用$\sigma(\cdot)$表示sigmoid函数, 则几个门控单元可以定义为
1. **遗忘门(forget gate)**: $\boldsymbol{f}^{(t)}=\sigma\left(W_f \boldsymbol{h}^{(t-1)}+U_f \boldsymbol{x}^{(t)}+\boldsymbol{b}_f\right)$
2. **输入门(input gate)**: $\boldsymbol{i}^{(t)}=\sigma\left(W_i \boldsymbol{h}^{(t-1)}+U_i \boldsymbol{x}^{(t)}+\boldsymbol{b}_i\right)$
3. **输出门(output gate)**: $\boldsymbol{o}^{(t)}=\sigma\left(W_o \boldsymbol{h}^{(t-1)}+U_o \boldsymbol{x}^{(t)}+\boldsymbol{b}_o\right)$

用$\boldsymbol{s}^{(t)}$表示LSTM的状态单元, 则状态的更新可以定义为
$$
\boldsymbol{s}^{(t)}=\boldsymbol{f}^{(t)} \circ \boldsymbol{s}^{(t-1)}+\boldsymbol{i}^{(t)} \circ g_s\left(W_s \boldsymbol{h}^{(t-1)}+U_s \boldsymbol{x}^{(t)}+\boldsymbol{b}_s\right)
$$
可以理解为, 状态单元以$1 - \boldsymbol{f}^{(t)}$的权重遗忘之前的输入, 并且以$\boldsymbol{i}^{(t)}$的权重接受新的输入. 

得到状态单元后, 隐藏层的输出可以定义为
$$
\boldsymbol{h}^{(t)}=\boldsymbol{o}^{(t)} \circ g_h\left(\boldsymbol{s}^{(t)}\right)
$$
下面是一个更清楚的图示, 这里用$\boldsymbol{c}$来表示状态单元

![image-20230403002414466](Lecture%204.%20RNN.assets/image-20230403002414466.png)

### 3.2. GRU
门控循环单元(Gated Recurrent Unit, GRU)是另一种门控RNN, 它的设计目标是简化LSTM, 但是在实践中效果也很好. GRU的设计思路是, 通过一个门控单元来同时控制遗忘因子和更新状态单元的决定
1. **更新门控(update gate)**: $\boldsymbol{u}^{(t)}=\sigma\left(W_u \boldsymbol{h}^{(t-1)}+U_u \boldsymbol{x}^{(t)}+\boldsymbol{b}_u\right)$
2. **复位门控(reset gate)**: $\boldsymbol{r}^{(t)}=\sigma\left(W_r \boldsymbol{h}^{(t-1)}+U_r \boldsymbol{x}^{(t)}+\boldsymbol{b}_r\right)$

状态单元的更新可以定义为
$$
\boldsymbol{h}^{(t)}=\left(1-\boldsymbol{u}^{(t)}\right) \circ \boldsymbol{h}^{(t-1)}+\boldsymbol{u}^{(t)} \circ g\left(W_h \left(\boldsymbol{r}^{(t)} \circ \boldsymbol{h}^{(t-1)}\right)+U_h \boldsymbol{x}^{(t)}+\boldsymbol{b}_h\right)
$$
可以理解为, 复位单元$\boldsymbol{r}^{(t)}$用于选择之前的隐藏层中的有效状态, 而更新单元$\boldsymbol{u}^{(t)}$用于同时接受新的输入信息和遗忘过去的信息.

![image-20230403003612017](Lecture%204.%20RNN.assets/image-20230403003612017.png)

### 3.3. LSTM如何解决长期依赖的梯度消失和梯度爆炸
考虑状态单元的更新公式
$$
\boldsymbol{s}^{(t)}=\boldsymbol{f}^{(t)} \circ \boldsymbol{s}^{(t-1)}+\boldsymbol{i}^{(t)} \circ g_s\left(W_s \boldsymbol{h}^{(t-1)}+U_s \boldsymbol{x}^{(t)}+\boldsymbol{b}_s\right)
$$
我们记$\tilde{\boldsymbol{s}}^{(t)}=g_s\left(W_s \boldsymbol{h}^{(t-1)}+U_s \boldsymbol{x}^{(t)}+\boldsymbol{b}_s\right)$, 则状态单元的更新可以写为
$$
\boldsymbol{s}^{(t)}=\boldsymbol{f}^{(t)} \circ \boldsymbol{s}^{(t-1)}+\boldsymbol{i}^{(t)} \circ \tilde{\boldsymbol{s}}^{(t)} 
$$
则根据链式法则, 我们有 
$$
\begin{aligned}
\dfrac{\partial \boldsymbol{s}^{(t)}}{\partial \boldsymbol{s}^{(t-1)\top}} =&  \dfrac{\partial \boldsymbol{s}^{(t)}}{\partial \boldsymbol{f}^{(t)\top}} \dfrac{\partial \boldsymbol{f}^{(t)}}{\partial \boldsymbol{h}^{(t-1)\top}} \dfrac{\partial \boldsymbol{h}^{(t-1)}}{\partial \boldsymbol{s}^{(t-1)\top}}+ \dfrac{\partial \boldsymbol{s}^{(t)}}{\partial \boldsymbol{i}^{(t)\top}} \dfrac{\partial \boldsymbol{i}^{(t)}}{\partial \boldsymbol{h}^{(t-1)\top}}\dfrac{\partial \boldsymbol{h}^{(t-1)}}{\partial \boldsymbol{s}^{(t-1)\top}} + \dfrac{\partial \boldsymbol{s}^{(t)}}{\partial\tilde{\boldsymbol{s}}^{(t)\top}} \dfrac{\partial \tilde{\boldsymbol{s}}^{(t)}}{\partial \boldsymbol{h}^{(t-1)\top}}\dfrac{\partial \boldsymbol{h}^{(t-1)}}{\partial \boldsymbol{s}^{(t-1)\top}} + \dfrac{\partial \boldsymbol{s}^{(t)}}{\partial \boldsymbol{s}^{(t-1)\top}} \\ 
 =& \mathrm{diag}\left\{\boldsymbol{s}^{(t-1)}\right\} \mathrm{diag}\left\{\sigma_f^{\prime}(\cdot)\right\}W_f  \mathrm{diag}\left\{\boldsymbol{o}^{(t-1)}\circ g^{\prime}_h(\boldsymbol{s}^{(t-1)})\right\}+ \mathrm{diag}\left\{\tilde{\boldsymbol{s}}^{(t)} \right\} \mathrm{diag}\left\{\sigma_i^{\prime}(\cdot)\right\}W_i\mathrm{diag}\left\{\boldsymbol{o}^{(t-1)}\circ g^{\prime}_h(\boldsymbol{s}^{(t-1)})\right\} \\ 
 +& \mathrm{diag}\left\{\boldsymbol{i}^{(t)} \right\} \mathrm{diag}\left\{g_s^{\prime}(\cdot)\right\}W_s\mathrm{diag}\left\{\boldsymbol{o}^{(t-1)}\circ g^{\prime}_h(\boldsymbol{s}^{(t-1)})\right\} + \mathrm{diag}\left\{\boldsymbol{f}^{(t)}\right\} \\ 
\end{aligned}
$$
于是, 如果我们要计算$W_s$的导数, 设输出层为$\hat{\boldsymbol{y}}^{(t)}$. 以$\boldsymbol{s}^{(t-1)} \to \boldsymbol{s}^{(t)}$的有向边为基础分解的版本结果为
$$
\frac{\partial L^{(t)}}{\partial \mathrm{vec}\left(W_s\right)^{\top}}=\sum_{k=0}^t \frac{\partial L^{(t)}}{\partial \hat{\boldsymbol{y}}^{(t)\top}} \frac{\partial \hat{\boldsymbol{y}}^{(t)}}{\partial \boldsymbol{h}^{(t)\top}}\frac{\partial \boldsymbol{h}^{(t)}}{\partial \boldsymbol{s}^{(t)\top}}\left(\prod_{j=k+1}^t \frac{\partial \boldsymbol{s}^{(j)}}{\partial \boldsymbol{s}^{(j-1)\top} }\right) \frac{\partial \boldsymbol{s}^{(k)}}{\partial \mathrm{vec}\left(W_s\right)^{(k)\top}}
$$
我们来分析这里的连乘项
$$
\dfrac{\partial \boldsymbol{s}^{(t)}}{\partial \boldsymbol{s}^{(t-1)\top}} = \left[\mathrm{diag}\left\{\boldsymbol{s}^{(t-1)}\right\} \mathrm{diag}\left\{\sigma_f^{\prime}(\cdot)\right\}W_f + \mathrm{diag}\left\{\boldsymbol{i}^{(t)} \right\} \mathrm{diag}\left\{g_s^{\prime}(\cdot)\right\}W_s+ \mathrm{diag}\left\{\tilde{\boldsymbol{s}}^{(t)} \right\} \mathrm{diag}\left\{\sigma_i^{\prime}(\cdot)\right\}W_i\right]\mathrm{diag}\left\{\boldsymbol{o}^{(t-1)}\circ g^{\prime}_h(\boldsymbol{s}^{(t-1)})\right\} + \mathrm{diag}\left\{\boldsymbol{f}^{(t)}\right\}
$$
在这里$\boldsymbol{o}^{(t-1)}$可以缓解梯度爆炸. 而$\boldsymbol{f}^{(t)}$可以缓解长期记忆的梯度消失. 网络通过学习来决定如何控制梯度的衰减/爆炸. 

但是, 只要网络中有一条路径的梯度没有消失, 长期记忆就是可学习的. 然而, 只要网络中有一条路径发生了梯度爆炸, 整体的梯度就会发生爆炸. 因此, 从这个角度, 门控单元解决的主要是梯度消失而不是梯度爆炸问题.

