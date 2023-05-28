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
### 2.1. 可导条件下Fourier系数的渐进估计
设以 $2 \pi$ 为周期的函数 $f$ 在 $[-\pi, \pi]$ 上除了有限个点以外均有 $k+1$ 阶导数. 如果其 $k$ 阶导数 $f^{(k)}$ 在 $[-\pi, \pi]$ 上处处连续且 $f^{(k+1)}$ 在 $[-\pi, \pi]$ 上可积和绝对可积, 则有
$$
a_n=o\left(\frac{1}{n^{k+1}}\right), \quad b_n=o\left(\frac{1}{n^{k+1}}\right)
$$
特别地, 当 $f$ 是周期 $2 \pi$ 的可积和绝对可积函数, 则其傅里叶系数 $\left\{a_n\right\}$ 和 $\left\{b_n\right\}$ 必为无穷小量
$$
\lim _{n \rightarrow \infty} a_n=\lim _{n \rightarrow \infty} b_n=0
$$

### 2.2. Lipschitz条件下Fourier系数的渐进估计
若 $f$ 是周期 $2 \pi$ 的函数且存在 $\alpha \in(0,1]$, 使得 $f$ 满足 $\alpha$ 阶 Lipschitz 条 件:
$$
|f(x)-f(y)| \leq L|x-y|^\alpha
$$
其中 $L$ 为常数, 则成立
$$
a_n=O\left(\frac{1}{n^\alpha}\right), \quad b_n=O\left(\frac{1}{n^\alpha}\right)
$$

## 3. Fourier系数的性质
### 3.1. Fourier系数是最佳三角逼近系数
设 $f$ 是区间 $[\pi, \pi]$ 上的可积和平方可积函数, $T_n(x)$ 是满足下述条件的任意三角多项式
$$
T_n(x) \sim \frac{A_0}{2}+\sum_{k=1}^n\left(A_k \cos k x+B_k \sin k x\right)
$$
$S_n(x)$ 是 $f$ 的 Fourier 级数的部分和函数
$$
S_n(x) \sim \frac{a_0}{2}+\sum_{k=1}^n\left(a_k \cos k x+b_k \sin k x\right)
$$
则有
$$
d^2\left(f, S_n\right) \leq d^2\left(f, T_n\right)
$$
当且仅当 $T_n \equiv S_n$ 时等号成立. 其中 $d^2\left(f, T_n\right)$ 是三角多项式逼近 $f$ 的逼近误差, 按照平方平均的意义定义:
$$
d^2\left(f, T_n\right)=\frac{1}{2 \pi} \int_{-\pi}^\pi\left[f(x)-T_n(x)\right]^2 \mathrm{~d} x
$$

### 3.2. Parseval恒等式
设 $f$ 在 $[-\pi, \pi]$ 上可积和平方可积, $f(x) \sim \dfrac{a_0}{2}+\sum\limits_{n=1}^{\infty}\left(a_n \cos n x+b_n \sin n x\right)$, 则有下列的等式成立
$$
\frac{a_0^2}{2}+\sum_{n=1}^{\infty}\left(a_n^2+b_n^2\right)=\frac{1}{\pi} \int_{-\pi}^\pi f^2(x) \mathrm{d} x
$$

### 3.3. Parseval恒等式的推广
设 $f, g$ 均在 $[-\pi, \pi]$ 上可积和平方可积, $\left\{a_n\right\},\left\{b_n\right\}$ 是 $f$ 的 Fourier 系数, $\left\{\alpha_n\right\},\left\{\beta_n\right\}$ 是 $g$ 的 Fourier 系数, 则成立
$$
\frac{1}{\pi} \int_{-\pi}^\pi f(x) g(x) \mathrm{d} x=\frac{a_0 \alpha_0}{2}+\sum_{n=1}^{\infty}\left(a_n \alpha_n+b_n \beta_n\right)
$$

## 4. Dirichelet核
### 4.1. Dirichelet核
在区间 $(0, \pi)$ 上定义 
$$
D_n(x)=\frac{\sin \dfrac{(2 n+1) x}{2}}{2 \sin \dfrac{x}{2}}, n \in N^{+}
$$
则 
$$
\int_0^\pi D_n(x) \mathrm{d} x=\frac{\pi}{2}
$$
其中$D_n$被称为Dirichelet核. $D_n$也可以写为离散的形式
$$
D_n(x) = \dfrac{1}{2}\sum\limits_{k=-n}^{n} e^{\mathrm{i}kx}
$$

### 4.2. Dirichelet核
利用 Euler-Fourier 公式和三角变换, 将函数 $f$ 的 Fourier 级数的部分和函数列
$$
S_n(x)=\frac{a_0}{2}+\sum_{k=1}^n\left(a_k \cos k x+b_k \sin k x\right)
$$
用 Dirichlet 积分表示出来
$$
S_n(x)=\frac{1}{\pi} \int_{-\pi}^\pi f(x+t) D_n(t) \mathrm{d} t=\frac{1}{\pi} \int_0^\pi[f(x+t)+f(x-t)] D_n(t) \mathrm{d} t
$$
这是一个卷积的形式, 