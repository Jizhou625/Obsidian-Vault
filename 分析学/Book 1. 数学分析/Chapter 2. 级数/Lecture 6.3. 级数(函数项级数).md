## 1. 函数项级数的一致收敛
### 1.1. Dini定理(连续性$\to$一致收敛)
若函数项级数 $\sum\limits_{n=1} u_n(x)$ 的每一项 (或 $n$ 充分大后的项) 为有界闭区间 $[a, b]$ 上的非负连续函数, 又已知级数的和函数 $S(x)$ 也在 $[a, b]$ 上连续, 则和函数$S(x)$ 在 $[a, b]$ 上一致收敛.

### 1.2. Bendixon判别法(导函数一致有界$\to$一致收敛)
设 $\sum\limits_{n=1}^{\infty} u_n(x)$ 为 $[a, b]$ 上的可微函数项级数, 且 $\sum\limits_{n=1}^{\infty} u_n^{\prime}(x)$ 的部分和函数列在 $[a, b]$ 上一致有界, 如果 $\sum\limits_{n=1}^{\infty} u_n(x)$ 在 $[a, b]$ 上收敛, 则必一致收敛.

### 1.3. 极限点处的性质(左连续+极限点发散$\to$不一致收敛)
设对每个 $n$, 函数 $u_n(x)$ 在 $x=c$ 处左连续, 又已知 $\sum\limits_{n=1}^{\infty} u_n(c)$ 发散, 则对于任意 $\delta>0, \sum\limits_{n=1}^{\infty} u_n(x)$ 在 区间 $(c-\delta, c)$ 上必不一致收敛.

### 1.4. 极限的可交换性
二元函数 $f(x, y)$定义在 $\mathcal{X} \times \mathcal{Y}$上,  $\exists x_0 \in \mathcal{X}, y_0 \in \mathcal{Y}$, 使得对每个 $x \in \mathcal{X}$ 存在极限 $\lim\limits_{y \rightarrow y_0} f(x, y)$, 对于每个 $y \in \mathcal{Y}$ 存在极限 $\lim\limits _{x \rightarrow x_0} f(x, y)$, 并且这两个极限过程之一对于另一个变量具有一致性, 则下式给出的二次极限存在且相等
$$
\lim _{x \rightarrow x_0} \lim _{y \rightarrow y_0} f(x, y)=\lim _{y \rightarrow y_0} \lim _{x \rightarrow x_0} f(x, y)
$$

## 2. 准一致收敛

### 2.1. 准一致收敛
如果函数列 $\left\{S_n\right\}$ 在 $[a, b]$ 上收敛于极限函数 $S(x)$, 且对每个 $\varepsilon>0$ 和每个 $N$, 存在 $N^{\prime}>N$, 使得对于每个 $x \in[a, b]$,  $\exists n_x \in\left[N, N^{\prime}\right]$, 满足 $\left|S_{n_x}(x)-S(x)\right|<\varepsilon$, 则称函数列 $\left\{S_n\right\}$ 在区间 $[a, b]$ 上准一致收敛
___
**Note**: 容易看出, 一致收敛一定是准一致收敛. 下面给出一个是准一致收敛但不是一致收敛的例子. 不失一般性, 设$S_n$定义在$[0,1]$上, 考虑
$$
S_n(x) = \begin{cases}  0 , \quad &x\neq \dfrac{1}{n} \\ 
\\
1, & x=\dfrac{1}{n}\end{cases}
$$
容易验证, $S_n(x)$收敛于$S(x)=0$, 但并非一致收敛. 而$S_n(x)$准一致收敛于$S(x)$

### 2.2. Arzela-Borel定理
设 $\left\{S_n\right\}$ 是 $[a, b]$ 上的连续函数列, 其极限函数为 $S(x) . S(x)$ 在 $[a, b]$ 上连 续的充分必要条件是函数列 $\left\{S_n\right\}$在 $[a, b]$上准一致收敛.

准一致收敛是级数和极限交换顺序的充分必要条件: 如果$S_n(x) = \sum\limits_{k=0}^{n} a_k(x)$, 则连续函数列$\{S_n(x)\}$准一致收敛当且仅当下式成立
$$
\lim\limits_{x\to x_0}\sum\limits_{k=0}^{\infty} a_k(x)=\sum\limits_{k=0}^{\infty}a_k(x_0)
$$

## 3. 积分、导数和极限的可交换性
### 3.1. Arzela控制收敛定理
设 $\left\{f_n\right\}$ 是在 $[a, b]$ 上收敛于极限函数 $f$ 的可积函数列, 若 $f$ 也在 $[a, b]$ 上可积, 且 $f_n$ 于 $[a, b]$ 上一致有界, 则有
$$
\lim _{n \rightarrow \infty} \int_a^b f_n(x) \mathrm{d} x=\int_a^b f(x) \mathrm{d} x
$$

### 3.2. Lebesgue控制收敛定理
设 $\left\{f_n\right\}$ 是测度空间 $(X, \mathscr{F}, \mu)$ 上的可测函数列, 若有 $f_n \stackrel{p}{\rightarrow} f$ 或 $f_n \stackrel{a . e}{\longrightarrow} f$, 且存在 $g \in L^1$ 使得 $\left|f_n\right| \leq g$, 则有
$$
\lim _{n \rightarrow \infty} \int_a^b f_n(x) \mathrm{d} \mu=\int_a^b f(x) \mathrm{d} \mu
$$

### 3.3. 导数和极限的可交换性
设函数列$\left\{f_n\right\}$ 在区间 $[a, b]$ 上可微. 且满足
1. 存在 $x_0 \in[a, b]$, 使得 $\lim\limits _{n \rightarrow \infty} f_n\left(x_0\right)$ 存在
2. $f_n^{\prime}(x) \rightrightarrows g(x)(x \in[a, b])$

则我们有以下结论
1.  存在 $[a, b]$ 上的函数 $f(x)$, 使得 $f_n(x) \rightrightarrows f(x)(x \in[a, b])$
2.  $f(x)$ 在 $[a, b]$ 上可微 (端点单侧可微), 并且 $f^{\prime}(x)=g(x)$, 即
$$
\lim _{n \rightarrow \infty} f_n^{\prime}(x)=\left[\lim _{n \rightarrow \infty} f_n(x)\right]^{\prime}=g(x)
$$

