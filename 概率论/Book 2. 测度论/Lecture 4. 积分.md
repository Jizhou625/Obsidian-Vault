## 1. 积分
### 1.1. 非负简单函数的积分
设$f$是一个非负简单函数而$f=\sum\limits_{i=1}^{n} a_i\mathbb{I}_{A_i}$是它的一个表达式, 则
$$
\int_{X} f\mathrm{d}\mu = \sum_{i=1}^{n} a_i\mu(A_i)
$$
为$f$的积分. 
____
##### 非负简单函数积分具有一意性
因为$f$是一个非负简单函数, 故$f$是一个只能取有限个不同非负值的可测函数. 于是, 必然存在不同的$b_1, b_2, \cdots, b_m\in \mathbb{R}^+$, 使得
$$
f = \sum\limits_{j=1}^{m} b_j\mathbb{I}_{\{f = b_j\}}
$$
不难看出: $n\ge m$, 对任意$i=1,2,\cdots, n$和$j=1,2,\cdots, m$, 有
$$
A_i\subset \{f = b_j\}\quad  \text{or} \quad A_i\cap \{f = b_j\} = \varnothing
$$
并且当$A_i\subset \{f = b_j\}$时, 有$a_i = b_j$, 因此我们有
$$
\begin{aligned} 
    \sum\limits_{i=1}^n a_i\mu(A_i) &= \sum\limits_{i=1}^{n} a_i \sum\limits_{j=1}^{m} \mu(A_i\cap \{f = b_j\}) \\ 
    & = \sum\limits_{i=1}^{n} \sum\limits_{\{j\mid A_i\subset \{f=b_j\}\}}^{} b_j\mu(A_i\cap \{f = b_j\}) \\ 
    & = \sum\limits_{i=1}^{n} \sum\limits_{j=1}^{m} b_j\mu(A_i\cap \{f = b_j\}) \\
    & = \sum\limits_{j=1}^{m} b_j\sum\limits_{i=1}^{n} \mu(A_i\cap \{f = b_j\}) \\
    & = \sum\limits_{j=1}^{m} b_j\mu(\{f = b_j\}) \\
\end{aligned}
$$
这说明通过$f$的不同表达式的算出来的积分总是相同的. 
#####
___


### 1.2. 非负简单函数积分的性质
设$f, g$和$\{f_n\}$是测度空间$(X, \mathscr{F}, \mu)$上的非负简单函数, 则
1. $\displaystyle{\int_X}\mathbb{I}_A\mathrm{d}\mu = \mu(A), \quad \forall A\in \mathscr{F}$
2. $\displaystyle{\int_X}f\mathrm{d}\mu \ge 0$
3. $\displaystyle{\int_X}(af)\mathrm{d}\mu = a\displaystyle{\int_X}f\mathrm{d}\mu, \quad \forall a\in \mathbb{R}^*$
4. $\displaystyle{\int_X}(f+g)\mathrm{d}\mu = \displaystyle{\int_X}f\mathrm{d}\mu+ \displaystyle{\int_X}g\mathrm{d}\mu$
5. 如果$f\ge g$, 则$\displaystyle{\int_X}f\mathrm{d}\mu \ge \displaystyle{\int_X}g\mathrm{d}\mu$
6. 如果$f \uparrow$且$\lim\limits_{n\to \infty} f_n\ge g$, 则$\lim\limits_{n\to\infty} \displaystyle{\int_X}f_n\mathrm{d}\mu \ge \displaystyle{\int_X}g\mathrm{d}\mu$

___
##### Proof:
我们只证明结论6, 对任意的$\alpha\in (0,1)$, 记$A_n(\alpha) = \{f_n\ge \alpha g\}$, $g=\sum\limits_{j=1}^{m} b_j\mathbb{I}_{B_j}$. 注意到$f_n\mathbb{I}_{A_n(\alpha)}$和$g\mathbb{I}_{A_n(\alpha)}$都还是非负简单函数而且$f_n\mathbb{I}_{A_n(\alpha)} \ge  \alpha g\mathbb{I}_{A_n(\alpha)}$, 由此
$$
\int_X f_n\mathrm{d}\mu \ge \int_X f_n\mathbb{I}_{A_n(\alpha)}\mathrm{d}\mu \ge \alpha \int_X g\mathbb{I}_{A_n(\alpha)}\mathrm{d}\mu = \alpha \sum\limits_{j=1}^{m} b_j\mu(A_n(\alpha)\cap B_j)
$$
由于$f_n\uparrow$且$\lim\limits_{n\to\infty} f_n\ge g$, 因此$A_n(\alpha)\uparrow X$, 因此$\mu(A_n(\alpha)\cap B_j)\uparrow \mu(B_j)$. 于是
$$
\lim\limits_{n\to\infty} \int_X f_n\mathrm{d}\mu \ge \alpha \sum\limits_{j=1}^{m}\lim\limits_{n\to\infty} b_j\mu(A_n(\alpha)\cap B_j) = \alpha\sum\limits_{j=1}^{m} b_j\mu(B_j) = \alpha \int_X g\mathrm{d}\mu
$$
再令$\alpha\to 1$, 即可得到原结论. 
#####
___

