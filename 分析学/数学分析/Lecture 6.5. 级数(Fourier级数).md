## 1. Fourier级数
### 1.1. Euler-Fourier 公式(Fourier系数的计算)
设$f$ 是以 $2 \pi$ 为周期的函数且在 $[-\pi, \pi]$ 上可积和绝对可积, 计算 $f$ 的傅里叶级数的 Euler-Fourier 公式是:
$$
\begin{aligned} 
    a_n & =\frac{1}{\pi} \int_{-\pi}^\pi f(x) \cos n x \mathrm{~d} x, \quad n=0,1,2 \cdots \\
b_n & =\frac{1}{\pi} \int_{-\pi}^\pi f(x) \sin n x \mathrm{~d} x, \quad n=1,2 \cdots 
\end{aligned}
$$
如果三角级数 $\dfrac{a_0}{2}+\sum\limits_{n=1}^{\infty} a_n \cos n x+b_n \sin n x$ 中的系数满足上述公式, 则称三角级数是 $f$ 的傅里叶级数, 记为
$$
f(x) \sim \frac{a_0}{2}+\sum_{n=1}^{\infty}\left(a_n \cos n x+b_n \sin n x\right)
$$
一致收敛的三角级数必然是其和函数的 Fourier 级数

### 1.2. Fourier级数的导数
设以 $2 \pi$ 为周期的连续函数 $f$ 在 $[-\pi, \pi]$ 上除了有限个点以外可导, 又设在任意补充有限个点上的值之后) $f^{\prime}$ 在 $[-\pi, \pi]$ 上可积和绝对可积, 则
$$
f^{\prime}(x) \sim \sum_{n=1}^{\infty}\left(a_n \cos n x+b_n \sin n x\right)^{\prime}=\sum_{n=1}^{\infty}\left(n b_n \cos n x-n a_n \sin n x\right)
$$
若用 $a_n^{\prime}, b_n^{\prime}$ 表示 $f^{\prime}$ 的 Fourier 级数, 这就等价于
$$
a_0^{\prime}=0, a_n^{\prime}=n b_n, b_n^{\prime}=-n a_n
$$

## 2. Fourier系数的估计
### 2.1. Fourier系数的渐进估计
设以 $2 \pi$ 为周期的函数 $f$ 在 $[-\pi, \pi]$ 上除了有限个点以外均有 $k+1$ 阶导数. 如果其 $k$ 阶导数 $f^{(k)}$ 在 $[-\pi, \pi]$ 上处处连续且 $f^{(k+1)}$ 在 $[-\pi, \pi]$ 上可积和绝对可积, 则有
$$
a_n=o\left(\frac{1}{n^{k+1}}\right), \quad b_n=o\left(\frac{1}{n^{k+1}}\right)
$$
特别地, 当 $f$ 是周期 $2 \pi$ 的可积和绝对可积函数, 则其傅里叶系数 $\left\{a_n\right\}$ 和 $\left\{b_n\right\}$ 必为无穷小量
$$
\lim _{n \rightarrow \infty} a_n=\lim _{n \rightarrow \infty} b_n=0
$$