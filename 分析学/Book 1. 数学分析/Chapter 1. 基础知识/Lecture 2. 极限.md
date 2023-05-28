## 1. 极限的基本概念
### 1.1. 极限的定义
$\{p_n\}$是度量空间$X$中的序列, 如果$\exists p\in X$, 使得对于$\forall \varepsilon>0$. $\exists N>0$, 当$n\ge N$时, 有$d(p_n,p)<\varepsilon$, 则称$\{p_n\}$收敛于$p$, 记作$\lim\limits_{n\to \infty}p_n=p$. 

### 1.2. 序列收敛不等于极限存在
若对任意的$a>0,b>0$, 均有$\lim\limits_{n \to \infty}f(a+bn)=0$, 仍可以不存在$\lim\limits_{n \to \infty}f(x)$
___
##### Example: 
考虑
$$
f(x)=\left\{\begin{aligned}
		&1,\quad x=n\sqrt[n]{2}\\
		&0,\quad x\text{ is other value}
	\end{aligned}\right.
$$
对于任意的$a, b$
$$
\begin{cases}
a+bn=m\sqrt[m]{2} \\ 
a+bk=l\sqrt[l]{2}
\end{cases}, \quad n\ne k,\ m\neq l
$$
解上面的方程组可以得到
$$
a=\dfrac{nl\sqrt[l]{2}-mk\sqrt[m]{2}}{n-k},\quad b=\dfrac{m\sqrt[m]{2}-l\sqrt[l]{2}}{n-k}$$
容易证明, 对$\forall q\notin \{m,l\}$, 不存在$p \in \mathbb{N}$, 使得$a+bp=q\sqrt[q]{2}$, 这意味着$\lim\limits_{n \to \infty}f(a+bn)=0$, 但$\lim\limits_{n \to \infty}f(x)$不存在.
#####
___

### 1.3. Stolz定理: 
设$f(x), g(x)$在$[a,\infty)$上有定义, $T$是一个正的常数,满足
1. $f(x),\ g(x)$在任意区间$[a,b]$上有界
2. 对任意$x>a$, 有$g(x+T)>g(x)$, 且当$x \to \infty$时, $g(x) \to \infty$. 

若存在极限$\lim\limits_{n \to \infty}\dfrac{f(x+T)-f(x)}{g(x+T)-g(x)}=A$, 则$\lim\limits_{n \to \infty}\dfrac{f(x)}{g(x)}=A$

### Toeplitz定理
设$n,k\in \mathbb{N},\ t_{nk}\ge 0$且有$\sum\limits_{k=1}^n t_{nk}=1,\ \lim\limits_{n\to \infty}t_{nk}=0$. 如果$\lim\limits_{n\to +\infty} a_n=a$, 则有$\lim\limits_{n\to +\infty}\sum\limits_{k=1}^{n}t_{nk}a_k=a$
___
##### Proof: 
$$
\begin{aligned}
		\left|\sum_{k=1}^nt_{nk}a_n-a\right|&=\left|\sum_{k=1}^nt_{nk}(a_k-a)\right| \\ 
        &\le t_{n1}|a_1-a|+\cdots+t_{nN_1}|a_{N_1}-a|+t_{n, N_1+1}|a_{N_1+1}-a|+\cdots+t_{nn}|a_{n}-a|\\&\le M(t_{n1}+\cdots+t_{nN_1})+\dfrac{\varepsilon}{2}(t_{n, N_1+1}+\cdots+t_{nn})\\
		&\le MN_1\cdot\dfrac{\varepsilon}{2N_1M}+\dfrac{\varepsilon}{2}\\ 
        &=\varepsilon
\end{aligned}
$$
#####
___

### 1.4. Heine归结原理
设$a,A\in \mathbb{R}$, 极限$\lim\limits_{x\to a}f(x)=A$存在的充分必要条件是: 对满足条件$x_n\neq a,\ \lim\limits_{n\to +\infty}x_n=a$的每个数列$\{x_n\}$, 都有$\lim\limits_{n\to +\infty}f(x_n)=A$

## 2. 自然对数的底$e$和Euler常数$\gamma$
### 2.1. 自然对数的底$e$
我们用级数形式
$$
e = 1+1+\dfrac{1}{2!}+\cdots+\dfrac{1}{n!} + \cdots
$$
来定义自然对数的底$e$. 用$e_n$表示
$$
e_n = 1+1+\dfrac{1}{2!}+\cdots+\dfrac{1}{n!}
$$
则其误差$\varepsilon_n = e - e_n$满足不等式
$$
\dfrac{1}{(n+1)!}<\varepsilon_n<\dfrac{1}{n!n}
$$

### 2.2. Euler常数$\gamma$
引入数列$c_n=1+\dfrac{1}{2}+\cdots+\dfrac{1}{n}-\ln n$. 显然数列$\{c_n\}$严格单调递减且下有界, 因此$\{c_n\}$是收敛的, 我们记$\gamma=\lim\limits_{n\to \infty}\left(1+\dfrac{1}{2}+\cdots+\dfrac{1}{n}-n\right)\approx 0.5772$, 称$\gamma$为Euler常数.

### 2.3. Wallis公式
$$
\lim\limits_{n\to +\infty}\left(\dfrac{(2n)!!}{(2n-1)!!}\right)^2\dfrac{1}{2n+1}=\dfrac{\pi}{2}
$$
___
##### Proof:
证明: 令$I_n=\displaystyle{\int_{0}^{\frac{\pi}{2}} \sin^nx \mathrm{d}x}$. 由$I_{2k+1}<I_{2k}<I_{2k-1}$可得, $\dfrac{2k!!}{(2k+1)!!}<\dfrac{(2k-1)!!}{2k!!}\dfrac{\pi}{2}<\dfrac{(2k-2)!!}{(2k-1)!!}$. 这就得到了结论. 
#####
___

### 2.4. Stirling公式
$$
\lim\limits_{n\to +\infty}\dfrac{n!}{\sqrt{2\pi n}\left(\dfrac{n}{e}\right)^n}=1
$$
事实上, 我们有
$$
n!=\sqrt{2\pi n}\left(\dfrac{n}{e}\right)^ne^{\theta_n}, \quad \theta_n<\dfrac{1}{n}
$$
___
##### Proof:
考虑$a_n=\dfrac{n!}{n^{n+\frac{1}{2}}e^{-n}}$, 不难证明$\{a_n\}$单调递减且$a_n>1$; 故$\{a_n\}$极限存在. 记$a_n$的极限为$A$, 由Wallis公式可得,  $\ \dfrac{\pi}{2}=\lim\limits_{n\to +\infty}\left(\dfrac{(2n)!!}{(2n-1)!!}\right)^2\dfrac{1}{2n+1}=\lim\limits_{n\to +\infty}\dfrac{2^{4n}\left[\dfrac{(n!)^2}{(2n)!}\right]^2}{2n+1}=\lim\limits_{n\to +\infty}\dfrac{2^{4n}A^22^{-4n-1}n}{2n+1}=\dfrac{A^2}{4}$, 故原命题成立.
#####
___

## 3. 实数系基本定理
### 3.1. 实数系基本定理
1. **上(下)确界原理**: 非空有上(下)界的实数集必有上(下)确界
2. **单调有界定理**: 单调有界数列必有极限
3. **闭区间套定理**: 对于任何闭区间套, 必存在属于所有闭区间套的公共点, 若区间的长度趋于$0$, 则该点是唯一的公共点
4. **有限开覆盖定理**: 闭区间上的任意一个开覆盖, 必可从中取出有限个开区间来覆盖这个闭区间
5. **聚点定理**: 每个无穷有界集至少有一个极限点
6. **致密性定理**: 有界数列必有收敛子列
7. **完备性定理**: 数列收敛的充要条件是其为柯西列

### 3.2. 有限覆盖定理的加强(Lebesgue数定理)
设$\mathscr{F}$是有界闭区间$[a,b]$上的一个开覆盖, 则必存在数$\lambda=\lambda({\mathscr{F}})>0$, 使得对$\forall A\subset[a,b]$满足$d(A)=\sup \{\rho(x',x'' | x',x''\in A)\}<\lambda=\lambda(\mathscr{F})$, 都存在$I\in \mathscr{F}$使得$A\subset I$, 我们称$\lambda=\lambda(\mathscr{F})$为$\mathscr{F}$的一个Lebesgue数
___
##### Proof:
用反证法, 假设结论不成立, 则对$\forall n\in N$, $\exists A_n\subset [a,b], d(A_n)<\dfrac{1}{n}$, 使得对$\forall I\in \mathscr{F}$都有$A_n\notin I$. 取$a_n$为$A_n$区间中的任意一点, 由闭区间的紧性可得存在子列$\{a_{n_k}\}$收敛于$a_0\in [a,b]$. 由于$\mathscr{F}$是开覆盖, 故存在$I_0\in\mathscr{F}$使得$a_0\in I_0$. 因此必然存在$A_n$被$I_0$完全覆盖. 
#####
___

### 3.3. 压缩映射原理
设函数$f$在区间$[a,b]$上定义, $f([a,b])\subset[a,b]$. 存在一个常数$k,\ 0<k<1$, 使得对一切$x,y \in [a,b]$成立不等式$|f(x)-f(y)|\le k|x-y|$, 则称$f$是$[a,b]$上的一个压缩映射,称常数$k$为压缩常数,  若$f$是$[a,b]$上的一个压缩映射,则
1. $f$在$[a,b]$中存在唯一的不动点$\varepsilon=f(\varepsilon)$
2. 由任何初始值$a_0\in[a,b]$和递推公式$a_{n+1}=f(a_n),\ n \in \mathbb{N}^+$, 生成的数列$\{a_n\}$一定收敛于$\varepsilon$
3. 成立估计式$|a_n-\varepsilon|\le \dfrac{k}{1-k}|a_n-a_{n-1}|$和$|a_n-\varepsilon|\le \dfrac{k^n}{1-k}|a_1-a_0|$

## 4. 上下极限
### 4.1. 上下极限的性质
1.  $\varlimsup\limits_{n \to \infty} (x_n+y_n)\le \varlimsup\limits_{n \to \infty}x_n+\varlimsup\limits_{n \to \infty}y_n$, $\varliminf\limits_{n \to \infty} (x_n+y_n)\ge \varliminf\limits_{n \to \infty}x_n+\varliminf\limits_{n \to \infty}y_n$
2.  $\varliminf\limits_{n \to \infty} (x_n+y_n)\le \varliminf\limits_{n \to \infty} x_n+\varlimsup\limits_{n \to \infty} y_n\le \varlimsup\limits_{n \to \infty} (x_n+y_n)$ ,该不等式在中间的和式有意义时成立
3.  若数列$\{y_n\}$广义收敛, 则成立
$$
\begin{aligned}
\varliminf\limits_{n \to \infty} (x_n+y_n)&=\varliminf\limits_{n \to \infty}x_n+\varliminf\limits_{n \to \infty} y_n \\ 
\varlimsup\limits_{n \to \infty} (x_n+y_n)&= \varlimsup\limits_{n \to \infty}x_n+\varlimsup\limits_{n \to \infty}y_n
\end{aligned}
$$


### 4.2. 半连续
设$f(x)$在$x_0$的邻域$U(x_0)$上定义
1. 若$\varlimsup\limits_{x \to x_0}f(x)\le f(x_0)$, 则称$f(x)$在$x=x_0$处是上半连续的
2. 若$\varliminf\limits_{x \to x_0}f(x)\ge f(x_0)$, 则称$f(x)$在$x=x_0$处是下半连续的

## 5. 多元函数的极限
### 5.1. 重极限
设$E\in \mathbb{R}^n,\ f: E\to \mathbb{R}^m,\ \boldsymbol{x}_0\in E',\ \boldsymbol{y}_0\in \mathbb{R}^m$, 对任意$\varepsilon>0, \exists \delta>0$, 使得||$f(\boldsymbol{x})-\boldsymbol{y}_0||<\varepsilon\quad (0<||\boldsymbol{x}-\boldsymbol{x}_0||<\delta)$, 则称$f(\boldsymbol{x})$在$\boldsymbol{x}\to \boldsymbol{x}_0$时有极限$\boldsymbol{y}_0$, 记为$\lim\limits_{\boldsymbol{x}\to \boldsymbol{x}_0}f(\boldsymbol{x})=\boldsymbol{y}_0$
### 5.2. 累次极限
设$f(x,y)$在$0<|x-x_0|<a,\ 0<|y-y_0|<b$上定义, 若对任意固定值$y$, 当$x\to x_0$时, 函数$f(x,y)$的极限存在, 记作$\lim\limits_{x\to x_0}f(x,y)=\varphi(y)$. 又当$y\to y_0$时, 函数$\varphi(y)$的极限存在, 记作$\lim\limits_{y\to y_0}\varphi(y)=A$. 则称$A$是函数$f(x,y)$的先对$x$后对$y$的累次极限, 记作$\lim\limits_{y\to y_0}\lim\limits_{x\to x_0} f(x,y)=A$

### 5.3. 路径极限
以$f(x,y)$在$(x_0,y_0)$处的情形为例, 设$\begin{cases}  x=\varphi(t) \\ y=\psi(t) \end{cases}$是过$(x_0,y_0)$的任意一条连续曲线, 若有
$$
\lim\limits_{t\to t_0}f(\varphi(t),\psi(t))=A 
$$
则称$f(x,y)$在动点$(x,y)$沿着路径$(\varphi(t),\psi(t))$趋于$(x_0,y_0)$时有极限$A$. 特别地, 在路径为$x=x,\ y=kx$时, 称该极限为方向(向径)极限