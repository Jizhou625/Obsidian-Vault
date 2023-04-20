## 1. 收敛域和收敛半径
### 1.1. Abel第一定理
幂级数 $\sum\limits_{n=0}^{\infty} a_n\left(x-x_0\right)^n$ 的收敛域一定是以 $x_0$ 为中心的区间 $\left\langle x_0-R, x_0+R\right\rangle$, 且于其内部$\left(x_0- R, x_0+R\right)$ 处处绝对收敛, 其中 $R \geq 0$ 称为该幂级数的收敛半径

### 1.2. Abel第二定理
幂级数 $\sum\limits_{n=0}^{\infty} a_n\left(x-x_0\right)^n$ 必于其收敛域中内闭一致收敛. 

### 1.3. 幂级数的收敛半径
若幂级数 $\sum\limits_{n=0}^{\infty} a_n\left(x-x_0\right)^n$的收敛半径$R$大于$0$, 则其在$\left(x_0- R, x_0+R\right)$内无限次可微, 且可以逐项积分和逐项求导

### 1.4. Cauchy-Hadamard公式
幂级数$\sum\limits_{n=0}^{\infty} a_n\left(x-x_0\right)^n$ 的收敛半径为
$$
R=\frac{1}{\varlimsup\limits_{n \rightarrow \infty} \sqrt[n]{\left|a_n\right|}}
$$

## 2. 幂级数的性质
### 2.1. Tauber定理(边界条件)
设已知幂级数 $\sum\limits_{n=0}^{\infty} a_n x^n=S(x)$ 在 $(-1,1)$ 上成立, 如果 $\lim \limits_{x \rightarrow 1^{-}} S(x)=S$ 且 $\lim\limits _{n \rightarrow \infty} n a_n=0$, 则 $\sum\limits_{n=0}^{\infty} a_n=S$

### 2.2. 幂级数展开的唯一性
如果函数 $f$ 在点 $x_0$ 的某个邻域 $U\left(x_0\right)$ 内能展开为幂级数 $\sum\limits_{n=0}^{\infty} a_n\left(x-x_0\right)^n$, 也即 $f(x)=$ $\sum\limits_{n=0}^{\infty} a_n\left(x-x_0\right)^n, x \in U\left(x_0\right)$, 则这个幂级数展开式是唯一的, 而且它就是 $f$ 在 $x_0$ 处的 Taylor 级数. 每个幂级数都是Taylor级数

### 2.3. 幂级数可展开的充要条件
$f$ 在点 $x_0$ 的邻域 $U\left(x_0\right)$ 能展开为幂级数 $\sum\limits_{n=0}^{\infty} a_n\left(x-x_0\right)^n$ 的充分必要条件是 $f$ 的 Taylor 公式的余项
$$
r_n(x)=f(x)-\sum_{k=0}^n \frac{f^{(k)}\left(x_0\right)}{k !}\left(x-x_0\right)^k
$$
在邻域 $U\left(x_0\right)$ 内处处收敛于 0