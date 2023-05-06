## 1. 可测函数的收敛
### 1.1. 几乎一致收敛
设$\{f_n\}$和$f$都是测度空间$(X, \mathscr{F}, \mu)$上的可测函数, 如果对任意的$\varepsilon>0$, 存在$A\in \mathscr{F}$使得$\mu(A)<\varepsilon$且
$$
\lim\limits_{n\to\infty} \sup\limits_{x\notin A} |f_n(x)-f(x)| = 0
$$
则说可测函数列$\{f_n\}$几乎一致收敛到$f$, 记为$f_n\stackrel{\text { a.u. }}{\longrightarrow}f$

### 1.2. 几乎处处收敛
设$\{f_n\}$和$f$是测度空间$(X, \mathscr{F}, \mu)$上的可测函数. 如果
$$
\mu(\lim\limits_{n\to\infty} f_n\neq f) = 0
$$
则可以说可测函数列$f$几乎处处以$f$为极限. 记为$f_n\stackrel{\text { a.e. }}{\longrightarrow}f$. 如果$f$ a.e. 有限且$f_n\stackrel{\text { a.e. }}{\longrightarrow}f$, 则说$\{f_n\}$几乎处处收敛到$f$. 

考虑$(X, \mathscr{F}, \mathbb{P})$是概率空间的情形, 设$\{\boldsymbol{f}^{(n)}, n\in \mathbb{N}\}$是一列随机向量，$\boldsymbol{f}$是一个随机向量，如果
$$
\mathbb{P}\left(\lim _{n \rightarrow \infty}\left\|\boldsymbol{f}^{(n)}-\boldsymbol{f}\right\|=0\right)=1
$$
则称$\boldsymbol{f}^{(n)}$几乎必然收敛于$\boldsymbol{f}$, 记为$\boldsymbol{f}^{(n)} \stackrel{\text { a.s. }}{\longrightarrow} \boldsymbol{f}$. 这里$\lim\limits _{n \rightarrow \infty}\left\|\boldsymbol{f}^{(n)}-\boldsymbol{f}\right\|=0$代表了事件
$$
\left\{w\ \Big|\ \lim _{n \rightarrow \infty}\left\|\boldsymbol{f}^{(n)}(w)-\boldsymbol{f}(w)\right\|=0\right\} \subset \Omega
$$

### 1.3. 依测度收敛
设$\{f_n\}$和$f$都是测度空间$(X, \mathscr{F}, \mu)$上的可测函数, 如果对每个$\varepsilon>0$, 都有
$$
\lim\limits_{n\to\infty}   \mu(|f_n-f|\ge \varepsilon) = 0 
$$
则说可测函数列$\{f_n\}$依测度收敛到$f$, 记为$f_n\stackrel{\mu}{\longrightarrow}f$

考虑$(X, \mathscr{F}, \mathbb{P})$是概率空间的情形, 设$\{\boldsymbol{f}^{(n)}, n\in \mathbb{N}\}$是一列随机向量，$\boldsymbol{f}$是一个随机向量，如果对于任意的$\varepsilon>0$，有
$$
\lim _{n \rightarrow \infty} \mathbb{P}\left(\left\|\boldsymbol{f}^{(n)}-\boldsymbol{f}\right\| \geq \varepsilon\right)=0
$$
则称$\boldsymbol{f}^{(n)}$依概率收敛于$\boldsymbol{f}$, 记为$\boldsymbol{f}^{(n)} \stackrel{p}{\rightarrow} \boldsymbol{f}$

## 2. 分布函数的收敛
### 2.1. 分布函数的形式化定义
**分布函数**: 设$F$是$\mathbb{R}$上的非降右连续的实值函数, 并且满足
$$
F(-\infty) = 0, \quad F(\infty) = 1
$$
则称$F$为分布函数. 

**随机元的概率分布**: 设$f$是从概率空间$(X, \mathscr{F}, \mathbb{P})$到可测空间$(Y, \mathscr{S})$的随机元. 它在$(Y, \mathscr{S})$上自然导出的概率测度
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
设$\{F_n\}$和$F$都是非降实值函数, 如果$F_n(x)\to F(x)$对$F$的每一个连续点都成立, 则称$\{F_n\}$弱收敛到$F$, 记为$F_n\stackrel{w}{\longrightarrow}F$.

设$\{\boldsymbol{f}^{(n)}\sim F_n, n\in \mathbb{N}\}$是概率空间$(X, \mathscr{F}, \mathbb{P})$上的一列随机向量，$\boldsymbol{f}$是一个随机向量，如果$F_n\stackrel{w}{\longrightarrow}F$,  则称$\boldsymbol{f}^{(n)}$依分布收敛于$\boldsymbol{f}$, 记为$\boldsymbol{f}^{(n)} \stackrel{d}{\rightarrow} \boldsymbol{f}$. 


