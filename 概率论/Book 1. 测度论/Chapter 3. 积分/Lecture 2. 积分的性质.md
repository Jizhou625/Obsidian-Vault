## 1. 一般可测函数积分的性质
### 1.1. 积分存在的性质
设$f$是测度空间$(X, \mathscr{F}, \mu)$上的可测函数, 如果$f$的积分存在, 则
1. $\left|\displaystyle{\int_X}f\mathrm{d}\mu\right|\le \displaystyle{\int_X}|f|\mathrm{d}\mu$
2. 对任意的$A\in \mathscr{F}$且$\mu(A)=0$, 有
   $$
   \displaystyle{\int_A}f\mathrm{d}\mu = 0
   $$
3. 设$g$也是测度空间$(X, \mathscr{F}, \mu)$上的可测函数, 如果$g$的积分存在, 且$f\ge g$ a.e.
   $$
   \int_X f\mathrm{d}\mu \ge \int_X g\mathrm{d}\mu
   $$
4. 设$g$也是测度空间$(X, \mathscr{F}, \mu)$上的可测函数, 如果$f=g$ a.e., 则只要其中任何一个积分存在, 则另一个积分也存在并且两个积分值相等. 
___
##### Proof: 
1. 我们可以得到
   $$
   \max\left\{\int_X f^+\mathrm{d}\mu, \int_X f^-\mathrm{d}\mu\right\} \le \int_X |f|\mathrm{d}\mu
   $$
   因此
   $$
   \left|\int_X f \mathrm{~d} \mu\right|=\left|\int_X f^{+} \mathrm{d} \mu-\int_X f^{-} \mathrm{d} \mu\right| \leqslant \int_X|f| \mathrm{d} \mu .
   $$
2. 如果$f$是非负简单函数, 可以被表示为$f=\sum\limits_{i=1}^{n} a_i\mathbb{I}_{A_i}$, 其中$\{A_i\in \mathscr{F}\}$是$(X, \mathscr{F}, \mu)$的有限可测分割. 
   $$
   \begin{aligned} 
   \int_A f\mathrm{d}\mu & = \int_X f\mathbb{I}_A\mathrm{d}\mu \\
   & = \int_X \left(\sum\limits_{i=1}^{n} a_i\mathbb{I}_{A_i\cap A}\right)\mathrm{d}\mu \\ 
   & = \sum\limits_{i=1}^{n} a_i\mu(A_i\cap A) \\
   & \le \mu(A) \sum\limits_{i=1}^{n} a_i \\
   & = 0
   \end{aligned}
   $$
   根据典型方法, 我们可以得到这个结论对非负可测函数和一般可测函数成立. 
3. 先考虑$f, g\ge 0$的情况, 记$A = \{f< g\}$, 则
   $$
   \begin{aligned}
   \int_X f \mathrm{~d} \mu & =\int_X f \mathbb{I}_A \mathrm{~d} \mu+\int_X f  \mathbb{I}_{A^c} \mathrm{~d} \mu=\int_X f  \mathbb{I}_{A^c} \mathrm{~d} \mu \\
   & \geqslant \int_X g  \mathbb{I}_{A^c} \mathrm{~d} \mu=\int_X g  \mathbb{I}_A \mathrm{~d} \mu+\int_X g  \mathbb{I}_{A^c} \mathrm{~d} \mu \\
   & =\int_X g \mathrm{~d} \mu,
   \end{aligned}
   $$
   在讨论一般情况, 根据$f\ge g$ a.e., 容易得到$f^+\ge g^+$ a.e. 和$f^-\le g^-$ a.e., 因此
   $$
   \int_x f^{+} \mathrm{d} \mu \leqslant \int_x g^{+} \mathrm{d} \mu ; \quad \int_x f^{-} \mathrm{d} \mu \geqslant \int_x g^{-} \mathrm{d} \mu .
   $$
   合在一起可以得到对于一般的$f\ge g$ a.e., 有
   $$
   \int_X f\mathrm{d}\mu \ge \int_X g\mathrm{d}\mu
   $$
4. 根据$f=g$ a.e., 我们可以得到$f\ge g$ a.e. 和$f\le g$ a.e., 因此可以得到结论成立. 
#####
___

