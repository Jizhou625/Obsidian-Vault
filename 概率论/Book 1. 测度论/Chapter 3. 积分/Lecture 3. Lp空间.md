## 1. 空间$L_p(X, \mathscr{F}, \mu)$
### 1.1. $L_p$空间的定义
设$(X, \mathscr{F}, \mu)$是测度空间
1. $1\le p < \infty$, 我们将所有满足下列条件的$(X, \mathscr{F}, \mu)$上的可测函数$f$
   $$
   \int_X |f|^p\mathrm{d}\mu < \infty
   $$
   组成的集合记作$L_p(X, \mathscr{F}, \mu)$
2. $p=\infty$时, 我们将$(X, \mathscr{F}, \mu)$上a.e.有界的可测函数的全体记为$L_{\infty}(X, \mathscr{F}, \mu)$. 
3. $0<p<1$, 我们将所有满足下列条件的$(X, \mathscr{F}, \mu)$上的可测函数$f$
   $$
   \int_X|f|^p\mathrm{d}\mu <\infty
   $$
   组成的集合记作$L_p(X, \mathscr{F}, \mu)$

由于我们只讨论给定的测度空间$(X, \mathscr{F}, \mu)$上集合$L_p(X, \mathscr{F}, \mu)$, 因此$L_p(X, \mathscr{F}, \mu)$也可以简记为$L_p$

### 1.2. $L_p$范数
在空间$L_p(X, \mathscr{F}, \mu)$上, 定义$L_p$范数为
1. 当 $1\le p < \infty$ 时
   $$
   \|f\|_p = \left(\displaystyle{\int_X}|f|^p\mathrm{d}\mu\right)^{\frac{1}{p}}
   $$
2. 当 $p=\infty$ 时
   $$
   \|f\|_{\infty} = \inf\{a\in \mathbb{R}^+ \mid \mu(|f|>a) = 0\}
   $$
3. 当 $0<p<1$ 时
   $$
   \|f\|_p = \displaystyle{\int_X}|f|^p\mathrm{d}\mu
   $$