## 3. 几种收敛模式的等价判定
### 3.1. 几乎一致收敛的等价判定
$f_n\stackrel{\mathrm{a.u.}}{\longrightarrow} f$当且仅当对任意给定的$\varepsilon>0$, 有
$$
\lim\limits_{m\to\infty} \mu\left(\bigcup\limits_{n=m}^{\infty} \{|f_n-f|\ge \varepsilon\}\right) = 0
$$
___
##### Proof:
先证明必要性, 如果$f_n\stackrel{\mathrm{a.u.}}{\longrightarrow} f$, 则对任意给定的$\delta>0$, 一定存在$A\in \mathscr{F}$, 它既满足$\mu(A)<\delta$, 又满足: 对任意给定的$\varepsilon>0$, 存在正整数$m$, 使得
$$
|f_n(x) - f(x)|< \varepsilon, \quad n\ge m,\ \forall x\notin A
$$
也就是说
$$
A^c\subset \bigcap\limits_{n=m}^{\infty} \{|f_n-f|< \varepsilon\}\Longrightarrow A\supset \bigcup\limits_{n=m}^{\infty} \{|f_n-f|\ge  \varepsilon\}
$$
这样, 对于任意给定的$\delta>0$和$\varepsilon>0$, 有
$$
\mu\left(\bigcup\limits_{n=m}^{\infty} \{|f_n-f|\ge  \varepsilon\}\right) \le \mu(A) < \delta
$$
这就得到了
$$
\limsup\limits_{m\to\infty} \mu\left(\bigcup\limits_{n=m}^{\infty} \{|f_n-f|\ge  \varepsilon\}\right) \le \delta
$$
取$\delta\to 0$就得到了
$$
\lim\limits_{m\to\infty} \mu\left(\bigcup\limits_{n=m}^{\infty} \{|f_n-f|\ge \varepsilon\}\right) = 0
$$
再证明充分性, 如果
$$
\lim\limits_{m\to\infty} \mu\left(\bigcup\limits_{n=m}^{\infty} \{|f_n-f|\ge \varepsilon\}\right) = 0
$$
那么任意给定$\delta>0$, 对每个$k=1,2,\cdots$, 都存在正整数$m_k$满足
$$
\mu\left(\bigcup\limits_{n=m_k}^{\infty} \left\{|f_n-f|\ge \dfrac{1}{k}\right\}\right) < \dfrac{\delta}{2^k}
$$
设$A = \bigcup\limits_{k=1}^{\infty} \bigcup\limits_{n=m_k}^{\infty} \left\{|f_n-f|\ge \dfrac{1}{k}\right\}$, 则
$$
\begin{aligned} 
   \mu(A) &= \mu\left(\bigcup\limits_{k=1}^{\infty} \bigcup\limits_{n=m_k}^{\infty} \left\{|f_n-f|\ge \dfrac{1}{k}\right\}\right) \\ 
   & \le \sum\limits_{k=1}^{\infty} \mu\left(\bigcup\limits_{n=m_k}^{\infty} \left\{|f_n-f|\ge \dfrac{1}{k}\right\}\right) \\ 
   & < \delta
\end{aligned}
$$
而且对每个$k=1,2,\cdots$, 当$n\ge m_k$时, $\sup\limits_{x\in A^c}|f_n(x) - f(x)| <\dfrac{1}{k}$, 这表明$f_n\stackrel{\mathrm{a.u.}}{\longrightarrow} f$
#####
___

### 3.2.  几乎处处收敛的等价判定
$f_n\stackrel{\mathrm{a.e.}}{\longrightarrow} f$当且仅当对任意给定的$\varepsilon>0$, 有
$$
\mu\left(\bigcap\limits_{m=1}^{\infty} \bigcup\limits_{n=m}^{\infty} \{|f_n-f|\ge \varepsilon\}\right) = 0
$$
这里, 把$f_n(x) - f(x)$没有定义的那些$x\in X$也计入集合$\{|f_n-f|\ge \varepsilon\}$
___
##### Proof:
我们有
$$
\left\{\lim\limits_{n\to\infty} f_n\neq f\right\}\cup \left\{|f|=\infty\right\} = \bigcup\limits_{k=1}^{\infty} \bigcap\limits_{m=1}^{\infty} \bigcup\limits_{n=m}^{\infty} \left\{|f_n-f|\ge \dfrac{1}{k}\right\}
$$
这就有原命题成立
#####

### 3.3. 几种收敛的关系
1. $f_n\overset{\mathrm{a.u.}}{\longrightarrow} f \Longrightarrow f_n\overset{\mathrm{a.e.}}{\longrightarrow} f$和$f_n\overset{\mu}{\longrightarrow} f$
2. 如果$\mu(X)<\infty$, 则有
   $$
   f_n\overset{\mathrm{a.u.}}{\longrightarrow} f \iff f_n\overset{\mathrm{a.e.}}{\longrightarrow} f\Longrightarrow f_n\overset{\mu}{\longrightarrow} f
   $$