### 1.2. 可积的性质
设$f$是测度空间$(X, \mathscr{F}, \mu)$上的可测函数
1. $f$可积当且仅当$|f|$可积
2. 如果$f$可积, 则$|f|<\infty$ a.e.
   
___
##### Proof:
1. 因为
   $$
   \max\left\{\int_X f^+\mathrm{d}\mu, \int_X f^-\mathrm{d}\mu\right\} \le \int_X |f|\mathrm{d}\mu
   $$
   因此当$|f|$可积时, $f$可积. 而当$f$可积时, 有
   $$
   \max \left\{\int_X f^{+} d \mu, \int_X f^{-} \mathrm{d} \mu\right\}<\infty
   $$
   于是我们有
   $$
   \int_X|f| \mathrm{d} \mu=\int_X f^{+} \mathrm{d} \mu+\int_X f^{-} \mathrm{d} \mu<\infty
   $$
2. 由于$f$可积当且仅当$|f|$可积, 因此我们可以不妨设$f\ge 0$可积, 下面用反证法, 如果$\mu(f = \infty)>0$, 则我们可以得到
   $$
   \int_X f \mathrm{~d} \mu \geqslant \int_X f \mathbb{I}_{\left\{f = \infty\right\}} \mathrm{d} \mu \geqslant n \mu(f=\infty) 
   $$
   这意味着
   $$
   \int_X f \mathrm{~d} \mu = \infty
   $$
   矛盾!
#####
___

### 1.3. 积分的线性性质
设$f$和$g$是测度空间$(X, \mathscr{F}, \mu)$上积分存在的可测函数, 则
1. 对任何$a\in \mathbb{R}$, $af$的积分存在并且
   $$
   \int_X(af)\mathrm{d}\mu = a\int_X f\mathrm{d}\mu
   $$
2. 如果$\displaystyle{\int_X}f\mathrm{d}\mu + \displaystyle{\int_X}g\mathrm{d}\mu$有意义, 则$f+g$ a.e. 有定义, 其积分存在并且
   $$
   \int_X(f+g)\mathrm{d}\mu = \int_X f\mathrm{d}\mu + \int_X g\mathrm{d}\mu
   $$
___
##### Proof:
结论1显然成立, 我们只需要证明结论2. 证明分3步进行
1. 如果$f, g\ge 0$ a.e., $\min\left\{\displaystyle{\int_X}f\mathrm{d}\mu, \displaystyle{\int_X}g\mathrm{d}\mu\right\}<\infty$且$f-g$ a.e. 有定义, 则$f-g$的积分存在并且
   $$
   \int_X (f-g)\mathrm{d}\mu  = \int_X f\mathrm{d}\mu - \int_X g\mathrm{d}\mu
   $$
   这是因为
   $$
   \begin{aligned} 
   &f - g \le f \text{ a.e.} \Longrightarrow (f - g)^+ \le f \text{ a.e.} \\ 
   & f - g \ge -g \text{ a.e.} \Longrightarrow (f - g)^- \le g \text{ a.e.}    
   \end{aligned}
   $$
   于是我们得到
   $$
   \min \left\{\int_x(f-g)^{+} \mathrm{d} \mu, \int_x(f-g)^{-} \mathrm{d} \mu\right\} 
    \leqslant \min \left\{\int_x f \mathrm{~d} \mu, \int_X g \mathrm{~d} \mu\right\}<\infty
   $$
   因此$f-g$的积分存在. 
   $$
   f-g = (f-g)^+ - (f-g)^- \text{ a.e.}
   $$
   则
   $$
   f+(f-g)^{-}=g+(f-g)^{+} \text {  a.e.}
   $$
   于是我们有
   $$
   \int_X f \mathrm{~d} \mu+\int_X(f-g)^{-} \mathrm{d} \mu=\int_X g \mathrm{~d} \mu+\int_X(f-g)^{+} \mathrm{d} \mu 
   $$
   这就得到了
   $$
   \begin{aligned}
   \int_X(f-g) \mathrm{d} \mu & =\int_X(f-g)^{+} \mathrm{d} \mu-\int_X(f-g)^{-} \mathrm{d} \mu \\
   & =\int_X f \mathrm{~d} \mu-\int_X g \mathrm{~d} \mu 
   \end{aligned}
   $$
