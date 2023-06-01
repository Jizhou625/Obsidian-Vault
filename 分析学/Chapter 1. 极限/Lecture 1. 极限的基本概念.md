## 1. 极限的基本概念
### 1.1. 极限
设$\{p_n\}$是度量空间$X$中的序列, 如果$\exists p\in X$, 使得对于$\forall \varepsilon>0$. $\exists N>0$, 当$n\ge N$时, 有$d(p_n,p)<\varepsilon$, 则称$\{p_n\}$收敛于$p$, 记作$\lim\limits_{n\to \infty}p_n=p$. 


### 1.2. 重极限
设$E\in \mathbb{R}^n,\ f: E\to \mathbb{R}^m,\ \boldsymbol{x}_0\in E',\ \boldsymbol{y}_0\in \mathbb{R}^m$, 对任意$\varepsilon>0, \exists \delta>0$, 使得
$$
||f(\boldsymbol{x})-\boldsymbol{y}_0||<\varepsilon\quad (0<||\boldsymbol{x}-\boldsymbol{x}_0||<\delta)
$$
则称$f(\boldsymbol{x})$在$\boldsymbol{x}\to \boldsymbol{x}_0$时有极限$\boldsymbol{y}_0$, 记为$\lim\limits_{\boldsymbol{x}\to \boldsymbol{x}_0}f(\boldsymbol{x})=\boldsymbol{y}_0$. 

### 1.3. 累次极限
设$f(x,y)$在$0<|x-x_0|<a,\ 0<|y-y_0|<b$上定义, 若对任意固定值$y$, 当$x\to x_0$时, 函数$f(x,y)$的极限存在, 记作$\lim\limits_{x\to x_0}f(x,y)=\varphi(y)$. 又当$y\to y_0$时, 函数$\varphi(y)$的极限存在, 记作$\lim\limits_{y\to y_0}\varphi(y)=A$. 则称$A$是函数$f(x,y)$的先对$x$后对$y$的累次极限, 记作$\lim\limits_{y\to y_0}\lim\limits_{x\to x_0} f(x,y)=A$

### 1.4. 路径极限
以$f(x,y)$在$(x_0,y_0)$处的情形为例, 设$\begin{cases}  x=\varphi(t) \\ y=\psi(t) \end{cases}$是过$(x_0,y_0)$的任意一条连续曲线, 若有
$$
\lim\limits_{t\to t_0}f(\varphi(t),\psi(t))=A 
$$
则称$f(x,y)$在动点$(x,y)$沿着路径$(\varphi(t),\psi(t))$趋于$(x_0,y_0)$时有极限$A$. 特别地, 在路径为$x=x,\ y=kx$时, 称该极限为方向(向径)极限
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