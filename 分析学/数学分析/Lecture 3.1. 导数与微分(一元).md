## 1. 导数的特征
### 1.1. 导数在一点的极限特征
设$f(x)$在$U(x_0)$ 上连续, 且在$x\neq x_0$处可导. 若有$\lim\limits_{x \to x_0}f'(x)=A$. 则$f'(x_0)$存在且等于$A$, 该性质也可以用导函数不存在第一类间断点来描述

### 1.2. 导数的中值性
设$f(x)$在$[a,b]$上可导, 则$f'(x)$可以取到位于$f'(a)$和$f'(b)$之间的一切值.

### 1.3. 相继零点的导数
若$\alpha,\beta$为$f(x)=0$的两相继零点, 则$f'(\alpha)\cdot f'(\beta)\le 0$, 等号成立当且仅当$\alpha$和$\beta$中至少有一个为$f(x)$的重根.

### 1.4. 渐近线和极限
设$f(x)$在$(a,\infty)$上可导, 即使曲线$y=f(x)$在$x \to \infty$时有斜渐近线, 也不一定存在极限$\lim\limits_{x \to \infty}f'(x)$
___
**Example**: $f(x)=x+\dfrac{\sin x^2}{x}$, 容易得到渐近线为$y=x$, 但由于$f'(x)=1+2\cos x^2-\dfrac{\sin x^2}{x^2}$, 所以$f'(x)$在$x \to +\infty $上无极限

## 2. 反函数与隐函数求导法则
### 2.1 反函数求导法则
设$x=\varphi(y)$ 在点$y_0$的某个邻域上为严格单调连续函数, 且有$\varphi'(y_0)\neq 0$. 若$y=f(x)$是$x=\varphi(y)$的反函数, 则$f(x)$在点$x_0=\varphi(y_0)$处可导,而且有$f'(x_0)=\dfrac{1}{\varphi^{\prime}(y_0)}$. 用微分算子的形式可以写作$\dfrac{\mathrm{d}y}{\mathrm{d} x} = \dfrac{1}{\dfrac{\mathrm{d}x}{\mathrm{d} y}}$

