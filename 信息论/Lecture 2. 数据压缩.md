## 1. 随机过程的熵率
### 1.1. 熵率的定义
**熵率的极限定义**: 当如下极限存在时, 随机过程$\{X_i\}$的熵率定义为
$$
H(\mathcal{X})=\lim_{n\to\infty} \dfrac{1}{n} H(X_1,X_2,\cdots , X_n)
$$

**熵率的条件熵定义**: 当如下的极限存在时, 随机过程$\{X_i\}$的熵率定义为
$$
H^{\prime}(\mathcal{X})=\lim_{n\to\infty} H(X_n\mid X_{n-1},X_{n-2},\cdots , X_1)
$$

**Note**: 显然, 熵率并不总是存在的. 即使这些随机变量$\{X_i\}$是独立的. 事实上, 取
$$
p_{i}= \begin{cases}0.5 & \text { if } 2 k<\log \log i \leq 2 k+1 \\ 0 & \text { if } 2 k+1<\log \log i \leq 2 k+2\end{cases}
$$
可以发现无论使用哪一种定义, 熵率都是不存在的. 

### 1.2. 平稳过程的熵率
对于平稳的随机过程, 两种不同方式定义的熵率均存在且相等. 
$$
H(\mathcal{X})=H'(\mathcal{X})
$$
这表明对于平稳的随机过程, 我们可以任意使用熵率的定义
___
##### Proof
显然, 对于平稳的随机过程, 我们有
$$
\begin{aligned}
H\left(X_{n+1} \mid X_{1}, X_{2}, \ldots, X_{n}\right) & \leq H\left(X_{n+1} \mid X_{n}, \ldots, X_{2}\right) =H\left(X_{n} \mid X_{n-1}, \ldots, X_{1}\right)
\end{aligned}
$$
因此
$$
H'(\mathcal{X})=\lim\limits_{n\to\infty} H(X_n\mid X_{n-1},X_{n-2},\cdots , X_1)
$$
存在. 