2. 如果$\displaystyle{\int_X}f\mathrm{d}\mu + \displaystyle{\int_X}g\mathrm{d}\mu$有意义, 则$\left(f^{+}+g^{+}\right)-\left(f^{-}+g^{-}\right)$a.e. 有意义, 而且
   $$
   \min \left\{\int_X\left(f^{+}+g^{+}\right) \mathrm{d} \mu, \int_X\left(f^{-}+g^{-}\right) \mathrm{d} \mu\right\}<\infty
   $$
   我们只需要证明
   $$
   \begin{aligned}
   & \int_X\left(f^{+}+g^{+}\right) \mathrm{d} \mu=\infty \Longrightarrow \int_X\left(f^{-}+g^{-}\right) \mathrm{d} \mu<\infty \\
   & \int_X\left(f^{-}+g^{-}\right) \mathrm{d} \mu=\infty \Longrightarrow \int_X\left(f^{+}+g^{+}\right) \mathrm{d} \mu<\infty
   \end{aligned}
   $$
   根据对称性, 我们只需要证明第一个结论. 事实上, 如果$\displaystyle{\int_X}(f^++g^+)\mathrm{d}\mu =\infty$, 于是我们知道$\displaystyle{\int_X}f^+\mathrm{d}\mu =\infty$和$\displaystyle{\int_X}g^+\mathrm{d}\mu =\infty$之一成立. 不妨设$\displaystyle{\int_X}f^+\mathrm{d}\mu =\infty$, 因为$f$的积分存在, 故必有$\displaystyle{\int_X}f^-\mathrm{d}\mu <\infty$. 此外, 因为$\displaystyle{\int_X}f\mathrm{d}\mu + \displaystyle{\int_X}g\mathrm{d}\mu$有意义, 故$\displaystyle{\int_X}g^{-}\mathrm{d}\mu <\infty$. 从而, 我们有$\displaystyle{\int_X}(f^{-}+g^{-})\mathrm{d}\mu <\infty$
3. 如果$\displaystyle{\int_X}f\mathrm{d}\mu + \displaystyle{\int_X}g\mathrm{d}\mu$有意义, 则$f+g$ a.e. 有定义, 其积分存在并且
   $$
   \int_X(f+g)\mathrm{d}\mu = \int_X f\mathrm{d}\mu + \int_X g\mathrm{d}\mu
   $$
   这是因为
   $$
   \begin{aligned}
   & (f+g)^{+} \leqslant f^{+}+g^{+} \text { a.e. } \\
   & (f+g)^{-} \leqslant f^{-}+g^{-} \text { a.e. }
   \end{aligned}
   $$
   根据2中的结果, 我们知道$f+g$ a.e. 有意义并且$f+g$的积分存在, 于是
   $$
   \begin{aligned} 
      \int_X(f+g)\mathrm{d}\mu &= \int_X (f^+ - f^- + g^+ - g^-)\mathrm{d}\mu \\ 
      &= \int_X ((f^+ +  g^+) -(f^- + g^-))\mathrm{d}\mu \\ 
      & = \int_X\left(f^{+}+g^{+}\right) \mathrm{d} \mu-\int_X\left(f^{-}+g^{-}\right) \mathrm{d} \mu \\ 
      & =\left(\int_X f^{+} \mathrm{d} \mu+\int_X g^{+} \mathrm{d} \mu\right)-\left(\int_X f^{-} \mathrm{d} \mu+\int_X g^{-} \mathrm{d} \mu\right) \\ 
      & = \int_X f\mathrm{d}\mu + \int_X g\mathrm{d}\mu 
   \end{aligned}
   $$