### 1.3. 非负可测函数的积分
对于测度空间$(X, \mathscr{F}, \mu)$上的非负可测函数$f$, 称
$$
\int_X f\mathrm{d}\mu = \sup \left\{\int_X g\mathrm{d}\mu\ \Big|\  0\le  g\le f, g\text{ is simple function}.\right\}
$$
为它的积分. 

### 1.4. 非负可测函数积分的性质
设$f$是测度空间$(X, \mathscr{F}, \mu)$上的非负可测函数$f$
1. 如果$\{f_n\}$是非负简单函数且$f_n\uparrow f$, 则
   $$
   \lim\limits_{n\to\infty} \displaystyle{\int_X}f_n\mathrm{d}\mu = \displaystyle{\int_X}f\mathrm{d}\mu
   $$
2. 非负可测函数的积分值也可以写成
   $$
   \int_X f\mathrm{d}\mu = \lim\limits_{n\to\infty}\left[\sum\limits_{k=0}^{n2^n-1} \dfrac{k}{2^n}\mu\left(\dfrac{k}{2^n}\le f< \dfrac{k+1}{2^n}\right) +n\mu(f\ge n) \right] 
   $$
3. $\displaystyle{\int_X}f\mathrm{d}\mu \ge 0$
4. $\displaystyle{\int_X}(af)\mathrm{d}\mu = a\displaystyle{\int_X}f\mathrm{d}\mu, \quad \forall a\in \mathbb{R}^*$
5. $\displaystyle{\int_X}(f+g)\mathrm{d}\mu = \displaystyle{\int_X}f\mathrm{d}\mu+ \displaystyle{\int_X}g\mathrm{d}\mu$
6. 如果$f\ge g$, 则$\displaystyle{\int_X}f\mathrm{d}\mu \ge \displaystyle{\int_X}g\mathrm{d}\mu$

### 1.5. 一般可测函数的积分
测度空间$(X, \mathscr{F}, \mu)$上的可测函数$f$如果满足
$$
\min\left\{\int_Xf^+\mathrm{d}\mu,\ \int_Xf^-\mathrm{d}\mu\right\} < \infty
$$
则称其积分存在或积分有意义, 如果满足
$$
\max\left\{\int_Xf^+\mathrm{d}\mu,\ \int_Xf^-\mathrm{d}\mu\right\} < \infty
$$
则称它是可积的. 在上述两种情况下, 把
$$
\int_X f\mathrm{d}\mu = \int_X f^+\mathrm{d}\mu - \int_X f^-\mathrm{d}\mu
$$
叫做$f$的积分或积分值. 

设$A\in \mathscr{F}$, 只要可测函数$f\mathbb{I}_{A}$的积分存在或可积, 我们就分别说$f$再集合$A\in \mathscr{F}$上积分存在或可积. 并且把
$$
\int_{A}f\mathrm{d}\mu = \int_{X} f\mathbb{I}_{A}\mathrm{d}\mu
$$
叫做$f$在集合$A\in \mathscr{F}$上的积分. 

### 1.6. L-S积分
设$g$是对准分布函数$F$而言的L-S可测函数, 如果$g$对$\lambda_F$的积分存在, 则这个积分称为$g$对$F$的L-S积分, 记作
$$
\int_{\mathbb{R}} g\mathrm{d}F = \int_{\mathbb{R}} g(x)\mathrm{d}F(x) = \int_{\mathbb{R}} g(x)\mathrm{d}\lambda_F(x)
$$
如果$A\in \mathscr{F}_{\lambda_F}$, 则称
$$
\int_{A} g\mathrm{d}F = \int_{\mathbb{R}}g \mathbb{I}_{A}\mathrm{d}F
$$
为$g$在集合$A$上对$F$的L-S积分. 

特别地, 如果$L$可测函数$g$对Lebesgue测度$\lambda$的积分存在, 则称之为L积分, 记为
$$
\int_{\mathbb{R}} g(x)\mathrm{d}x = \int_{\mathbb{R}} g \mathrm{d}\lambda
$$
如果$A\in \mathscr{F}_{\lambda}$, 则称
$$
\int_{A}g(x)\mathrm{d}x = \int_{\mathbb{R}}g(x)\mathbb{I}_A(x)\mathrm{d}x
$$
为$g$在集合$A$上的L积分. 
## 2. 积分的性质
### 2.1. 积分存在的性质
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

### 2.2. 积分可积的性质
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

### 2.3. 积分的线性性质
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
### 2.4. 积分值相等与可积函数的几乎处处相等
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

