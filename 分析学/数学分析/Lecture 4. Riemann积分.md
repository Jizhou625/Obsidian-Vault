## 1. 一元函数的黎曼积分
### 1.1. Riemann积分的定义
 设$f:\ [a,b]\to \mathbb{R}(\mathbb{C})$是有界闭区间$[a,b]$上的实值函数. 闭区间$[a,b]$上的$n+1$个点
$$
\mathcal{C}:\ a=x_0<x_1<\cdots<x_{n-1}<x_n=b
$$
称为闭区间$[a,b]$的一个分划, 闭区间$[a,b]$因此被分划成了$n$个小区间
$$
[a,b]=\bigcup_{k=1}^n[x_{i-1},x_i]
$$
其中两个不同的小区间之交至多为单点集. 在每个小区间上任选一点$\xi_i\in [x_{i-1},x_i]$, 并构造函数$f$相对于分划$\mathcal{C}$和选点组$\boldsymbol{\xi}=\{\xi_1,\cdots,\xi\}$的Riemann和
$$
\mathcal{R}(f;\mathcal{C},\boldsymbol{\xi})=\sum_{i=1}^nf(\xi_i)(x_i-x_{i-1})
$$
假若当小区间$[x_{i-1},x_i](1\le i\le n)$的长度的最大者趋于零时, 对任意满足条件$\xi_i\in [x_{i-1},x_i]$的选点组$\boldsymbol{\xi}=\{\xi_1,\cdots,\xi_n\}$, Riemann和收敛于某个实(复)数$I\in \mathbb{R}(\mathbb{C})$. 则称$f$在$[a,b]$上Riemann可积, $f$在区间$[a,b]$上的Riemann积分, 记作
$$
I=\int_a^bf(x)\mathrm{d}x
$$
$f(x)$称为上述积分的被积函数, $[a,b]$称为积分区间, $a$称为积分下限, $b$称为积分上限

### 1.2. 达布和
设函数$f$在区间$[a,b]$上有界, $P=\{x_0,x_1,\cdots,x_n\}$为$[a,b]$的一个分划, 对$i=1,2,\cdots,n$, 记
$$
M_i=\sup\{f(x)| x\in [x_{i-1},x_i]\}\quad m_i=\inf\{f(x)| x\in [x_{i-1},x_i]\}
$$
称$w_i=M_i-m_i$为$f$在$[x_{i-1},x_i]$上的振幅,$\quad \displaystyle{\sum_{i=1}^n w_i\Delta x_i}$为$f$的振幅面积.  称$\displaystyle{\sum_{i=1}^n m_i\Delta x_i}$为$f$在$[a,b]$上的达布下和, 记为$\underline{S}_{\Delta'}$, 称$\displaystyle{\sum_{i=1}^n M_i\Delta x_i}$为$f$在$[a,b]$上的达布上和, 记为$\overline{S}_{\Delta'}$

达布和具有下述的性质
1. $\displaystyle{\sum_{i=1}^n m_i\Delta x_i\le \sum_{i=1}^n f(\xi_i)\Delta x_i\le \sum_{i=1}^n M_i\Delta x_i}$
2.  若$\Delta''$为$\Delta'$的加细分划, 则有$\underline{S}_{\Delta'}\le\underline{S}_{\Delta''}\le\overline{S}_{\Delta''}\le\overline{S}_{\Delta'}$
3. 设$\Delta',\Delta''$是$[a,b]$的任意两个分划, 则有$\underline{S}_{\Delta''}\le\overline{S}_{\Delta'}$, 即达布上和大于等于达布下和恒成立
   