#####
___
### 1.4. 积分值相等与几乎处处相等
设$f$和$g$是测度空间$(X, \mathscr{F}, \mu)$上的可积函数
1. 如果$\displaystyle{\int_A}f\mathrm{d}\mu \ge \displaystyle{\int_A}g\mathrm{d}\mu$对每个$A\in \mathscr{F}$成立, 则$f\ge g$ a.e.
2. 如果$\displaystyle{\int_A}f\mathrm{d}\mu = \displaystyle{\int_A}g\mathrm{d}\mu$对每个$A\in \mathscr{F}$成立, 则$f =  g$ a.e.
___
##### Proof:
显然1可以推出2, 因此我们只需要证明结论1. 设$B=\{f<g\}$. 则我们有
$$
\int_B (g-f)\mathrm{d}\mu = \int_X (g-f)\mathbb{I}_B\mathrm{d}\mu \ge 0
$$
根据条件$\displaystyle{\int_A}f\mathrm{d}\mu \ge \displaystyle{\int_A}g\mathrm{d}\mu, \forall A\in\mathscr{F}$. 根据积分的线性性, 我们有
$$
\int_B(g-f) \mathrm{d} \mu=\int_B g \mathrm{~d} \mu-\int_B f \mathrm{~d} \mu \leqslant 0
$$
于是我们有
$$
\int_X(g-f) \mathbb{I}_B \mathrm{~d} \mu=\int_B(g-f) \mathrm{d} \mu=0 .
$$
这意味着$(g-f)\mathbb{I}_b=0$ a.e., 但因为在$B$上$g>f$, 因此我们有$\mathbb{I}_B= 0$ a.e. 这就意味着
$$
\mu(f<g) = \mu(B) = 0
$$ 
#####
___