### 2.2. 隐函数求导
设$\begin{cases}  x=\varphi(t) \\ y=\psi(t) \end{cases}$在区间$(a,b)$上处处可导, 且$\varphi'(t)\neq 0$, 则$\forall t\in (a,b)$, 则有以下结论成立:
1. $x=\varphi(t)$是区间$(a,b)$上的严格单调的连续函数, 因而存在反函数$t=t(x)$;
2. 在$x=\varphi(t)$和$y=\psi(t)$之间存函数关系$y=\psi(t(x))$, 简记为$y=y(x)$
3. 函数$y=y(x)$可导, 且有公式
    $$
    y'(x)=\dfrac{\psi'(t)}{\varphi'(t)}\Bigg|_{t=t(x)}
    $$

## 3. 微分学基本定理
### 3.1. 广义Taylor中值公式
设$f(x) \in C^{(n)}([a,b]), g(x) \in C^{(n)}([a,b])$, 且在$(a,b)$上都有$n$阶导数, $x_0 \in [a,b]$, 对$\forall x\in [a,b]\neq x_0$, $\exists \xi, a<\xi<b$, 使得
$$
\left[f(x)-\sum_{k=0}^{n}\dfrac{f^{(k)}(x_0)}{k!}(x-x_0)^k\right]g^{(n+1)}(\xi)=\left[g(x)-\sum_{k=0}^{n}\dfrac{g^{(k)}(x_0)}{k!}(x-x_0)^k\right]f^{(n+1)}(\xi)
$$
___
不妨设$x_0<x<b$, 取定$x$, 作
$$
F(t)=f(t)+\displaystyle{\sum_{k=1}^{n-1}\dfrac{f^{(k)}(t)}{k!}(x-t)^k}
$$
$$
G(t)=g(t)+\displaystyle{\sum_{k=1}^{n-1}\dfrac{g^{(k)}}{k!}(x-t)^k}
$$
利用Cauchy中值公式可得
$$
F'(\xi)\left[G(x)-G(x_0)\right]=G'(\xi)\left[F(x)-F(x_0)\right]
$$
将导数的表达式带入即可得命题成立. 注意到, 取$g(x)=(x-x_0)^n$即可得到Taylor公式

### 3.2. 泰勒公式
对于在$x_0$处$n$次可导的函数$f(x)$，我们称多项式
$$
P_n(x)\overset{\Delta}{=}P_n(x_0,x)=\sum_{k=0}^{n}\dfrac{f^{(k)}(x_0)}{k!}(x-x_0)^k
$$
为$f(x)$在点$x_0$处的Taylor多项式，而称
$$
R_n(x)\overset{\Delta}{=}R_n(x_0,x)=f(x)-\sum_{k=0}^{n}\dfrac{f^{(k)}(x_0)}{k!}(x-x_0)^k
$$
为$f(x)$在点$x_0$处的Taylor余项

**Peano余项**: 若函数$f$在点$x_0$存在$n$阶导数$f^{(n)}(x_0)$, 则有
\[f(x)=f(x_0)+f'(x_0)(x-x_0)+\cdots+\dfrac{f^{(n)}(x_0)}{n!}(x-x_0)^n+o((x-x_0)^n)\quad (x \to x_0)\]

**Lagrange余项**: 若函数$f$在点$x_0$的某个邻域$U(x_0)$中$n+1$次可微, 则对$\forall x \neq x_0\in U(x_0) $, 在$x_0$和$x$之间存在$\xi$, 使得
$$
f(x)=f(x_0)+f'(x_0)(x-x_0)+\cdots+\dfrac{f^{(n)}(x_0)}{n!}(x-x_0)^n+\dfrac{f^{n+1}(\xi)}{(n+1)!}(x-x_0)^{n+1}
$$

**Cauchy余项**:  若函数$f$在点$x_0$的某个邻域$U(x_0)$中$n+1$次可微, 则对每个$x \in U(x_0), \ x\neq x_0$, 在$x_0$和$x$之间存在$\eta$, 使得
$$
f(x)=f(x_0)+f'(x_0)(x-x_0)+\cdots+\dfrac{f^{(n)}(x_0)}{n!}(x-x_0)^n+\dfrac{f^{n+1}(\eta)}{n!}(x-\eta)^{n}(x-x_0)
$$

**积分余项**: 若函数$f$在点$x_0$的某个邻域$U(x_0)$中$n+1$次可微, 且$f^{(n+1)}(x)$在$U(x_0)$中可积, 则有
$$
f(x)=f(x_0)+f'(x_0)(x-x_0)+\cdots+\dfrac{f^{(n)}(x_0)}{n!}(x-x_0)^n+\dfrac{(-1)^n}{n!}\int_{x_0}^{x}(t-x)^n f^{(n+1)}(t)\mathrm{d}t
$$

**广义Cauchy余项**: 设$f(x) \in C^{(n)}([a,b])$, 且在$(a,b)$上$f^{(n+1)}(x)$存在, 则对任意$x_0, x \in [a,b]$以及任意自然数$p$, 存在$\theta \in(0,1)$, 使得
$$
f(x)=f(x_0)+f'(x_0)(x-x_0)+\cdots+\dfrac{f^{(n)}(x_0)}{n!}(x-x_0)^n+\dfrac{f^{(n+1)}\left(x_0+\theta(x-x_0)\right)}{n!p}(1-\theta)^{n+1-p}(x-x_0)^{n+1}
$$
当$p=1$时, 即为Cauchy余项
___
**Proof**: 证明: 设$x_0<x$, 考虑$[x_0,x]$上的函数
	$$
    F(t)=f(x)-\left[f(t)+\dfrac{f'(t)}{1!}(x-t)+\cdots+\dfrac{f^{(n)}(x)}{n!}(x-t)^n\right]
    $$
	易得
	$$
    F(x_0)=R_n(x),\quad F(x)=0,\quad F'(t)=-\dfrac{f^{(n+1)}(t)(x-t)^n}{n! }
    $$
	根据Cauchy中值公式
	$$
    \dfrac{F(x)-F(x_0)}{G(x)-G(x_0)}=\dfrac{F'(\xi)}{G'(\xi)},\quad x_0<\xi<x
    $$
	取$G(t)=(x-t)^p$并记$\xi=x_0+\theta(x-x_0)$, 我们有
	$$
    R_n(x)=\dfrac{G(x)-G(x_0)}{G'(\xi)}\cdot\dfrac{f^{(n+1)}(\xi)}{n!}(x-\xi)^n=\dfrac{f^{(n+1)}\left(x_0+\theta(x-x_0)\right)}{n!p}(1-\theta)^{n+1-p}(x-x_0)^{n+1}
    $$

