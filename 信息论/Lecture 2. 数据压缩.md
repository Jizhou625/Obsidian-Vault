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

显然, 熵率并不总是存在的. 即使这些随机变量$\{X_i\}$是独立的. 事实上, 取
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

而根据[[../分析学/数学分析/Lecture 1. 极限#1.3. Stolz定理|Stolz定理]]和[[Lecture 1. 熵、相对熵和互信息#1.3. 条件熵的链式法则|条件熵的链式法则]]. 
$$
\lim_{n\to\infty}\frac{H\left(X_{1}, X_{2}, \ldots, X_{n}\right)}{n}=\lim_{n\to\infty}\frac{1}{n} \sum_{i=1}^{n} H\left(X_{i} \mid X_{i-1}, \ldots, X_{1}\right)=\lim\limits_{n\to\infty} H(X_n\mid X_{n-1},X_{n-2},\cdots , X_1)
$$
因此就有
$$
H(\mathcal{X})=H'(\mathcal{X})
$$
#####
___

### 1.3. 马尔科夫链函数的界
若$X_1,X_2,\cdots, X_n$构成平稳的马尔科夫链, 并且$Y_i=\Phi(X_i)$, 那么
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
因此右侧显然成立. 

下面证明左边的
#####
___