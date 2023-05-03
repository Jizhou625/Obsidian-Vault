## 1. 可测函数的收敛性
### 1.1. 几乎处处成立
设$f$是测度空间$(X, \mathscr{F}, \mu)$上的可测函数
1. 如果$\mu(|f|=\infty) =0$, 则称$f$几乎处处有限
2. 如果存在$M>0$使得$\mu(|f|>M)=0$, 则称$f$几乎处处有界
3. 当$\mu(f\neq 0)=0$时, 就说$f$几乎处处为$0$

将这些说法一般化, 对于测度空间$(X, \mathscr{F}, \mu)$上关于$X$的元素$x$的一个命题, 如果存在$(X, \mathscr{F}, \mu)$中的零测集$N$使得该命题对所有的$x\in N^c$成立, 就说这个命题是几乎处处成立的, 简写为a.e.(almost everywhere). 

### 1.2. 几乎一致收敛
设$\{f_n\}$和$f$都是测度空间$(X, \mathscr{F}, \mu)$上的可测函数, 如果对任意的$\varepsilon>0$, 存在$A\in \mathscr{F}$使得$\mu(A)<\varepsilon$且
$$
\lim\limits_{n\to\infty} \sup\limits_{x\notin A} |f_n(x)-f(x)| = 0
$$
则说可测函数列$\{f_n\}$几乎一致收敛到$f$, 记为$f_n\stackrel{\text { a.u. }}{\longrightarrow}f$

### 1.3. 几乎处处收敛
设$\{f_n\}$和$f$是测度空间$(X, \mathscr{F}, \mu)$上的可测函数. 如果
$$
\mu(\lim\limits_{n\to\infty} f_n\neq f) = 0
$$
则可以说可测函数列$f$几乎处处以$f$为极限. 记为$f_n\stackrel{\text { a.e. }}{\longrightarrow}f$. 如果$f$ a.e. 有限且$f_n\stackrel{\text { a.e. }}{\longrightarrow}f$, 则说$\{f_n\}$几乎处处收敛到$f$. 

考虑$(X, \mathscr{F}, \mathbb{P})$是概率空间的情形, 设$\{\boldsymbol{x}^{(n)}, n\in \mathbb{N}\}$是一列随机向量，$\boldsymbol{x}$是一个随机向量，如果
$$
\mathbb{P}\left(\lim _{n \rightarrow \infty}\left\|\boldsymbol{x}^{(n)}-\boldsymbol{x}\right\|=0\right)=1
$$
则称$\boldsymbol{x}^{(n)}$几乎必然收敛于$\boldsymbol{x}$, 记为$\boldsymbol{x}^{(n)} \stackrel{\text { a.s. }}{\longrightarrow} \boldsymbol{x}$. 这里$\lim\limits _{n \rightarrow \infty}\left\|\boldsymbol{x}^{(n)}-\boldsymbol{x}\right\|=0$代表了事件
$$
\left\{w\ \Big|\ \lim _{n \rightarrow \infty}\left\|\boldsymbol{x}^{(n)}(w)-\boldsymbol{x}(w)\right\|=0\right\} \subset \Omega
$$

### 1.4. 依测度收敛
设$\{f_n\}$和$f$都是测度空间$(X, \mathscr{F}, \mu)$上的可测函数, 如果对每个$\varepsilon>0$, 都有
$$
\lim\limits_{n\to\infty}   \mu(|f_n-f|\ge \varepsilon) = 0 
$$
则说可测函数列$\{f_n\}$依测度收敛到$f$, 记为$f_n\stackrel{\mu}{\longrightarrow}f$

考虑$(X, \mathscr{F}, \mathbb{P})$是概率空间的情形, 设$\{\boldsymbol{x}^{(n)}, n\in \mathbb{N}\}$是一列随机向量，$\boldsymbol{x}$是一个随机向量，如果对于任意的$\varepsilon>0$，有
$$
\lim _{n \rightarrow \infty} \mathbb{P}\left(\left\|\boldsymbol{x}^{(n)}-\boldsymbol{x}\right\| \geq \varepsilon\right)=0
$$
则称$\boldsymbol{x}^{(n)}$依概率收敛于$\boldsymbol{x}$, 记为$\boldsymbol{x}^{(n)} \stackrel{p}{\rightarrow} \boldsymbol{x}$

## 2. 分布函数的收敛
### 2.1. 分布函数的形式化定义
设$F$是$\mathbb{R}$上的非降右连续的实值函数, 并且满足
$$
F(-\infty) = 0, \quad F(\infty) = 1
$$
则称$F$为分布函数. 