### 1.3. 达布定理
设函数$f$在区间$[a,b]$上有界, 对$[a,b]$的一切分划$\Delta $, 作相应的达布上和数集$\{\overline{S}_{\Delta}\}$与达布下和数集$\{\underline{S}_{\Delta}\}$, 且记其下,上确界分别为$$
\inf\limits_{\Delta}\{\overline{S}_{\Delta}\}=\overline{\int_a^b}f(x)\mathrm{d}x,\quad \sup\limits_{\Delta}\{\underline{S}_{\Delta}\}=\underline{\int_a^b}f(x)\mathrm{d}x
$$ 
并分别称它们为$f(x)$在$[a,b]$上的达布上积分和达布下积分, 我们有
$$
\underline{S}_{\Delta}\le \underline{\int_a^b}f(x)\mathrm{d}x\le \overline{\int_a^b}f(x)\mathrm{d}x\le\overline{S}_{\Delta}
$$
并且
$$
\lim\limits_{||\Delta|| \to 0}\overline{S}_{\Delta }=\overline{\int_a^b}f(x)\mathrm{d}x, \quad\lim\limits_{||\Delta|| \to 0}\underline{S}_{\Delta }=\underline{\int_a^b}f(x)\mathrm{d}x
$$
设$f$是有界函数, 则$f \in R([a,b])$当且仅当其上下积分相等, 此时有
$$
\overline{\int_a^b}f(x)\mathrm{d}x=\underline{\int_a^b}f(x)\mathrm{d}x=\int_a^b f(x)\mathrm{d}x
$$


### 1.4. Riemann可积定理
设$f(x)$是$[a,b]$上的有界函数, 则$f\in R([a,b])$的充分必要条件为下面的任意一条
1. 对$\forall \varepsilon>0, \exists\delta >0$, 使得当分划$\Delta$满足$||\Delta||\le \delta$时, 满足$\sum w_i\Delta x_i<\varepsilon$, 也即
	$$
    \lim\limits_{||\Delta|| \to 0}\sum_{i=1}^nw_i\Delta x_i=0
    $$
2. 对$\forall \varepsilon>0$, 存在区间$[a,b]$的一个分划$\Delta$, 使得
	$$
    \sum_{\Delta } w_i\Delta x_i<\varepsilon
    $$
3. 对$\forall \varepsilon>0,\sigma>0$, 存在分划$\Delta: a=x_0<x_1<\cdots<x_n=b$, 其满足$w_i\ge \varepsilon$的子区间的长度总和小于$\sigma$, 也即
	$$
    \sum_{w_i\ge \varepsilon}\Delta x_i<\sigma 
    $$
4. 设$f$在$[a,b]$上有界, 且$f$的所有不连续点可以用总长度任意小的至多可列个开区间覆盖
   
## 2. 特殊函数的积分
### 2.1. 有理函数的积分
有理函数是具有以下形式的函数
$$
f(x)=\dfrac{p(x)}{q(x)}
$$
其中$p(x), q(x)$是两个多项式
$$
p(x)=a_nx^n+a_{n-1}x^{n-1}+\cdots +a_0,\quad q(x)=b_mx^m+b_{m-1}x^{m-1}+\cdots +b_0
$$
每个实系数多项式函数
$$
q(x)=b_mx^m+b_{m-1}x^{m-1}+\cdots +b_0
$$
都有以下的因式分解
$$
q(x)=(x-\alpha_1)^{r_1}\cdots (x-\alpha_k)^{r_k}(x^2+\beta_1x+\gamma_1)^{s_1}\cdots(x^2+\beta_lx+\gamma_l)^{s_l}
$$
其中出现的一次和二次因子都是互不相同的实因子, 而且二次因子都是在实数域的多项式环中不可分解的, 即
$$
\beta_i^2-4\gamma_i<0
$$
给定有理函数$f(x)=\dfrac{p(x)}{q(x)}$, 其中$p(x),q(x)$是两个多项式
$$
p(x)=x^n+a_{n-1}x^{n-1}+\cdots +a_0
$$
$$
q(x)=x^m+b_{m-1}x^{m-1}+\cdots +b_0=(x-\alpha_1)^{r_1}\cdots (x-\alpha_k)^{r_k}(x^2+\beta_1x+\gamma_1)^{s_1}\cdots(x^2+\beta_lx+\gamma_l)^{s_l}
$$
其中$n<m$, 则有理函数可以分解为如下形式(称为有理函数的部分分式分解)
$$
\begin{aligned}
	\dfrac{p(x)}{q(x)}&=\left[\dfrac{a_{11}}{(x-\alpha_1)}+\cdots +\dfrac{a_{1r_1}}{(x-\alpha_1)^{r_1}}\right]+\cdots +\left[\dfrac{a_{k1}}{(x-\alpha_k)}+\cdots +\dfrac{a_{kr_k}}{(x-\alpha_k)^{r_k}}\right]\\
	&+\left[\dfrac{b_{11}x+c_{11}}{(x^2+\beta_1x+\gamma_1)}+\cdots +\dfrac{b_{1s_1}x+c_{1s_1}}{(x^2+\beta_1x+\gamma_1)^{s_1}}\right]+\cdots+\left[\dfrac{b_{l1}x+c_{l1}}{(x^2+\beta_lx+\gamma_l)}+\cdots +\dfrac{b_{ls_l}x+c_{ls_l}}{(x^2+\beta_lx+\gamma_l)^{s_l}}\right]
