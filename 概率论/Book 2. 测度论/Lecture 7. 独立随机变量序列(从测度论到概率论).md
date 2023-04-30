## 1. 零一律和三级数定理
### 1.1. 尾事件
设$\{f_n\}$是概率空间$(X, \mathscr{F}, \mathbb{P})$上的随机变量序列, 对每个$n=1,2,\cdots$, 记
$$
\mathscr{G} = \sigma(\{f_k \mid k=n, n+1, \cdots\})
$$
则$\mathscr{G}_n$是$\mathscr{F}$的子$\sigma$域, 它们的交
$$
\mathscr{G} = \bigcap\limits_{n=1}^{\infty} \mathscr{G}_n
$$
还是一个$\mathscr{F}$的子$\sigma$域, 称之为$\{f_n\}$的尾$\sigma$域, 尾$\sigma$域中的事件称为尾事件; 关于尾$\sigma$域$\mathscr{G}$可测的随机变量称为尾随机变量. 
___
##### Examples:
1. 设$\{f_n\}$是一串随机变量序列, 则
   $$
   \left\{\lim _{n \rightarrow \infty} f_n \exists\right\}=\left\{\lim _{n \rightarrow \infty} f_{n+N} \exists\right\} \in \mathscr{G}_N 
   $$
   这表明$\left\{\lim\limits _{n \rightarrow \infty} f_n \exists\right\}\in \mathscr{G}$, 因此是个尾事件. 
2. 设$\{f_n\}$是一串随机变量序列, $a\in \mathbb{R}$, 则
   $$
   \left\{\liminf _{n \rightarrow \infty} f_n>a\right\}=\left\{\liminf _{n \rightarrow \infty} f_{n-N}>a\right\} \in \mathscr{G}_N
   $$
   这表明$\left\{\liminf \limits_{n \rightarrow \infty} f_n>a\right\}\in \mathscr{G}$, 因此是一个尾事件. 
#####
___

### 1.2. Kolmogorov零一律
独立随机变量序列任何一个尾事件的概率非$0$即$1$, 任何一个伪随机变量a.s.为一个常数. 
___
##### Proof:
考虑filter $\mathscr{F}_n = \sigma(\{f_k \mid k=1,2,\cdots, n\})$, 则$\mathscr{F}_n$是$\mathscr{F}$的子$\sigma$域, 且$\mathscr{F}_n \subset \mathscr{F}_{n+1}$, 令
#####
___

### 1.3. Borell-Cantelli引理
设$\{A_n\}\subset \mathscr{F}$
1. 如果$\sum\limits_{n=1}^{\infty} \mathbb{P}(A_n)<\infty$, 则
   $$
   \mathbb{P}\left(\limsup\limits_{n\to\infty} A_n\right) = 0
   $$
2. 如果$\{A_n\}$独立并且$\sum\limits_{n=1}^{\infty} \mathbb{P}(A_n) = \infty$, 则
   $$
    \mathbb{P}\left(\limsup\limits_{n\to\infty} A_n\right) = 1
   $$

### 1.4. 级数和的a.s.收敛
1. 对任意随机变量序列$\{f_n\}$, $\sum\limits_{n=1}^{\infty} f_n$ a.s.收敛当且仅当对任意给定的$\varepsilon>0$, 有
   $$
   \lim\limits_{n\to\infty}\lim\limits_{N\to\infty} \mathbb{P}\left(\max_{n\le l\le N}|S_l - S_n|\ge \varepsilon\right) = 0 
   $$
2. 设$\{f_n\}$是独立随机变量序列, 而且对每个$n=1,2,\cdots$, 均有$\mathbb{E}f_n=0$和$\sigma^2 = \operatorname*{Var}\left(f_n\right)<\infty$. 如果$\sum\limits_{n=1}^{\infty} \sigma^2_n<\infty$, 则$\sum\limits_{n=1}^{\infty}f_n$ a.s. 收敛. 反之, 若对每个$n=1,2,\cdots$, 均有$|f_n|\le C$ a.s. 且$\sum\limits_{n=1}^{\infty} f_n$ a.s.收敛, 则$\sum\limits_{n=1}^{\infty} \sigma^2_n<\infty$

### 1.5. Kolmogorov三级数定理
设$\{f_n\}$是独立随机变量序列, 级数$\sum\limits_{n=1}^{\infty} f_n$ a.s. 收敛的充分必要条件是对某一个$C>0$或对任意的$C>0$, 下列三式成立
$$
\begin{aligned} 
    &\sum\limits_{n=1}^{\infty} \mathbb{P}(|f_n|>C) < \infty \\ 
    &\sum\limits_{n=1}^{\infty} \mathbb{E}f_n\mathbb{I}_{\{|f_n|\le C\}} \text{ is convergent} \\ 
    &\sum\limits_{n=1}^{\infty} \operatorname*{Var}\left(f_n\mathbb{I}_{\{|f_n|\le C\}} \right) < \infty