### 2.5. 积分的绝对连续性
如果$f$可积, 则对任何$\varepsilon>0$, 存在$\delta>0$, 使得对任意满足$\mu(A)<\delta$的$A\in \mathscr{F}$, 有
$$
\int_A |f|\mathrm{d}\mu < \varepsilon
$$
___
##### Proof: 
首先, 根据[[#2.2. 积分可积的性质]], $f$可积意味着$|f|$可积. 由于$|f|$是非负可测函数, 因此可以取非负简单函数
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

## 3. 可测函数列的积分性质
### 3.1. 单调收敛定理(Levi定理)
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

### 3.2. Fatou引理
对任意a.e.非负可测函数的序列$\{f_n\}$, 有
$$
\int_X (\liminf\limits_{n\to\infty} f_n)\mathrm{d}\mu \le \liminf\limits_{n\to\infty} \int_X f_n\mathrm{d}\mu
$$
___
##### Proof:
设$g_k =\inf\limits_{n\ge k} f_n$, 则我们有$g_k\uparrow \liminf\limits_{n\to\infty} f_n$, 因此根据[[#3.1. 单调收敛定理(Levi定理)]], 我们有
$$
\int_X(\liminf_{n\to\infty}f_n)\mathrm{d}\mu = \lim\limits_{k\to\infty}\int_X g_k\mathrm{d}\mu = \lim\limits_{k\to\infty} \int_X \left(\inf\limits_{n\ge k}f_n\right) \mathrm{d}\mu \le \liminf\limits_{n\to\infty} \int_X f_n\mathrm{d}\mu
$$
#####
___

### 3.3. Lebesgue控制收敛定理
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
从而我们有结论成立. 再考虑$f_n \overset{\mu}{\longrightarrow} f$的情况, 根据[[../Book 1. 初等概率论/Chapter 2. 收敛理论/Lecture 1. Modes of Stochastic Convergence#3.3. 几种收敛的关系|几种收敛的关系]], 我们知道对$\{f_n\}$的任意一个子序列, 存在一个子子列$\{f_{n^{\prime}}\}$使得$f_{n^{\prime}}\overset{\mathrm{a.e.}}{\longrightarrow} f$. 从而根据已经证明的结论有
$$
\lim _{n^{\prime} \rightarrow \infty} \int_X f_{n^{\prime}} \mathrm{d} \mu=\int_X f \mathrm{~d} \mu .
$$
#####
___

### 3.4. 积分的变数替换
设$g$是测度空间$(X, \mathscr{F}, \mu)$到可测空间$(Y, \mathscr{S})$的可测映射
1. 对每个$B \in \mathscr{S}$, 令$\nu(B) = \mu(g^{-1}(B))$, 则$(Y, \mathscr{S}, \nu)$还是一个测度空间
2. 对$(Y, \mathscr{S}, \nu)$上的任何可测函数$f$, 只要等式
   $$
   \int_Y f\mathrm{d}\nu = \int_X f\circ g \mathrm{d}\mu 
   $$
   的一端有意义, 就一定成立. 

## 4. 空间$L_p(X, \mathscr{F}, \mu)$
### 4.1. $L_p$空间的定义
设$(X, \mathscr{F}, \mu)$是测度空间
1. $1\le p < \infty$, 我们将所有满足下列条件的$(X, \mathscr{F}, \mu)$上的可测函数$f$
   $$
   \int_X |f|^p\mathrm{d}\mu < \infty
   $$
   组成的集合记作$L_p(X, \mathscr{F}, \mu)$
2. $p=\infty$时, 我们将$(X, \mathscr{F}, \mu)$上a.e. 有界的可测函数的全体记为$L_{\infty}(X, \mathscr{F}, \mu)$. 
3. $0<p<1$, 以$L_p$记测度空间$(X, \mathscr{F}, \mu)$上满足
   $$
   \|f\|_p = \int_X|f|^p\mathrm{d}\mu <\infty
   $$
   的可测函数的全体

由于我们只讨论给定的测度空间$(X, \mathscr{F}, \mu)$上集合$L_p(X, \mathscr{F}, \mu)$, 因此$L_p(X, \mathscr{F}, \mu)$也可以简记为$L_p$



### 4.2. 赋范线性空间
如果视$L_p$中a.e.相等的函数为同一个$L_p$中的元($1\le p\le \infty$), 则根据$\|f\|_p = \left(\displaystyle{\int_X}|f|^p\mathrm{d}\mu\right)^{\frac{1}{p}}$定义的$\|\cdot\|_p$是$L_p$上的范数, 在此观点下, $L_p$是一个赋范线性空间. 
___
##### Proof:
根据$\|\cdot\|_p$的定义, 可以验证$\|\cdot\|_p$具有半正定性和绝对一次齐次性. 而使用[[../../代数学/Chapter 0. 代数不等式/Lecture 1. 基础不等式#1.3. Minkowski不等式|Minkowski不等式]], 我们可以得到$\|\cdot\|$也具有次可加性. 因此$\|\cdot\|$是$L_p$上的范数, 从而$L_p$是一个赋范线性空间.
#####
___