\end{aligned}
$$

### 2.2.  $\boldsymbol{R\left(x,\sqrt[n]{\dfrac{\alpha x+\beta }{\gamma x+\delta}}\right)}$的积分
需要做替换$t=\sqrt[n]{\dfrac{\alpha x+\beta }{\gamma x+\delta}}$, 就可以把它变成一个有理函数的积分. 事实上, 这时
$$
x(t)=\dfrac{\delta t^n-\beta }{\alpha -\gamma t^n},\quad \mathrm{d}x=\dfrac{n\delta t^{n-1}(\alpha-\gamma t^n)+n(\delta t^n-\beta)\gamma t^{n-1}}{(\alpha-\gamma t^n)^2}\mathrm{d}t
$$
故积分
$$
\int R\left(x,\sqrt[n]{\dfrac{\alpha x+\beta }{\gamma x+\delta}}\right)\mathrm{d}x=\int R(x(t),t)\dfrac{n\delta t^{n-1}(\alpha-\gamma t^n)+n(\delta t^n-\beta)\gamma t^{n-1}}{(\alpha-\gamma t^n)^2}\mathrm{d}t
$$

### 2.3. $\boldsymbol{R(x,\sqrt{ax^2+bx+c})}$的积分
对于形如$R(x,\sqrt{ax^2+bx+c})$的积分, 我们需要对其系数进行分类讨论
1. 设$a>0$, 作替换
	$$
	\sqrt{ax^2+bx+c}=t-\sqrt{a}x
	$$
	这时
	$$
	x=\dfrac{t^2-c}{2\sqrt{a}t+b},\quad \sqrt{ax^2+bx+c}=\dfrac{\sqrt{a}t^2+bt+c\sqrt{a}}{2\sqrt{a}t+b},\quad \mathrm{d}x=2\dfrac{\sqrt{a}t^2+bt+c\sqrt{a}}{(2\sqrt{a}t+b)^2}\mathrm{d}t
	$$
2. 设$c>0$, 作替换
	$$
	\sqrt{ax^2+bx+c}=xt-\sqrt{c}
	$$
	这时
	$$
	x=\dfrac{2\sqrt{c}t-b}{a-t^2},\quad \sqrt{ax^2+bx+c}=\dfrac{\sqrt{c}t^2-bt+a\sqrt{c}}{a-t^2},\quad \mathrm{d}x=\dfrac{\sqrt{c}t^2-bt+a\sqrt{c}}{(a-t^2)^2}\mathrm{d}t
	$$