\end{aligned}
$$

## 2. 强大数律
### 2.1. Kronecker大数律
设对每个 $n=1,2, \cdots, a_n, b_n \in \mathbb{R}$ 且 $0<b_n \uparrow \infty$. 如果 $\sum\limits_{n=1}^{\infty} \dfrac{a_n}{b_n}$ 收敛, 则
$$
\lim _{n \rightarrow \infty} \frac{1}{b_n} \sum_{k=1}^n a_k=0
$$

### 2.2. Kolmogorov强大数律(方差版本)
设 $\left\{f_n\right\} \subset L_2$ 是独立随机娈量序列. 如果 $\sum\limits_{n=1}^{\infty} \dfrac{\operatorname{var} f_n}{n^2}$ $<\infty$, 则
$$
\frac{S_n-\mathbb{E}S_n}{n} \stackrel{\text { a.s. }}{\longrightarrow} 0
$$


### 2.2. Kolmogorov强大数律(绝对值期望版本)
设$\left\{f_n\right\}$ 是独立同分布随机变量序列. 如果 $\mathrm{E}\left|f_1\right|<\infty$, 则
$$
\frac{S_n}{n} \stackrel{\text { a.s. }}{\longrightarrow} \mathbb{E}f_1
$$
反之, 如果 $\lim \limits_{n \rightarrow \infty}\dfrac{S_n}{n}$ a.s. 存在,  则$\mathbb{E}\left|f_1\right|<\infty$ 而且 $\lim \limits_{n \rightarrow \infty}\dfrac{S_n}{n} = \mathbb{E}f_1$  a.s. 

## 3. 特征函数
### 3.1. 定义
对每个 $t \in \mathbb{R}$, 随机变量 $f$ 的特征函数 $\phi(t)$ 定义为
$$
\phi(t)=\mathrm{Ee}^{t f} \stackrel{\text { def }}{=} \mathbb{E} \cos (t f)+ \mathrm{i}\mathbb{E} \sin (t f)
$$
如果$f\sim F$, 可以把特征函数 $\phi(t)$用它的分布函数的L-S积分表示为
$$
\begin{aligned}
\phi(t) & =\int_{\mathbb{R}} \cos t x \mathrm{~d} F(x)-\mathrm{i} \int_{\mathbb{R}}  \sin t x \mathrm{~d} F(x) \\
& \stackrel{\operatorname{def}}{=} \int_{\mathbb{R}} \mathrm{e}^{\mathrm{i} t x} \mathrm{~d} F(x) .
\end{aligned}
$$

### 3.2. 特征函数的性质
特征函数满足
1. $\phi(0)=1$;
2. $|\phi(t)|\le 1,\quad \forall t\in \mathbb{R}$
3. $\phi$在$\mathbb{R}$上一致连续

### 3.3. 矩和特征函数
设 $\phi$ 是随机变量 $f$ 的特征函数. 奻果 $f$ 的 $k$ 阶矩存在, 则 $\phi$ 的 $k$ 阶导数 $\phi^{(k)}$ 存在, 且对每个 $t \in \mathbb{R}$ 有
$$
\phi^{(k)}(t)=\mathrm{i}^k \mathbb{E} f^k \mathrm{e}^{\mathrm{i} t f} .
$$
特别地, 下列关系成立: $\phi^{(k)}(0)=\mathrm{i}^k \mathbb{E} f^k$.

### 3.4. 独立随机变量组合的特征函数
如果 $\phi_1, \cdots, \phi_n$ 分别是独立随机变量 $f_1, \cdots, f_n$ 对应的特征函数, 对每个 $t \in\mathbb{R}$, 令
$$
g_n(t)=\prod_{t=1}^n \phi_1(t),
$$
则 $g_n$ 是 $S_n=f_1+\cdots+f_n$ 的特征函数.

