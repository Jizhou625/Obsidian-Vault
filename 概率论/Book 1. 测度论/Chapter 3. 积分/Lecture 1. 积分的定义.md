## 1. 非负简单函数的积分
### 1.1. 定义
在测度空间$(X, \mathscr{F}, \mu)$上, $f$是一个非负简单函数而$f=\sum\limits_{i=1}^{n} a_i\mathbb{I}_{A_i}$是它的一个表达式, 则
$$
\int_{X} f\mathrm{d}\mu = \sum_{i=1}^{n} a_i\mu(A_i)
$$
为$f$的积分. 

### 1.2. 非负简单函数积分具有一意性
非负简单函数的积分具有一意性. 即无论如何选择$f$的表达式, 都会得到相同的积分.
___
##### Proof
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


### 1.3. 非负简单函数积分的性质
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

## 2. 非负可测函数的积分
### 2.1. 非负可测函数的积分
对于测度空间$(X, \mathscr{F}, \mu)$上的非负可测函数$f$, 称
$$
\int_X f\mathrm{d}\mu = \sup \left\{\int_X g\mathrm{d}\mu\ \Big|\  0\le  g\le f,\quad g\text{ is simple function}.\right\}
$$
为它的积分. 

### 2.2. 非负可测函数积分的性质
设$f$是测度空间$(X, \mathscr{F}, \mu)$上的非负可测函数$f$
1. 如果$\{f_n\}$是非负简单函数且$f_n\uparrow f$, 则
   $$
   \lim\limits_{n\to\infty} \displaystyle{\int_X}f_n\mathrm{d}\mu = \displaystyle{\int_X}f\mathrm{d}\mu
   $$
2. 非负可测函数的积分值可以写成
   $$
   \int_X f\mathrm{d}\mu = \lim\limits_{n\to\infty}\left[\sum\limits_{k=0}^{n2^n-1} \dfrac{k}{2^n}\mu\left(\dfrac{k}{2^n}\le f< \dfrac{k+1}{2^n}\right) +n\mu(f\ge n) \right] 
   $$
3. $\displaystyle{\int_X}f\mathrm{d}\mu \ge 0$
4. $\displaystyle{\int_X}(af)\mathrm{d}\mu = a\displaystyle{\int_X}f\mathrm{d}\mu, \quad \forall a\in \mathbb{R}^*$
5. $\displaystyle{\int_X}(f+g)\mathrm{d}\mu = \displaystyle{\int_X}f\mathrm{d}\mu+ \displaystyle{\int_X}g\mathrm{d}\mu$
6. 如果$f\ge g$, 则$\displaystyle{\int_X}f\mathrm{d}\mu \ge \displaystyle{\int_X}g\mathrm{d}\mu$


## 3. 一般可测函数的积分
### 3.1. 一般可测函数的积分
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

设$A\in \mathscr{F}$, 只要可测函数$f\mathbb{I}_{A}$的积分存在或可积, 我们就分别说$f$在集合$A\in \mathscr{F}$上积分存在或可积. 并且把
$$
\int_{A}f\mathrm{d}\mu = \int_{X} f\mathbb{I}_{A}\mathrm{d}\mu
$$
叫做$f$在集合$A\in \mathscr{F}$上的积分. 

### 3.2. L-S积分
设$g$是对准分布函数$F$而言的L-S可测函数, 如果$g$对$\lambda_F$的积分存在, 则这个积分称为$g$对$F$的L-S积分, 记作
$$
\int_{\mathbb{R}^n} g\mathrm{d}F = \int_{\mathbb{R}^n}g(\boldsymbol{x})\mathrm{d}F(\boldsymbol{x}) = \int_{\mathbb{R}^n}g\mathrm{d}\lambda_F
$$
如果$A\in \mathscr{F}_{\lambda_F}$, 则称
$$
\int_A g\mathrm{d}F = \int_{\mathbb{R}^n} g\mathbb{I}_A \mathrm{d}F
$$
为$g$在集合$A$上对$F$的L-S积分. 特别地, 如果L可测函数$g$对Lebesgue测度$\lambda$的积分存在, 则称为$L$积分
$$
\int_{\mathbb{R}^n} g(\boldsymbol{x})\mathrm{d}\boldsymbol{x} = \int_{\mathbb{R}^n} g\mathrm{d}\lambda
$$
如果$A\in \mathscr{F}_{\lambda}$, 则称
$$
\int_A g(\boldsymbol{x})\mathrm{d}\boldsymbol{x} = \int_{\mathbb{R}^n} g(\boldsymbol{x})\mathbb{I}_A \mathrm{d}\boldsymbol{x}
$$
为$g$在集合$A$上的$L$积分.