3. 设二次多项式$ax^2+bx+c$有两个不相等的实根$\lambda$和$\mu$
	$$
	ax^2+bx+c=a(x-\lambda)(x-\mu)
	$$
	作替换
	$$
	\sqrt{ax^2+bx+c}=t(x-\lambda)
	$$
	有
	$$
	x=\dfrac{-a\mu +\lambda t^2}{t^2-a},\quad \sqrt{ax^2+bx+c}=\dfrac{a(\lambda-\mu)t}{t^2-a},\quad \mathrm{d}x=\dfrac{2a(\mu-\lambda)t}{(t^2-a)^2}\mathrm{d}t
	$$

### 2.3. $\boldsymbol{R(\sin x, \cos x)}$的积分
三角函数的积分一般有以下几种换元方法
1. $R(\sin x, \cos x)$型积分总可以用替换$t=\tan \left(\dfrac{x}{2}\right)$把它变成有理函数的积分.
2. 若$R$满足关系式$R(-u,v)=-R(u,v)$, 则有另一个二元有理函数$R_1$, 使得
    $$
    R(u,v)=R_1(u^2,v)u
    $$
    这时, 替换$t=\cos x$就可以把积分化为有理函数的积分
3. 若$R$满足关系式$R(u,-v)=-R(u,v)$, 则有另一个二元有理函数$R_2$, 使得
    $$
    R(u,v)=R_2(u,v^2)v
    $$
	这时, 替换$t=\sin x$就可以把积分化为有理函数的积分
4. 若$R$满足关系式$R(-u,-v)=R(u,v)$, 则有另一个二元有理函数$R_3$, 使得
	$$
	R(u,v)=R_3\left(\dfrac{u}{v}, v^2\right)
	$$
	这时, 作替换$t=\tan x$后, 就可以把积分化为有理函数的积分

## 3. 积分中值定理
### 3.1. 第一中值定理
设$f,g \in R([a,b])$, 且$g$在$[a,b]$上不变号, 则存在$\eta \in f([a,b])=[m,M]$, 使得
$$
\int_a^bf(x)g(x)\mathrm{d}x=\eta\int_a^bg(x)\mathrm{d}x
$$
### 3.2. 第二中值定理
设$f\in R([a,b])$, $g$在$[a,b]$上单调, 则存在$\xi \in [a,b]$, 使得
$$
\int_a^bf(x)g(x)\mathrm{d}x=g(a)\int_a^{\xi} f(x)\mathrm{d}x+g(b)\int_{\xi}^b f(x)\mathrm{d}x
$$
特别地, 如果$g(x)$在$[a,b]$上单调增加且$g(x)\ge 0$, 则存在$\xi \in [a,b]$, 使得
$$
\int_a^bf(x)g(x)\mathrm{d}x=g(b)\int_{\xi}^b f(x)\mathrm{d}x
$$

## 4. Riemann定理
### 4.1. Riemann引理
设$f \in R([a,b])$, 则
$$
\lim\limits_{p \to +\infty}\int^b_a f(x)\sin px\mathrm{d}x=\lim\limits_{p \to +\infty}\int^b_a f(x)\cos px\mathrm{d}x=0
$$

### 4.2. Riemann定理
设$f,g \in R([a,b])$, 其中$g$是以$T$为周期的周期函数, 则
$$
\lim\limits_{p \to +\infty}\int^b_a f(x)g(px)\mathrm{d}x=\dfrac{1}{T}\int_0^Tg(x)\mathrm{d}x\int_a^bf(x)\mathrm{d}x
$$


## 5. 原函数与定积分
### 5.1. 微积分基本定理
设$f$在$[a,b]$上可积, 且在$[a,b]$上有原函数$F(x)$, 则
$$
\int_a^b f(x)\mathrm{d}x=F(b)-F(a)=F(x)\bigg|_a^b
$$