### 3.5. 反演公式
如果 $\phi$ 是 d.f. $F$ 的特征函数, 则
$$
\bar{F}(b)-\bar{F}(a)=\frac{1}{2 \pi} \lim _{T \rightarrow \infty} \int_{-T}^T \frac{\mathrm{e}^{-\mathrm{i} t s}-\mathrm{e}^{-\mathrm{i} t a}}{-\mathrm{i} t} \phi(t) \mathrm{d} t
$$
对任何 $a, b \in R$ 成立,这里
$$
\left.\frac{\mathrm{e}^{-\mathrm{i} t t}-\mathrm{e}^{-\mathrm{i} t a}}{-\mathrm{i} t}\right|_{t=0} \stackrel{\text { def }}{=} \lim _{t \rightarrow 0} \frac{\mathrm{e}^{-\mathrm{i} tb}-\mathrm{e}^{-\mathrm{i} t a}}{-\mathrm{i} t}=b-a,
$$
而对每个 $x \in \mathbb{R}$,
$$
\bar{F}(x)=\frac{F(x)+F(x-0)}{2} .
$$

### 3.6. 分布函数与特征函数的收敛
分布函数序列 $\left\{F_n, n=1,2, \cdots\right\}$ 弱收敛到分布函数 $F$ 的充分必要条件是对应的特征函数序列点点收敛到 $F$ 的特征函数. 并且, 如果 $F_n \stackrel{w}{\longrightarrow} F$, 则对任何 $T>0, \phi_n(t) \rightarrow \phi(t)$ 在区间 $[-T, T]$ 上一致成立.

## 4. 弱大数定律
### 4.1. 弱大数定律
对任意的$\{a_n\in \mathbb{R}^+\}$, 如果
$$
\begin{cases} 
\lim \limits_{n \rightarrow \infty} \sum\limits_{k=1}^n \mathbb{P}\left(\left|f_k\right| \geqslant a_n\right)=0 \\
\lim\limits _{n \rightarrow \infty} \dfrac{1}{a_n} \sum\limits_{k=1}^n \mathbb{E} f_k \mathbb{I}_{\left\{\left|f_k\right|<a_n\right\}}=0 \\
\lim\limits _{n \rightarrow \infty} \dfrac{1}{a_n^2} \sum\limits_{k=1}^n \operatorname{Var} \left(f_k \mathbb{I}_{\left\{\left|f_k\right|<a_n\right\}}\right)=0  
\end{cases}
$$
则
$$
\dfrac{S_n}{a_n} \stackrel{p}{\longrightarrow} 0
$$


### 4.2. 一致渐进可忽略
设 $\left\{g_{n, k}\mid  k=1, \cdots, n \right\}$ 是一个随机变量阵列. 如果对任给 $\varepsilon>0$ 均有
$$
\lim _{n \rightarrow \infty } \max _{1 \leqslant k \leqslant n} \mathbb{P}\left(\left|g_{n ,  k}\right| \geqslant \varepsilon\right)=0
$$
则称它为一致渐进可忽略的.

### 4.3. 一致渐进可忽略的性质
如果 $\left\{g_{n, k}\mid  k=1, \cdots, n \right\}$ 是一致渐进可忽略的, 以 $\phi_{n, k}$ 记 $g_{n, k}$ 的特征函数, $m_{n, k}$ 记 $g_{n, k}$ 的一个中位数, 则
$$
\lim _{n \rightarrow \infty} \max _{1 \ll k \leqslant n} m_{n, k}=0
$$
且对每个 $t \in \mathbb{R}$ 有
$$
\max _{1 \leqslant k \leqslant n}\left|\phi_{n, k}(t)-1\right| \rightarrow 0
$$

## 5. 中心极限定理
### 5.1. Lindeberg定理
如果独立不全退化的随机变量序列$\{f_n\}$满足
$$
\lim _{n \rightarrow \infty} \sum_{k=1}^n \mathbb{E} {g_{n, k}^2} \mathbb{I}_{\left\{\left|g_{n, k}\right| \geqslant \varepsilon\right\}}=0
$$
则
$$
\frac{S_n-M_n}{D_n} \stackrel{d}{\longrightarrow} \Phi .
$$
这里
$$
M_n=\sum_{k=1}^n \mathbb{E} f_n ; \quad D_n^2=\sum_{k=1}^n \sigma_k^2 .
$$

### 5.2. Lyapounov定理
设 $\left\{f_n, n=1,2, \cdots\right\}$ 为独立不全退化的随机变量序列. 如果存在 $\delta>0$ 使 $\mathbb{E}\left|f_n\right|^{2+\delta}<\infty$ 且满足 Lyapounov 条件
$$
\lim _{n \rightarrow \infty} \frac{1}{D_n^{2+\delta}} \sum_{k=1}^n \mathbb{E}\left|f_k-\mathbb{E} f_k\right|^{2+\delta}=0,
$$
则
$$
\frac{S_n-M_n}{D_n} \stackrel{d}{\longrightarrow} \Phi .
$$