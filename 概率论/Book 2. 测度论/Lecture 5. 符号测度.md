## 1. 符号测度
### 1.1. 符号测度的定义
设$(X, \mathscr{F})$是一个可测空间, 从$\mathscr{F}$到$\overline{\mathbb{R}}$的集函数$\varphi$, 如果满足
1. $\varphi(\varnothing)=0$
2. 可列可加性: 对任何两两不交的$\{A_n\}\subset \mathscr{F}$, 有
   $$
   \varphi\left(\bigcup\limits_{n=1}^{\infty} A_n\right) = \sum\limits_{n=1}^{\infty} \varphi(A_n)
   $$

如果符号测度$\varphi$满足$|\varphi(A)|<\infty, \forall A\in \mathscr{F}$, 则称它是有限的. 如果存在$X$的可测分割$\{A_n\}$, 使得$|\varphi(A_n)|<\infty, \forall n$, 则称$\varphi$是$\sigma$-有限的.

显然, 测度空间$(X, \mathscr{F}, \mu)$上积分存在的可测函数$f$的不定积分
$$
\varphi(A) = \int_A f\mathrm{d}\mu, \quad \forall A\in \mathscr{F}
$$
是一个符号测度.

### 1.2. 符号测度的性质
1. 对任何符号测度$\varphi$, 有下面两条中的某一条成立
   $$
   \begin{aligned} 
        -\infty < \varphi(A) \le \infty, \quad \forall A\in \mathscr{F} \\
        -\infty \le \varphi(A) < \infty, \quad \forall A\in \mathscr{F} 
   \end{aligned}
   $$
2. 设$\varphi$是可测函数$(X, \mathscr{F})$上的符号测度. 如果$A, B\in \mathscr{F}$, $A\supset B$且$|\varphi(A)|<\infty$, 则$|\varphi(B)|<\infty$
3. 设$\varphi$是一个符号测度, 如果$\{A_n\}\subset \mathscr{F}$两两不相交且满足
   $$
   \left|\varphi\left(\bigcup\limits_{n=1}^{\infty} A_n\right)\right| < \infty
   $$

## 2. 不定积分的Hahn分解和Jordan分解
### 2.1. 不定积分的Hahn分解
考虑不定积分
$$
\varphi(A) = \int_A f\mathrm{d}\mu, \quad \forall A\in \mathscr{F}
$$
设$X^+ = \{f\ge 0\}, X^- = \{f< 0\}$. 则$\{X^+, X^-\}$形成$(X, \mathscr{F})$的可测分割. 它们把空间$X$劈成具有下列性质的两部分
$$
\begin{aligned} 
    A\in \mathscr{F}, A\subset X^+ \Rightarrow \varphi(A)\ge 0 \\ 
    A\in \mathscr{F}, A\subset X^- \Rightarrow \varphi(A)\le 0
\end{aligned}
$$
我们把具有上述性质的$\{X^+, X^-\}$称为$\varphi$的Hahn分解

### 2.2. 不定积分的Jordan分解
对每个$A\in\mathscr{F}$, 设
$$
\varphi^{\pm}(A) = \int_A f^{\pm}\mathrm{d}\mu
$$
则$\varphi^+$和$\varphi^-$都是测度而且分解式
$$
\varphi = \varphi^+ - \varphi^-
$$
我们把该分解称为$\varphi$的Jordan分解

## 3. Hahn分解
### 3. Hahn分解
对于可测空间$(X, \mathscr{F})$上的符号测度$\varphi$, 存在$X^{\pm}\in \mathscr{F}$使得
$$
X^+\cup X^{-} = X, \quad X^+\cap X^{-} = \varnothing
$$
并且对于每个$A\in \mathscr{F}$, 有
$$
\varphi(A\cap X^{+}) \ge 0 \ge \varphi(A\cap X^{-})
$$
Hahn分解$\{X^+, X^-\}$在下列意义下是唯一的, 如果存在两个分解$\{X^+_1, X^-_1\}$和$\{X^+_2, X^-_2\}$, 则
$$
\begin{aligned} 
   A\in \mathscr{F}, A\subset X^+_1 \Delta X^+_2 &\Longrightarrow \varphi(A) = 0 \\ 
   B\in \mathscr{F}, B\subset X^-_1 \Delta X^-_2 &\Longrightarrow \varphi(B) = 0
\end{aligned}
$$

## 4. Jordan 分解
### 4.1. Jordan分解
对可测空间$(X, \mathscr{F})$上的符号测度$\varphi$, 存在测度$\varphi^+$和有限测度$\varphi^-$, 使得
$$
\varphi = \varphi^+ - \varphi^-
$$
成立, 并且
$$
\begin{aligned} 
\varphi^+(A) &= \sup\{\varphi(B)\mid B\subset A. B\in \mathscr{F}\}\\
\varphi^-(A) &= \sup\{-\varphi(B)\mid B\subset A. B\in \mathscr{F}\}
\end{aligned}
$$
我们把$\varphi^+$和$\varphi^-$分别称为$\varphi$的上变差和下变差, 而$|\varphi| = \varphi^+ +\varphi^-$叫做它的全变差. 

## 5. Radon-Nikodym导数
### 5.1. Radon-Nikodym导数
设$\varphi$是测度空间$(X, \mathscr{F}, \mu)$上的符号测度, 如果在a.e.的意义下存在唯一的可测函数$f$使得
$$
\varphi(A) = \int_A f\mathrm{d}\mu , \quad \forall A\in \mathscr{F}
$$
成立, 则称$f$为$\varphi$对于$\mu$的Radon-Nikodym导数, 记为$\dfrac{\mathrm{d}\varphi}{\mathrm{d}\mu} = f$. 

### 5.2. 绝对连续