**微积分基本定理的注解**: 
1. 微积分基本定理并不是说可积函数一定有原函数, 而是说如果存在原函数, 可以用来计算定积分的值
   **Example**:
   $$
    f(x)=\left\{\begin{aligned}
                -1,\quad 0\le x\le 1\\
                1,\quad 1<x\le2
            \end{aligned}
            \right.
    $$
    在$[0,2]$上可积,但在$[0,2]$不存在原函数
2. 即使有原函数存在的函数也不一定可积(不包括广义可积)
   **Example**: 在$[-1,1]$上的函数
		$$
        F(x)=\left\{\begin{aligned}
                    &0,\qquad &x=0\\
                    &x^2\sin \dfrac{1}{x^2},\quad &x\neq0
                \end{aligned}
                \right.
        $$
		是函数
		$$
        f(x)=\left\{\begin{aligned}
                    &0,\qquad &x=0\\
                    &-\dfrac{2}{x}\cos\dfrac{1}{x^2}+2x\sin \dfrac{1}{x^2},\quad &x\neq0
                \end{aligned}
                \right.
        $$
		在$[-1,1]$的原函数, 但$f \notin R([-1,1])$

### 5.3. 变限函数积分的导数
若$f \in C([a,b])$, 且有定义在$[c,d]$上的可微函数$\varphi(x), \psi(x)$满足$a\le \varphi(x), \psi(x)\le b$, 则函数$F(x)=\displaystyle{\int_{\varphi(x)}^{\psi(x)}f(t)\mathrm{d}t, x\in [c,d]}$在$[c,d]$上可微, 且$\dfrac{\mathrm{d}F(x)}{\mathrm{d}x}=f[\psi(x)]\psi'(x)-f[\varphi(x)]\varphi'(x)$

**变上限积分注解**:
1. $[a,b]$上可积但不连续的函数也可能有原函数
   **Example**: 
   $$
    f(x)=\left\{\begin{aligned}
                &\ 0,\quad &x=0\\
                &\sin\dfrac{1}{x}, &x\neq0
            \end{aligned}\right.
    $$
    有原函数为
    $$
    F(x)=\int_0^x f(t)\mathrm{d}t
    $$
2. 设$f(x),g(x)$在$[a,b]$上均有原函数, 但乘积$f(x)g(x)$在$[a,b]$上不一定有原函数.
   **Example**: 
    $$
    f(x)=\left\{\begin{aligned}
                &x^2\sin \dfrac{1}{x^3},\quad &x\neq 0\\
                &0,\quad &x=0
            \end{aligned}\right.,\qquad  g(x)=\left\{\begin{aligned}
                &x^2\cos \dfrac{1}{x^3},\quad &x\neq 0\\
                &0,\quad &x=0\end{aligned}\right.
    $$
    不难证明$f(x), g(x)$都有原函数, 但$\Phi (x)=f(x)g'(x)-f'(x)g(x)=\begin{cases}  3, \quad x\neq 0 \\ 0, \quad x=0 \end{cases}$,  可知$\Phi(x)$没有原函数, 也即$f(x)g'(x)$和$f'(x)g(x)$不可能都有原函数
3. 设$f(x)$在$[0,1]$上有原函数, 但是$|f(x)|$在$[0,1]$上不一定有原函数
   **Example**: 
   $$
    f(x)=\left\{\begin{aligned}
            -\dfrac{\pi}{kx^3}\sin\dfrac{\pi}{x^2},\qquad &x\in[x_k,x_{k-1}]\\
            0,\qquad \qquad&x=0
        \end{aligned}\right.,\quad x_n=\dfrac{1}{\sqrt{n}}
    $$
	显然$f(x)$在在$[0,1]$上有原函数
	$$
    F(x)=\left\{\begin{aligned}
            -\dfrac{1}{2k} \left(\cos\dfrac{\pi}{x^2}+1 \right),\qquad &x\in[x_{2k-1},x_{2k+1}]\\
            0,\qquad \qquad&x=0
        \end{aligned}\right.,\quad x_n=\dfrac{1}{\sqrt{n}}
    $$
	如果在闭区间在$[0,1]$上,$\ |f(x)|$有原函数$G(x)$, 则函数$G(x)$必须有界, 矛盾! 因此$|f(x)|$在$[0,1]$上没有原函数. 
   