3. $f_n\overset{\mu}{\longrightarrow}f$当且仅当对$\{f_n\}$的任一子列, 存在该子列的一个子子列, 使得该子子列几乎一致收敛于$f$: 
   $$
   f_{n^{\prime}} \overset{\mathrm{a.u.}}{\longrightarrow} f
   $$

___
##### Proof:
1, 2两条显然, 我们只需要证明结论3

首先证明必要性, 若$f_n\overset{\mu}{\longrightarrow} f$, 对每个$k=1,2,\cdots$, 取$n_k$使得$n_k\to\infty$且
$$
\mu\left(|f_{n_k} - f|\ge \dfrac{1}{k}\right) < \dfrac{1}{2^k}
$$
则对于每一个$m=1,2, \cdots$, 有
$$
\mu\left(\bigcup\limits_{k=m}^{\infty} \left\{|f_{n_k} - f|\ge \dfrac{1}{k}\right\}\right) \le \sum\limits_{k=m}^{\infty} \mu\left(|f_{n_k} - f|\ge \dfrac{1}{k}\right) < \sum\limits_{k=m}^{\infty} \dfrac{1}{2^k} = \dfrac{1}{2^{m-1}}
$$
由此可见, 对任给的$\varepsilon>0$, 有
$$
\lim\limits_{m\to\infty} \mu\left(\bigcup\limits_{k=m}^{\infty} \left\{|f_{n_k} - f|\ge \dfrac{1}{k}\right\}\right) = 0
$$
从而$f_{n_k} \overset{\mathrm{a.u.}}{\longrightarrow} f$

再证明充分性, 假设对$\{f_n\}$的任一子列, 存在该子列的一个子子列, 使得该子子列几乎一致收敛于$f$: 
   $$
   f_{n^{\prime}} \overset{\mathrm{a.u.}}{\longrightarrow} f
   $$
   用反证法, 设$f_n\overset{\mu}{\longrightarrow}f$不成立, 即存在$\varepsilon_0>0$和$\delta_0>0$, 使得
   $$
   \mu(|f_{n_k} - f|\ge \varepsilon_0) \ge \delta_0
   $$
   于是, 对$\{f_{n_k}\}$的任意子列, 都没有几乎一致收敛成立. 从而导致矛盾!
#####
___

### 3.4. 依概率收敛与依分布收敛
设$\{f_n, n=1,2,\cdots\}$和$f$是概率空间$(X, \mathscr{F}, \mathbb{P})$上的随机变量, 则
$$
f_n \overset{p}{\longrightarrow} f \Longrightarrow f_n \overset{d}{\longrightarrow} f
$$
____
##### Proof:
用$F$表示$f$的分布函数, 对任意给定的$x\in  \mathbb{R}, \varepsilon>0$和$n=1,2,\cdots$, 有
$$
\begin{aligned} 
\mathbb{P}(f_n\le x) &\le \mathbb{P}(f_n\le x, |f_n - f|<  \varepsilon) +  \mathbb{P}(f_n\le x, |f_n - f|\ge \varepsilon) \\ 
    & \le \mathbb{P}(f \le x + \varepsilon) + \mathbb{P}(|f_n - f|\ge \varepsilon) \\
\end{aligned}
$$
先令$n\to \infty$, 再设$\varepsilon\to 0$, 我们可以得到
$$
\limsup\limits_{n\to\infty} \mathbb{P}(f_n\le x) \le F(x)
$$
另一方面, 我们又有
$$
\begin{aligned} 
\mathbb{P}(f\le x-\varepsilon)  &\le \mathbb{P}(f_n\le x - \varepsilon, |f_n - f|<  \varepsilon) +  \mathbb{P}(f_n\le x - \varepsilon, |f_n - f|\ge \varepsilon) \\ 
    & \le \mathbb{P}(f_n \le x) + \mathbb{P}(|f_n - f|\ge \varepsilon) \\
\end{aligned}
$$
依次设$n\to\infty$和$\varepsilon\to 0$, 可以得到
$$
\liminf\limits_{n\to\infty} \mathbb{P}(f_n\le x) \ge F(x - 0)
$$
于是我们得到了$F_n(x)\to F(x)$对F的每一个连续点$x$成立. 
#####
___

### 3.5. 依分布收敛可以在另一个概率空间表示为几乎必然收敛
设$\{f_n\}$和$f$是概率空间$(X, \mathscr{F}, \mathbb{P})$上的随机变量, 如果$f_n\overset{d}{\longrightarrow} f$, 则存在概率空间$(\widetilde{X}, \widetilde{\mathscr{F}}, \widetilde{\mathbb{P}})$, 在它上面定义着随机变量$\widetilde{f}_n$和$\widetilde{f}$, 使得
$$
\widetilde{f}_n \xlongequal{d} f_n, \quad \widetilde{f}_n \xlongequal{d}f
$$
而且
$$
\widetilde{f}_n \overset{\mathrm{a.s.}}{\longrightarrow} \widetilde{f}
$$
___
##### Proof:
设$\{f_n\}$和$f$的分布函数分别是$\{F_n, n=1,2,\cdots\}$和$F$. 
#####
___