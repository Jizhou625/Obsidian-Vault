## 1. 一般项级数的基本性质
### 1.1. Riemann重排定理
设级数 $\sum\limits_{n=1}^{\infty} a_n$ 条件收敛, 则对于任意满足 $-\infty \leq A \leq B \leq+\infty$ 的 $A, B$, 可以改变级数 $\sum\limits_{n=1}^{\infty} a_n$ 中项排列的顺序, 使得重排之后的级数部分和数列 $\left\{S_n^{\prime}\right\}$ 满足要求
$$
\varliminf_{n \rightarrow+\infty} S_n^{\prime}=A, \quad \varlimsup_{n \rightarrow+\infty} S_n^{\prime}=B
$$
特别是当 $A=B$ 时, 重排级数的和可以是任何有限数或带确定符号的无穷大

## 2. Cauchy乘积
### 2.1. Cauchy乘积的定义
一般地, 柯西乘积定义为如下的离散卷积形式
$$
\left(\sum_{n=0}^{\infty} a_n\right) \cdot\left(\sum_{n=0}^{\infty} b_n\right)=\sum_{n=0}^{\infty} c_n
$$
这里
$$
c_n=\sum_{k=0} a_k b_{n-k}, n=0,1,2, \ldots
$$
### 2.2. Mertens定理
设 $\sum\limits_{k=0}^{\infty} a_k=A$ 和 $\sum\limits_{k=0}^{\infty} b_k=B$, 且其中至少有一个级数绝对收敛, 则就有 $\sum\limits_{k=0}^{\infty} c_k=A \cdot B$. 其中 $c_k$ 是 $a_k, b_k$ 的 Cauchy 乘积.
___
**Note**: 当两个级数都只是条件收敛的时候, Mertens定理不成立. 例如考虑两个交错级数
$$
a_n=b_n=\frac{(-1)^n}{\sqrt{n+1}}
$$
其柯西乘积由下式给出
$$
c_n=\sum_{k=0}^n \frac{(-1)^k}{\sqrt{k+1}} \cdot \frac{(-1)^{n-k}}{\sqrt{n-k+1}}=(-1)^n \sum_{k=0}^n \frac{1}{\sqrt{(k+1)(n-k+1)}}
$$
显然我们有
$$
|c_n|\ge \sum\limits_{k=0}^n \dfrac{1}{n+1} = 1
$$
因此其Cauchy乘积的和不收敛. 
___
**Proof**: 设$A_n = \sum\limits_{k=0}^{n} a_k$, $B_n = \sum\limits_{k=0}^{n} b_k$, $C_n = \sum\limits_{k=0}^{n} c_k$, 不妨设$\sum\limits_{k=0}^{\infty} a_n$绝对收敛, 于是我们有
$$
C_n=\sum_{i=0}^n \sum_{k=0}^i a_k b_{i-k}=\sum_{i=0}^n B_i a_{n-i} = \sum_{i=0}^n\left(B_i-B\right) a_{n-i}+B A_n
$$
对于任意给定的$\varepsilon>0$, 存在充分大的整数$N$, 对于任意的$n\ge N$, 都有
$$
\left|B_n-B\right|<\frac{\varepsilon / 4}{\sum\limits_{n=0}^{\infty}\left|a_n\right|+1}
$$
并且存在一个充分大的整数$M$, 对于所有$n\ge M$, 有
$$
\left|a_{n-N}\right|<\frac{\varepsilon / 4}{N \sup \left|B_n-B\right|+1}
$$
同样地, 存在一个充分大的整数$L$, 对于所有的$n\ge L$, 有
$$
|A_n- A|< \dfrac{\varepsilon / 2}{|B|+1}
$$
因此, 对于$n> \max\{N, M, L\}$, 有
$$
\begin{aligned} 
    |C_n - AB| &= \left| \sum\limits_{i=0}^{n} (B_i - B)a_{n-i}+ B(A_n - A)\right| \\  
    & \le \sum\limits_{i=0}^{N-1} \left|B_i - B\right| \left|a_{n-i}\right| + \sum\limits_{i=N}^{n} \left|B_i - B\right| \left|a_{n-i}\right| + \left|B\right| \left|A_n - A\right| \\
    & \le \varepsilon
\end{aligned}
$$
根据收敛的定义, 可以得到$\lim\limits_{n\to\infty} C_n = AB$


### 2.3. Cauchy乘积收敛的值
设 $\sum\limits_{n=1}^{\infty} a_n=A$ 和 $\sum\limits_{n=1}^{\infty} b_n=B$ 收敛, 且它们的 Cauchy 乘积 $\sum\limits_{n=1}^{\infty} c_n=C$ 也收敛, 则 $C=A \cdot B$
