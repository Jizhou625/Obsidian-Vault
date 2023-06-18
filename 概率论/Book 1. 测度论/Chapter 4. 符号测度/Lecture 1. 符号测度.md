## 1. 符号测度
### 1.1. 符号测度的定义
设$(X, \mathscr{F})$是一个可测空间, 从$\mathscr{F}$到$\overline{\mathbb{R}}$的集函数$\varphi$, 如果满足
1. **空集为0**: $\varphi(\varnothing)=0$
2. **可列可加性**: 对任何两两不交的$\{A_n\}\subset \mathscr{F}$, 有
   $$
   \varphi\left(\bigcup\limits_{n=1}^{\infty} A_n\right) = \sum\limits_{n=1}^{\infty} \varphi(A_n)
   $$

如果符号测度$\varphi$满足$|\varphi(A)|<\infty, \forall A\in \mathscr{F}$, 则称它是有限的. 如果存在$X$的可测分割$\{A_n\}$, 使得$|\varphi(A_n)|<\infty$, 则称$\varphi$是$\sigma$-有限的.

### 1.2. 符号测度与不定积分
测度空间$(X, \mathscr{F}, \mu)$上积分存在的可测函数$f$的不定积分
$$
\varphi(A) = \int_A f\mathrm{d}\mu, \quad \forall A\in \mathscr{F}
$$
是一个符号测度.

### 1.3. 符号测度的性质
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
   则
   $$
   \sum\limits_{n=1}^{\infty} |\varphi(A_n)| < \infty
   $$

___
##### Proof
1. 用反证法, 如果存在$A, B\in \mathscr{F}$, 使得$\varphi(A) = \infty$和$\varphi(B) = - \infty$, 则
   $$
   \begin{aligned}
   & \varphi(A \cup B)=\varphi(A)+\varphi(B \backslash A) ; \\
   & \varphi(A \cup B)=\varphi(B)+\varphi(A \backslash B) .
   \end{aligned}
   $$
   由于 $\varphi(A)=\infty$, 要保证前一式有意义必须有 $\varphi(A \cup B)=\infty$; 由于 $\varphi(B)=-\infty$, 要保证后一式有意义必须有 $\varphi(A \cup B)=-\infty$. 矛盾!
2. 易得 $\varphi(A)=\varphi(B)+\varphi(A \backslash B)$. 因此, 如果 $\varphi(A)$ 有限, 则 $\varphi(B)$ 必须有限.
3. 对每个 $n=1,2, \cdots$, 令
   $$
   \begin{aligned}
   & A_n^{+}= \begin{cases}A_n, & \varphi\left(A_n\right)>0, \\
   \varnothing, & \varphi\left(A_n\right) \leqslant 0,\end{cases} \\
   & A_n^{-}= \begin{cases}\varnothing, & \varphi\left(A_n\right)>0, \\
   A_n, & \varphi\left(A_n\right) \leqslant 0 .\end{cases}
   \end{aligned}
   $$
   易见 
   $$
   \bigcup_{n=1}^{\infty} A_n=\bigcup_{n=1}^{\infty} A_n^{+} \cup \bigcup_{n=1}^{\infty} A_n^{-}
   $$
   且 $\left\{A_n^{+}, A_n^{-}, n=1,2, \cdots\right\}$ 两两不交. 但由命题 2 及条件 $\left|\varphi\left(\bigcup\limits_{n=1}^{\infty} A_n\right)\right|<\infty$ 可知
   $$
   \left|\varphi\left(\bigcup_{n=1}^{\infty} A_n^{+}\right)\right|<\infty \text { and }\left|\varphi\left(\bigcup_{n=1}^{\infty} A_n^{-}\right)\right|<\infty
   $$
   成立, 故
   $$
   \begin{aligned}
   \sum_{n=1}^{\infty}\left|\varphi\left(A_n\right)\right| & =\sum_{n=1}^{\infty}\left[\varphi\left(A_n^{+}\right)+\left|\varphi\left(A_n^{-}\right)\right|\right] \\
   & =\sum_{n=1}^{\infty} \varphi\left(A_n^{+}\right)+\sum_{n=1}^{\infty}\left|\varphi\left(A_n^{-}\right)\right| \\
   & =\left|\sum_{n=1}^{\infty} \varphi\left(A_n^{+}\right)\right|+\left|\sum_{n=1}^{\infty} \varphi\left(A_n^{-}\right)\right| \\
   & =\left|\varphi\left(\bigcup_{n=1}^{\infty} A_n^{+}\right)\right|+\left|\varphi\left(\bigcup_{n=1}^{\infty} A_n^{-}\right)\right| \\ 
   &<\infty 
   \end{aligned}
   $$
#####
___




## 2. Hahn分解与Jordan分解
### 2.1. 符号测度的正部

设 $\varphi$ 是一个符号测度. 对任意的 $A \in \mathscr{F}$, 记
$$
\varphi^*(A)=\sup \{\varphi(B): B \subset A, B \in \mathscr{G}\} .
$$
不难看出: $\varphi^*$ 是 $\mathscr{F}$ 上非负,单调且满足 $\varphi^*(\varnothing)=0$ 的集函数, 我们称$\varphi^*$为符号测度$\varphi$的正部. 

### 2.2. 
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