设$f$是从概率空间$(X, \mathscr{F}, \mathbb{P})$到可测空间$(Y, \mathscr{S})$的随机元. 它在$(Y, \mathscr{S})$上自然导出的概率测度
$$
\mathbb{P}_{f^{-1}}(B) = \mathbb{P}(f^{-1}(B)), \quad \forall B\in \mathscr{S}
$$
称为随机元$f$的概率分布. 


不难验证, 如果$f$是概率空间$(X, \mathscr{F}, \mathbb{P})$上的随机变量. 对每个$x\in \mathbb{R}$, 设
$$
F(x) = \mathbb{P}(f\le x)
$$
则$F$是一个分布函数, 记为$f\sim F$.  容易看出, $f$的分布函数是它的概率分布在$\mathscr{B}_{\mathbb{R}}$中的$\pi$系$\mathscr{P}_{\mathbb{R}}$上的值. 

### 2.2. 左连续逆
设$F$是$\mathbb{R}$上的非降右连续的实值函数, 对每个$t\in (F(-\infty), F(\infty))$, 令
$$
F^{\gets}(t) = \inf\{x\in \mathbb{R}\ |\ F(x)\ge t\}
$$
我们称$F^{\gets}(t)$为$F$的左连续逆. 

左连续逆有下列的性质
1. $F^{\gets}(t)\in \mathbb{R}, \forall t\in (F(-\infty), F(\infty))$
2. $F^{\gets}(t)$左连续
3. 对任何$t\in (F(-\infty), F(\infty))$和$x\in \mathbb{R}$, 有
   $$
   F^{\gets}(t)\le x \Longleftrightarrow t\le F(x)
   $$
### 2.3. 弱收敛和依分布收敛
设$\{F_n\}$和$F$都是非降实质函数, 如果$F_n(x)\to F(x)$对$F$的每一个连续点都成立, 则称$\{F_n\}$弱收敛到$F$, 记为$F_n\stackrel{w}{\longrightarrow}F$.

设$\{\boldsymbol{x}^{(n)}, n\in \mathbb{N}\}$是一列随机向量，$\boldsymbol{x}$是一个随机向量，如果$F_n\stackrel{w}{\longrightarrow}F$,  则称$\boldsymbol{x}^{(n)}$依分布收敛于$\boldsymbol{x}$, 记为$\boldsymbol{x}^{(n)} \stackrel{d}{\rightarrow} \boldsymbol{x}$

### 2.4. 

## 2. 几种收敛模式的关系
### 2.1. 几乎必然收敛 $\to$ 依概率收敛
设$\boldsymbol{x}^{(n)}, n\in \mathbb{N}$是一列随机向量，$\boldsymbol{x}$是一个随机向量，如果$\boldsymbol{x}^{(n)} \stackrel{\text { a.s. }}{\rightarrow} \boldsymbol{x}$, 则$\boldsymbol{x}^{(n)} \stackrel{p}{\rightarrow} \boldsymbol{x}$
___
##### Proof: 
The event $\left(\boldsymbol{x}^{(n)} \stackrel{\text { as }}{\rightarrow} \boldsymbol{x}\right)^c$ is equivalent to the event $\bigcup\limits_{\varepsilon>0}\left\{\left\|\boldsymbol{x}^{(n)}-\boldsymbol{x}\right\| \geq \varepsilon\right.$ i.o. $\}$. 而
$$
\left\{\left\|\boldsymbol{x}^{(n)}-\boldsymbol{x}\right\| \geq \varepsilon \text { i.o. }\right\}=\left\{\limsup _{n\to\infty}\left\|\boldsymbol{x}^{(n)}-\boldsymbol{x}\right\| \geq \varepsilon\right\}
$$
于是我们有
$$
\begin{aligned}
\lim _{n\to\infty} \mathbb{P}\left(\left\|\boldsymbol{x}^{(n)}-\boldsymbol{x}\right\| \geq \varepsilon\right) & \leq \limsup _{n\to\infty} \mathbb{P}\left(\left\|\boldsymbol{x}^{(n)}-\boldsymbol{x}\right\| \geq \varepsilon\right) \\
& \leq \mathbb{P}\left(\limsup _{n\to\infty}\left\|\boldsymbol{x}^{(n)}-\boldsymbol{x}\right\| \geq \varepsilon\right)=0
\end{aligned}
$$
#####
___