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
\int_X f\mathrm{d}\mu = \sup \left\{\int_X g\mathrm{d}\mu\mid  0\le  g\le f, g\text{ is simple function}\right\}
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

### 2.2. 积分可积的性质
1. $f$可积当且仅当$|f|$可积
2. 如果$f$可积, 则$|f|<\infty$ a.e.

### 2.3. 积分的线性性质
设$f$和$g$是测度空间$(X, \mathscr{F}, \mu)$上积分存在的可测函数, 则
1. 对任何$a\in \mathbb{R}$, $af$的积分存在并且
   $$
   \int_X(af)\mathrm{d}\mu = a\int_X f\mathrm{d}\mu
   $$
2. 如果$\displaystyle{\int_X}f\mathrm{d}\mu + \displaystyle{\int_X}g\mathrm{d}\mu$, 则$f+g$ a.e. 有定义, 其积分存在并且
   $$
   \int_X(f+g)\mathrm{d}\mu = \int_X f\mathrm{d}\mu + \int_X g\mathrm{d}\mu
   $$

### 2.4. 积分的单调性质
设$f$和$g$是测度空间$(X, \mathscr{F}, \mu)$上的可积函数
1. 如果$\displaystyle{\int_A}f\mathrm{d}\mu \ge \displaystyle{\int_A}g\mathrm{d}\mu$对每个$A\in \mathscr{F}$成立, 则$f\ge g$ a.e.
2. 如果$\displaystyle{\int_A}f\mathrm{d}\mu = \displaystyle{\int_A}g\mathrm{d}\mu$对每个$A\in \mathscr{F}$成立, 则$f =  g$ a.e.

### 2.5. 积分的绝对连续性
如果$f$可积, 则对任何$\varepsilon>0$, 存在$\delta>0$, 使得对任意满足$\mu(A)<\delta$的$A\in \mathscr{F}$, 有
$$
\int_A |f|\mathrm{d}\mu < \varepsilon
$$

## 3. 可测函数列的积分性质
### 3.1. 单调收敛定理(Levi定理)
设$\{f_n\}$和$f$均为a.e.非负的可测函数. 如果$f_n \uparrow f$, 则
$$
\int_X f_n\mathrm{d}\mu \uparrow \int_X f\mathrm{d}\mu
$$

### 3.2. Fatou引理
对任意a.e.非负可测函数的序列$\{f_n\}$, 有
$$
\int_X (\liminf\limits_{n\to\infty} f_n)\mathrm{d}\mu \le \liminf\limits_{n\to\infty} \int_X f_n\mathrm{d}\mu
$$

### 3.3. Lebesgue控制收敛定理
设$\{f_n\}$和$f$均为可测函数, 且存在可积函数$g$, 使得$|f_n|\le g$ a.e.,  则$f_n\overset{\text{a.e.}}{\longrightarrow} f$或$f_n\overset{\mu}{\longrightarrow} f$意味着
$$
\lim\limits_{n\to\infty} \int_X f_n\mathrm{d}\mu  = \int_X f\mathrm{d}\mu
$$

### 3.4. 积分的变数变换
设$g$是测度空间$(X, \mathscr{F}, \mu)$到可测空间$(Y, \mathscr{S})$的可测映射
1. 对每个$B \in \mathscr{S}$, 令$\nu(B) = \mu(g^{-1}(B))$, 则$(Y, \mathscr{S}, \nu)$还是一个测度空间
2. 对$(Y, \mathscr{S}, \nu)$上的任何可测函数$f$, 只要等式
   $$
   \int_Y f\mathrm{d}\nu = \int_X f\circ g \mathrm{d}\mu 
   $$
   的一端有意义, 就一定成立. 

## 4. 空间$L_p(X, \mathscr{F}, \mu)$
### 4.1. $L_p$空间的定义
设$(X, \mathscr{F}, \mu)$是测度空间而且$1\le p < \infty$, 我们将所有满足下列条件的$(X, \mathscr{F}, \mu)$上的可测函数$f$
$$
\int_X |f|^p\mathrm{d}\mu < \infty
$$
组成的集合记作$L_p(X, \mathscr{F}, \mu)$, 由于我们只讨论给定的测度空间$(X, \mathscr{F}, \mu)$上集合$L_p(X, \mathscr{F}, \mu)$, 因此$L_p(X, \mathscr{F}, \mu)$也可以简记为$L_p$