而根据[[../分析学/Book 1. 数学分析/Chapter 1. 基础知识/Lecture 2. 极限#1.3. Stolz定理|Stolz定理]]和[[Lecture 1. 熵、相对熵和互信息#1.3. 条件熵的链式法则|条件熵的链式法则]]. 
$$
\lim_{n\to\infty}\frac{H\left(X_{1}, X_{2}, \ldots, X_{n}\right)}{n}=\lim_{n\to\infty}\frac{1}{n} \sum_{i=1}^{n} H\left(X_{i} \mid X_{i-1}, \ldots, X_{1}\right)=\lim\limits_{n\to\infty} H(X_n\mid X_{n-1},X_{n-2},\cdots , X_1)
$$
因此就有
$$
H(\mathcal{X})=H'(\mathcal{X})
$$
#####
___

### 1.3. Markov链的熵率
设$\{X_i\}$为平稳的Markov链, 其平稳分布为$\boldsymbol{\mu}$, 转移概率矩阵为$P$, 那么熵率为
$$
H(\mathcal{X}) = -\sum_{ij} \mu_i P_{ij} \log P_{ij}
$$

### 1.4. Markov链函数的界
若$X_1,X_2,\cdots, X_n$构成平稳的Markov链, 并且$Y_i=\Phi(X_i)$, 那么
$$
H(Y_n\mid Y_{n-1},\cdots Y_1, X_1)\le H(\mathcal{Y})\le H(Y_n\mid Y_{n-1},\cdots , Y_1)
$$
并且
$$
\lim_{n\to \infty} H(Y_n\mid Y_{n-1},\cdots Y_1, X_1) =H(\mathcal{Y})=\lim_{n\to \infty} H(Y_n\mid Y_{n-1},\cdots , Y_1)
$$
___
##### Proof
显然, 对于平稳的随机过程, 我们有
$$
\begin{aligned}
H\left(Y_{n+1} \mid Y_{1}, Y_{2}, \ldots, Y_{n}\right) & \leq H\left(Y_{n+1} \mid Y_{n}, \ldots, Y_{2}\right) =H\left(Y_{n} \mid Y_{n-1}, \ldots, Y_{1}\right)
\end{aligned}
$$
因此不等式右侧显然成立. 

下面证明左边的不等式成立, 对$k=1,2,\cdots$, 有
$$
\begin{aligned} 
    H(Y_n\mid Y_{n-1}, \cdots, Y_2, Y_1, X_1) &=  H(Y_n\mid Y_{n-1}, \cdots, Y_2, Y_1, X_1, X_0, X_{-1}, \cdots, X_{-k}) \\
    & = H(Y_n\mid Y_{n-1}, \cdots, Y_2, Y_1, X_1, X_0, X_{-1}, \cdots, X_{-k}, Y_0, \cdots, Y_{-k}) \\
    & \le H(Y_n\mid Y_{n-1}, \cdots, Y_2, Y_1,  Y_0, \cdots, Y_{-k}) \\
    & = H(Y_{n+k+1}\mid Y_{n+k}, \cdots , Y_1)
\end{aligned}
$$
因此, 我们有
$$
 H(Y_n\mid Y_{n-1}, \cdots, Y_2, Y_1, X_1) \le\lim\limits_{k\to\infty} H(Y_{n+k+1}\mid Y_{n+k}, \cdots , Y_1) = H(\mathcal{Y})
$$

下面, 只需要证明左右区间长度趋于$0$. 
$$
    H(Y_n\mid Y_{n-1}, \cdots, Y_1) -   H(Y_n\mid Y_{n-1}, \cdots, Y_1, X_1)  = I(X_1; Y_n\mid Y_{n-1}, \cdots, Y_1) 
$$
根据互信息的性质
$$
\begin{aligned} 
    H(X_1) &\ge \lim\limits_{n\to\infty}  I(X_1; Y_1, Y_2, \cdots, Y_n)  \\ 
    & = \lim\limits_{n\to\infty} I(X_1; Y_1) + I(X_1; Y_2\mid Y_1) + \cdots + I(X_1; Y_n\mid Y_1, Y_2, \cdots, Y_{n-1}) \\
    & = \sum\limits_{i=1}^{\infty} I(X_1; Y_i\mid Y_{i-1}, \cdots, Y_1)
\end{aligned}
$$
由于上面的无限和是有限的, 且每一项均非负, 故有
$$
\lim\limits_{n\to\infty} I(X_1; Y_n\mid Y_{n-1}, \cdots, Y_1) = 0
$$
于是, 我们有
$$
\lim_{n\to \infty} H(Y_n\mid Y_{n-1},\cdots Y_1, X_1) =H(\mathcal{Y})=\lim_{n\to \infty} H(Y_n\mid Y_{n-1},\cdots , Y_1)
$$
#####
___

## 2. 唯一可译码
### 2.1. 信源编码
关于随机变量$X$的信源编码$C$是从$X$的取值空间$\mathcal{X}$到$\mathcal{D}^*$的一个映射, 其中$\mathcal{D}^*$表示$D$元字母表$\mathcal{D}$上有限长度的字符串所构成的集合. 用$C(x)$表示$x$的码字, 用$l(x)$表示$C(x)$的长度. 
	
信源编码$C(x)$的期望长度$L(C)$定义为
$$
L(C)=\sum_{x\in \mathcal{X}}p(x)l(x)
$$

### 2.2. 编码的拓展(extension)
编码$C$的扩展$C^*$是从$\mathcal{X}$上的有限长字符串到$\mathcal{D}$上的有限长字符串的映射, 定义为
$$
C(x_1,x_2,\cdots , x_n)=C(x_1)C(x_2)\cdots C(x_n)
$$
其中$C(x_1)C(x_2)\cdots C(x_n)$表示相应码字的串联

### 2.3. 唯一可译码(uniquely decodable code)
如果一个编码的拓展码是非奇异的, 也就是说对任意的$(x_1, x_2, \cdots, x_n)\neq (x_1^{\prime}, x_2^{\prime}, \cdots, x_n^{\prime})$, 都有
$$
C(x_1, x_2, \cdots, x_n)\neq C(x_1^{\prime}, x_2^{\prime}, \cdots, x_n^{\prime})
$$
则称该编码是唯一可译的. 
	
特别地, 若码中无任何码字是其他码字的前缀, 则称该编码为前缀码(prefix code)或即时编码(instantaneous code)

### 2.4. 唯一可译码的判定

![image-20230526202041547](./Lecture%202.%20%E6%95%B0%E6%8D%AE%E5%8E%8B%E7%BC%A9.assets/image-20230526202041547.png)

## 3. Kraft不等式
### 3.1. Kraft不等式(前缀码)
对于任意构成前缀码的有限码字集, 码字长度满足Kraft不等式
$$
\sum\limits_{i=1}^{\infty} D^{-l_i}\le 1
$$
反之, 若给定任意满足Kraft不等式的$l_1,l_2,\cdots$, 可以构造出具有相应码长的前缀码. 
___
##### Proof
不妨设第$i$个码字为$y_1y_2\cdots y_{l_i}$. 设$0.y_1y_2\cdots y_{l_i}$是一个$D$进制的实值小数, 则可以将该码字和一个区间
$$
\left[0.y_1y_2\cdots y_{l_i},\ 0.y_1y_2\cdots y_{l_i}+\dfrac{1}{D^{l_i}}\right)
$$
相对应, 这个区间是$[0,1]$的子区间, 并且根据前缀码的性质, 所有的区间均不相交. 这就证明了
$$
\sum\limits_{i=1}^{\infty} D^{-l_i}\le 1
$$
#####
___

### 3.2. 唯一可译码和前缀码的可转换性
对于任意一个唯一可译的编码$C(x)$, 总可以找到一个前缀码$P(x)$, 使得$P(x)$的期望长度不超过$C(x)$的期望长度. 

### 3.3. Kraft不等式(唯一可译码)
对于任意构成唯一可译码的可数码字集, 码字长度满足{\rm Kraft}不等式
$$
\sum_{i=1}^{\infty} D^{-l_i}\le 1
$$
反之, 若给定任意满足Kraft不等式的$l_1,l_2,\cdots$, 可以构造出具有相应码长的唯一可译码. 
___
##### Proof
首先先证明有限的情况. 考虑$C$的$k$次拓展$C^k$, 由唯一可译性的定义, 该码是非奇异的. 我们有
$$
\left(\sum_{x\in \mathcal{X}}D^{-l(x)}\right)^k=\sum_{x^k\in \mathcal{X}^k}D^{-l(x^k)}
$$
按照码字长度合并同类项, 可以得到
$$
\sum_{x^k\in \mathcal{X}^k}D^{-l(x^k)}=\sum_{m=1}^{kl_{\max}}a(m)D^{-m}
$$
其中$l_{\max}$代表码字的最大长度, $a(m)$表示所有长度为$m$的码字所对应的$x^k$的数目. 

因此
$$\left(\sum_{x\in \mathcal{X}}D^{-l(x)}\right)^k\le \sum_{m=1}^{kl_{\max}}D^mD^{-m}=kl_{\max}$$
因此当$k\to \infty$时, 有
$$
\sum\limits_{j}D^{-l_j}\le 1
$$
这就是Kraft不等式. 对于无限的码字表, 只需要对其任意的子序列取极限即可. 
$$\sum_{i=1}^{\infty}D^{-l_i}=\lim_{N\to \infty} \sum_{i=1}^N D^{-l_i}\le 1$$
#####
___