### 1.5. 积分的绝对连续性
如果$f$可积, 则对任何$\varepsilon>0$, 存在$\delta>0$, 使得对任意满足$\mu(A)<\delta$的$A\in \mathscr{F}$, 有
$$
\int_A |f|\mathrm{d}\mu < \varepsilon
$$
___
##### Proof: 
首先, 根据[1.2. 可积的性质](#1.2.%20可积的性质), $f$可积意味着$|f|$可积. 由于$|f|$是非负可测函数, 因此可以取非负简单函数
$$
g_n \uparrow |f| \Longrightarrow\lim\limits_{n\to\infty} \int_X g_n\mathrm{d}\mu = \int_X |f|\mathrm{d}\mu 
$$
对任意给定的$\varepsilon>0$, 存在正整数$N$使得
$$
\int_X|f| \mathrm{d} \mu-\int_X g_N \mathrm{~d} \mu<\frac{\varepsilon}{2} 
$$
设$M = \max\limits_{x\in X}g_N(x)$, 则
$$
\int_A|f| \mathrm{d} \mu<\frac{\varepsilon}{2}+\int_A g_N \mathrm{~d} \mu \leqslant \frac{\varepsilon}{2}+M \mu(A)
$$
于是我们只要取$\delta = \dfrac{\varepsilon}{2M}$, 即可得到结论. 
#####
___

## 2. 可测函数列极限的积分性质
### 2.1. 单调收敛定理(Levi定理)
设$\{f_n\}$和$f$均为a.e.非负的可测函数. 如果$f_n \uparrow f$, 则
$$
\int_X f_n\mathrm{d}\mu \uparrow \int_X f\mathrm{d}\mu
$$
___
##### Proof:
不妨设$\{f_n\}$和$f$是处处非负的可测函数并且对每个$x\in X$有
$$
f_n(x) \uparrow f(x)
$$
对每个$n=1,2,\cdots$, 作非负函数列$\{f_{n, k}, k=1,2,\cdots\}$使得当$k\to\infty$时$f_{n, k}\uparrow f_n$. 再设$g_k = \max\limits_{1\le n\le k}f_{n,k}$, 则
1. 对每个$k$, 都有$g_k$都是非负简单函数
2. 对每个$k$, 都有
   $$
   g_k = \max_{1\le n\le k}f_{n,k} \le \max_{1\le n\le k}f_{n,k+1} \le \max_{1\le n\le k+1}f_{n,k+1} = g_{k+1}
   $$
   这表明$g_k\uparrow$
3. 由于$g_k =\max\limits_{1\le n\le k}f_{n, k} \le \max\limits_{1\le n\le k}f_n = f_k$, 因此
   $$
   \int_X g_k\mathrm{d}\mu \le \int_X f_k\mathrm{d}\mu \le \int_X f\mathrm{d}\mu
   $$
   $$
   \lim\limits_{k\to\infty} g_k \le \lim\limits_{k\to\infty} f_k = f 
   $$
4. 由于对每个$n=1,2,\cdots, k$都有$g_k=\max\limits_{1\le n\le k}f_{n, k}\ge f_{n, k}$, 我们有
   $$
   \lim\limits_{k\to\infty} g_k\ge \lim\limits_{k\to\infty} f_{n, k} = f_n , \quad n=1,2,\cdots
   $$
   则
   $$
   \lim\limits_{k\to\infty}g_k \ge \lim\limits_{n\to\infty}  f_n = f
   $$

结合2,3,4我们得到了$g_k\uparrow f$. 于是我们有
$$
\int_X g_k \mathrm{d}\mu \uparrow  \int_X f\mathrm{d}\mu
$$
结合
$$
g_k = \max_{1\le n\le k}f_{n,k} \le \max_{1\le n\le k}f_{n,k+1} \le \max_{1\le n\le k+1}f_{n,k+1} = g_{k+1}
$$
这就得到了
$$
\int_X f_n \mathrm{d}\mu \uparrow  \int_X f\mathrm{d}\mu
$$
#####
___

### 2.2. Fatou引理
对任意a.e.非负可测函数的序列$\{f_n\}$, 有
$$
\int_X (\liminf\limits_{n\to\infty} f_n)\mathrm{d}\mu \le \liminf\limits_{n\to\infty} \int_X f_n\mathrm{d}\mu
$$
___
##### Proof:
设$g_k =\inf\limits_{n\ge k} f_n$, 则我们有$g_k\uparrow \liminf\limits_{n\to\infty} f_n$, 因此根据[2.1. 单调收敛定理(Levi定理)](#2.1.%20单调收敛定理(Levi定理)), 我们有
$$
\int_X(\liminf_{n\to\infty}f_n)\mathrm{d}\mu = \lim\limits_{k\to\infty}\int_X g_k\mathrm{d}\mu = \lim\limits_{k\to\infty} \int_X \left(\inf\limits_{n\ge k}f_n\right) \mathrm{d}\mu \le \liminf\limits_{n\to\infty} \int_X f_n\mathrm{d}\mu
$$
#####
___

### 2.3. Lebesgue控制收敛定理
设$\{f_n\}$和$f$均为可测函数, 且存在可积函数$g$, 使得$|f_n|\le g$ a.e.,  则$f_n\overset{\text{a.e.}}{\longrightarrow} f$或$f_n\overset{\mu}{\longrightarrow} f$意味着
$$
\lim\limits_{n\to\infty} \int_X f_n\mathrm{d}\mu  = \int_X f\mathrm{d}\mu
$$
___
##### Proof: 
先考虑$f_n \overset{\mathrm{a.e.}}{\longrightarrow} f$的情况, 我们有
$$
\begin{aligned} 
   \int_X f\mathrm{d}\mu & = \int_X \left(\lim\limits_{n\to\infty} f_n\right)\mathrm{d}\mu \\ 
   & \le \liminf_{n\to\infty} \int_X f_n\mathrm{d}\mu \\ 
   & \le  \limsup_{n\to\infty} \int_X f_n\mathrm{d}\mu \\ 
   & \le  \int_X \left(\lim\limits_{n\to\infty} f_n\right)\mathrm{d}\mu\\ 
   & = \int_X f\mathrm{d}\mu 
\end{aligned}
$$
从而我们有结论成立. 再考虑$f_n \overset{\mu}{\longrightarrow} f$的情况, 根据[依测度收敛有几乎一致收敛的子子列](../Chapter%201.%20可测空间与可测函数/Lecture%202.%20可测函数的收敛性#3.2.%20依测度收敛有几乎一致收敛的子子列), 我们知道对$\{f_n\}$的任意一个子序列, 存在一个子子列$\{f_{n^{\prime}}\}$使得$f_{n^{\prime}}\overset{\mathrm{a.e.}}{\longrightarrow} f$. 从而根据已经证明的结论有
$$
\lim _{n^{\prime} \rightarrow \infty} \int_X f_{n^{\prime}} \mathrm{d} \mu=\int_X f \mathrm{~d} \mu .
$$
#####
___