### 1.3. $L_p$是完备距离空间
对任意的$f, g\in L_p$, 定义$L_p$上的距离为
$$
\rho(f, g) = \|f-g\|_p
$$
$L_p$在这个距离下是完备的. 也就是说, 如果$\{f_n\}\subset L_p$满足
$$
\lim\limits_{n, m\to\infty}  \|f_n - f_m\|_p = 0 
$$
则存在$f\in L_p$使得
$$
\lim\limits_{n\to\infty} \|f_n - f\|_p = 0
$$
称$\{f_n\}$($p$阶)平均收敛到$f$, 记为$f_n \overset{L_p}{\longrightarrow} f$
___
##### Proof
对每个$k=1,2,\cdots$, 取正整数$n_k$使得$n_1<n_2<\cdots$而且
$$
\left\|f_{n_{k+1}}-f_{n_k}\right\|_p< \dfrac{1}{2^k}
$$
对每个$k=1,2,\cdots$, 令
$$
g_k = |f_{n_1}| + \sum\limits_{i=1}^{k} |f_{n_{i+1}} - f_{n_i}| 
$$
根据Minkowski不等式, 我们有
$$
\left\|g_k\right\|_p \leqslant\left\|f_{n_1}\right\|_p+\sum_{i=1}^k\left\|f_{n_{i+1}}-f_{n_i}\right\|_p \le \|f_{n_1}\|_p + 1
$$
设
$$
g=\left|f_{n_1}\right|+\sum_{i=1}^{\infty}\left|f_{n_{i+1}}-f_{n_i}\right|
$$
容易看出, $g_k\uparrow g$, 从而由单调收敛定理推出
$$
\int_X g^p \mathrm{~d} \mu=\lim _{k \rightarrow \infty} \int_X g_k^p \mathrm{d} \mu \leqslant\left(\left\|f_{n_1}\right\|_p+1\right)^p<\infty
$$
故$g\in L_p$, 这蕴含$g<\infty$ a.e. 从而我们知道级数$f_{n_1} +\sum\limits_{i=1}^{\infty} (f_{n_{i+1}} - f_{n_i})$ a.e. 收敛, 即$f = \lim\limits_{k\to\infty} f_{n_k}$ a.e. 有定义. 由于
$$
|f|=\lim _{k \rightarrow \infty}\left|f_{n_1}+\sum_{i=1}^k\left(f_{n_{i+1}}-f_{n_i}\right)\right| \leqslant \lim _{k \rightarrow \infty} g_k=g \text { a. e. }
$$
因为$g\in L_p$, 因此$f\in L_p$. 由于
$$
\lim\limits_{n, m\to\infty}  \|f_n - f_m\|_p = 0 
$$
因此对任意给定的$\varepsilon>0$, 可以取充分大的$N$, 使得对一切$n, m\ge N$, 由
$$
\|f_n - f_m\|_p < \varepsilon
$$
则由[Fatou引理](Lecture%202.%20积分的性质.md#2.2.%20Fatou引理), 当$n\ge N$, 有
$$
\int_X|f_n-f|^p \mathrm{d}\mu =\int_X \lim\limits_{k\to\infty} |f_n-f_{n_k}|^p\mathrm{d}\mu  \leqslant \liminf _{m \rightarrow \infty} \int_X\left|f_n-f_{n_k}\right|^p \mathrm{d}\mu \leqslant \varepsilon
$$
这就证明了$\lim\limits_{n\to\infty} \|f_n - f\|_p = 0$.
#####
___


### 2. $L_p$上的收敛
### 2.1. $p$阶平均收敛和其他收敛的关系
设$0<p<\infty$, $\{f_n\}\subset L_p$和$f\in L_p$
1. 如果$f_n\overset{L_p}{\longrightarrow}f$, 则$f_n\overset{\mu}{\longrightarrow} f$且$\lim\limits_{n\to\infty} \|f_n\|_p\to\|f\|_p$
2. 如果$f_n\overset{\mathrm{a.e.}}{\longrightarrow} f$或$f_n\overset{\mu}{\longrightarrow} f$, 则
   $$
   \|f_n\|_p \to \|f\|_p \iff f_n\overset{L_p}{\longrightarrow} f
   $$

___
##### Proof:
1. 设$f_n\overset{L_p}{\longrightarrow}f$, 对任意给定的$\varepsilon>0$有
   $$
   \begin{aligned}
   \mu\left(\left|f_n-f\right| \geqslant \varepsilon\right) & \leqslant \frac{1}{\varepsilon^p} \int_{\left\{\left|f_n-f\right| \geqslant \varepsilon \right\}}\left|f_n-f\right|^p \mathrm{~d} \mu \\
   & \leqslant \frac{1}{\varepsilon^p} \int_X\left|f_n-f\right|^p \mathrm{~d} \mu \\
   & =\frac{1}{\varepsilon^p}\left\|f_n-f\right\|_p^p \rightarrow 0,
   \end{aligned}
   $$
   因此我们有$f\overset{\mu}{\longrightarrow} f$. 此外由Minkowski不等式, 我们有
   $$
   \left|\left\|f_n\right\|_p-\|f\|_p\right| \leqslant\left\|f_n-f\right\|_p \rightarrow 0 
   $$
2. 只需要证明$\Longrightarrow$部分, 如果$f_n\overset{\mu}{\longrightarrow}f$, 则对$\{f_n\}$的任意一个子列, 存在其子列$\{f_{n^{\prime}}\}$使得$f_{n^{\prime}}\overset{\mathrm{a.e.}}{\longrightarrow}f$, 令
   $$
   g_{n^{\prime}}=C_p\left(\left|f_{n^{\prime}}\right|^p+|f|^p\right)-\left|f_{n^{\prime}}-f\right|^p,\quad C_p = \begin{cases}  2^{p-1},\quad &1\le p\le \infty \\ 1, &0<p<1\end{cases}
   $$
   于是
   $$
   \lim _{n^{\prime} \rightarrow \infty} g_{n^{\prime}} =C_p\left(\lim _{n^{\prime} \rightarrow \infty}\left|f_{n^{\prime}}\right|^p+|f|^p\right)-\lim _{n^{\prime} \rightarrow \infty}\left|f_{n^{\prime}}-f\right|^p  =2 C_p|f|^p \text { a. e. . }
   $$
   当$\|f_n\|_p\to \|f\|_p$成立时, 由[Fatou引理](Lecture%202.%20积分的性质.md#2.2.%20Fatou引理), 我们有
   $$
   \begin{aligned}
   \int_X\left(2 C_p|f|^p\right) \mathrm{d} \mu & =\int_X\left(\lim _{n^{\prime} \rightarrow \infty} g_{n^{\prime}}\right) \mathrm{d} \mu \leqslant \liminf _{n^{\prime}\to\infty} \int_X g_{n^{\prime}} \mathrm{d} \mu \\
   & =\int_X\left(2 C_p|f|^p\right) \mathrm{d} \mu-\limsup _{n^{\prime} \rightarrow \infty} \int_X\left|f_{n^{\prime}}-f\right|^p \mathrm{~d} \mu 
   \end{aligned}
   $$
   这样我们就得到了
   $$
   \lim\limits_{n^{\prime}\to\infty} \int_X\left|f_{n^{\prime}}-f\right|^p \mathrm{~d} \mu = 0
   $$
   于是对$\{\|f_n-f\|_p\}$的任意一个子列, 都进一步存在一个趋于$0$的子列, 这意味着$f_n\overset{L_p}{\longrightarrow}f$
#####
___

### 2.2. 弱收敛
如果当 $1<p<\infty$ 或当 $p=1$ 且 $(X, \mathscr{F}, \mu)$ 为 $\sigma$ 有限测度空间时, 对某个 $f \in L_p$ 有
$$
\lim _{n \rightarrow \infty} \int_{X} f_n g \mathrm{~d} \mu=\int_{X} f g \mathrm{~d} \mu, \quad \forall g \in L_q,\ \dfrac{1}{q}+ \dfrac{1}{p} =1
$$
则称 $\left\{f_n\right\}$ 在 $L_p$ 中弱收敛到 $f$, 记为
$$
f_n \stackrel{(w) L_p}{\longrightarrow} f 
$$


### 2.3. 弱收敛和其他收敛的关系
1. 设 $1<p<\infty$. 如果 $\left\{f_n\right\}$ 是 $L_p$ 中的有界序列(也就是说 $\sup\left\|f_n\right\|_p<\infty$)而且 $f_n \stackrel{\mu}{\longrightarrow} f$ 或者 $f_n \stackrel{\text { a.e. }}{\longrightarrow} f$ 对某个可测函数 $f$ 成立, 则 $f \in L_p$ 且 $f_n \stackrel{(w) L_p}{\longrightarrow} f$.
2. 设 $\left\{f_n\right\} \subset L_1$ 和 $f \in L_1$ 如果 $\left\|f_n\right\| \rightarrow\|f\|$ 而且 $f_n \stackrel{\mu}{\longrightarrow} f$ 或者 $f_n \stackrel{\text { a.e. }}{\longrightarrow} f$ 成立, 则
   - $f_n \stackrel{L_1}{\longrightarrow} f$
   - $f_n \stackrel{(w) L_1}{\longrightarrow} f$
   - $\displaystyle{\int_A} f_n \mathrm{~d} \mu \rightarrow \displaystyle{\int_A} f \mathrm{~d} \mu, \forall A \in \mathscr{F}$.
___
##### Proof
1. 我们只需要证明$f_n \stackrel{\text { a.e. }}{\longrightarrow} f$的情况, $f_n \stackrel{\mu}{\longrightarrow} f$可以用任意子序列存在一致收敛的子序列来进行证明. 我们分下面的
#####
___