## 1. 极限点和导集
### 1.1. 极限点和导集的定义
设$E\subset \mathbb{R}^n, \boldsymbol{x}\in \mathbb{R}^n$, 若存在$E$中的互异点列$\{\boldsymbol{x}_k\}$使得
$$
\lim\limits_{k\to\infty}\|\boldsymbol{x}_k - \boldsymbol{x}\| = 0
$$
则称$\boldsymbol{x}$为$E$的极限点, $E$的极限点的全体记为$E^{\prime}$, 称为$E$的导集. 

### 1.2. 极限点的判定
若$E\subset \mathbb{R}^n$, 则$\boldsymbol{x}\in E^{\prime}$当且仅当对任意的$\delta>0$, 有
$$
(\mathbb{B}(\boldsymbol{x}, \delta)\backslash \{\boldsymbol{x}\})\cap E \neq \varnothing
$$

### 1.3. 并集的导集等于导集的并集
设$E_1, E_2\subset \mathbb{R}^n$, 则
$$
(E_1\cup E_2)^{\prime} = E_1^{\prime}\cup E_2^{\prime}
$$

### 1.4. Bolzano-Weierstrass 定理
$\mathbb{R}^n$中任意一个有界无限点集$E$至少有一个极限点.

## 2. $\mathbb{R}^n$中的基本点集
### 2.1. 开集
**Definition**: A subset $\mathcal{C}$ of $\mathbb{R}^n$ is called open, if for every $x \in \mathcal{C}$ there exists $\varepsilon>0$ such that the ball
$$
B_{\varepsilon}(\boldsymbol{x})=\left\{\boldsymbol{y} \mid\|\boldsymbol{y}-\boldsymbol{x}\|_2 \leq \varepsilon\right\}
$$
is included in $\mathcal{C}$.

**Examples**:
$$\{x \mid a<x<b\},\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\},\{\boldsymbol{x} \mid \boldsymbol{x}>\mathbf{0}\}, \mathbb{S}_{++}^n=\{X \mid X \succ \mathbf{0}\}$$

**运算性质**
1. 任意多个开机的并集还是开集, 也就是说, 若$\{G_{\alpha}\mid \alpha\in I\}$是$\mathbb{R}^n$中的一个开集族, 则其并集$G = \bigcup\limits_{\alpha\in I}G_{\alpha}$是开集. 
2. 有限个开集的交还是开集, 也就是说, 若$G_1, G_2, \cdots, G_k$是$\mathbb{R}^n$中的开集, 则$G = \bigcap\limits_{i=1}^kG_i$也是开集. 但是, 无限个开集的交不一定是开集. 考虑集合列$\left\{G_k = \left(0, 1 +\dfrac{1}{n}\right)\right\}$, 我们有$\bigcap\limits_{k=1}^{\infty}G_k = \left(0, 1\right]$不是开集

**开集的构造**: 
1. $\mathbb{R}$中的非空开集是由可数个互不相交的开区间的并集, 这里的开区间也包括无穷开区间.
2. $\mathbb{R}^n$中的非空开集$G$是由可列个互不相交的半开半闭方体的并集
___
##### Proof: 

1. 设$G$是$\mathbb{R}$中的开集, 对于$G$中的任意一点$a$, 由于$a$是$G$的内点, 因此存在$\varepsilon>0$使得$(a-\varepsilon, a+\varepsilon)\subset G$. 现在设
   $$
   a^{\prime} = \inf\{x\mid (x, a)\subset G\}, \quad a^{\prime\prime} = \inf\{x\mid (a, x)\subset G\}
   $$
   显然$a^{\prime}<a< a^{\prime\prime}$且$(a^{\prime}, a^{\prime\prime})\subset G$. 我们称这样的开区间$(a^{\prime}, a^{\prime\prime})$为$G$关于点$a$的构成区间$I_{a}$. 考虑构成区间$I_a$和$I_b$, 不妨设$a<b$. 若有$I_a\cap I_b\neq \varnothing$, 则有$b^{\prime}< a^{\prime\prime}$, 取$x\in I_a\cap I_b$, 则有$I_x = I_a=I_b$, 这就证明了所有的构成区间或者重合, 或者互不相交. 最后, 我们知道$\mathbb{R}$中互不相交的区间族是可数的(有理数是可数的). 
2. 

### 2.2. 闭集
**Definition**: A subset $\mathcal{C}$ of $\mathbb{R}^n$ is called closed, if its complement $\mathcal{C}^c=\mathbb{R}^n \backslash \mathcal{C}$ is open.

**Examples**:
$$
\{x \mid a \leq x \leq b\},\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\},\{\boldsymbol{x} \mid \boldsymbol{x} \geq \mathbf{0}\}, \mathbb{S}_{+}^n=\{X \mid X \succeq \mathbf{0}\}
$$

**运算性质**: 
1. 有限多个闭集的并集还是闭集, 也就是说, 如果$F_1, F_2, \cdots, F_k$是$\mathbb{R}^n$中的闭集, 则其并集$\bigcup\limits_{i=1}^{k}F_i$也是闭集. 但是, 可数个闭集的并未必是闭集. 考虑集合列$\left\{F_k = \left[\dfrac{1}{n}, 1\right]\right\}$, 我们有$\bigcup\limits_{k=1}^{\infty}F_k = \left(0, 1\right]$不是闭集
2. 任意多个闭集的交集仍然是闭集. 也就是说, 如果$\{F_{\alpha}\mid \alpha \in I\}$是$\mathbb{R}^n$中的一个闭集族, 则其交集$F = \bigcap\limits_{\alpha\in I}F_{\alpha}$是闭集. 

### 2.3. 有界集
**Definition**: A subset $\mathcal{C}$ of $\mathbb{R}^n$ is called bounded, if $\exists R>0$ such that $\|\boldsymbol{x}\|<R,\ \forall \boldsymbol{x} \in \mathcal{C}$.

**Examples**: 
$$
\{x \mid a \leq x<b\},\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\},\{\boldsymbol{x} \mid \mathbf{1}>\boldsymbol{x} \geq \mathbf{0}\},\{X \mid I \succeq X \succ 0\}
$$


### 2.4. 紧集
**Definition**: A subset $\mathcal{C}$ of $\mathbb{R}^n$ is called compact, if it is both bounded and closed.

**Examples**:
$$
\{x \mid a \leq x \leq b\},\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\},\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x} \geq \mathbf{0}\}, \mathbb{S}_{+}^n=\{X \mid I \succeq X \succeq \mathbf{0}\}
$$

**性质**: 

设$E\in\mathbb{R}^n$, 则$E$的任意一个开覆盖都包含有限子覆盖的充要条件是$E$是紧集.
### 2.5. 内点集
**Definition**: The interior of $\mathcal{C} \subseteq \mathbb{R}^n$ is defined as $\mathcal{C}^{\circ}=\left\{\boldsymbol{y} \mid \exists \varepsilon>0\right.$ such that $\left.\mathcal{B}_{\varepsilon}(\boldsymbol{y}) \subset \mathcal{C}\right\}$

**Examples**: 
$$
\begin{gathered}
(\{x \mid a \leq x \leq b\})^{\circ}=\{x \mid a<x<b\} \\
(\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\})^{\circ}=\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\} \\
(\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x} \geq \mathbf{0}\})^{\circ}=\{\boldsymbol{x} \mid \mathbf{1}>\boldsymbol{x}>\mathbf{0}\} \\
(\{X \mid I \succeq X \succeq 0\})^{\circ}=\{X \mid I \succ X \succ 0\}
\end{gathered}
$$


### 2.6. 闭包
**Definition**: The closure of $\mathcal{C} \subset \mathbb{R}^n$ is defined as
$$
\overline{\mathcal{C}}=\mathbb{R}^n \backslash\left(\mathbb{R}^n \backslash \mathcal{C}\right)^{\circ}=\left(\left(\mathcal{C}^c\right)^{\circ}\right)^c
$$
**Examples**: 
$$
\begin{gathered}
\overline{\{x \mid a \leq x<b\}}=\{x \mid a \leq x \leq b\} \\
\overline{\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\}}=\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\} \\
\overline{\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x}>\mathbf{0}\}}=\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x} \geq \mathbf{0}\} \\
\overline{\{X \mid I \succ X \succ 0\}}=\{X \mid I \succeq X \succeq 0\}
\end{gathered}
$$


### 2.7. 边界点集
**Definition**: The boundary of $\mathcal{C} \subseteq \mathbb{R}^n$ is defined as $\partial \mathcal{C}=\overline{\mathcal{C}} \backslash \mathcal{C}^{\circ}$.

**Examples**: 
$$
\begin{gathered}
\partial(\{x \mid a \leq x<b\})=\{a, b\} \\
\partial(\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\})=\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|=1\}\\
\partial(\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x}>\mathbf{0}\})=\left\{\boldsymbol{x} \mid 0 \leq x_i \leq 1 . \forall i, \text { and } \exists j \text { such that } x_j=0 \text { or } 1\right\} \\ 
\partial(\{X \mid I \succ X \succ 0\})=\left\{X \mid 0 \leq \lambda_i(X) \leq 1, \forall i \text { and } \exists j \text { such that } \lambda_j(X)=0 \text { or } 1\right\}
\end{gathered}
$$





## 3. 函数的closedness
### 3.1. 函数闭的定义
A function $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is said to be closed if, for each $\alpha \in \mathbb{R}$, the sublevel set
$$
\{\boldsymbol{x} \in \operatorname{dom} f \mid f(\boldsymbol{x}) \leq \alpha\}
$$
is closed. This is equivalent to the condition that the epigraph of $f$
$$
\text { epi } f=\left\{(\boldsymbol{x}, t) \in \mathbb{R}^{n+1} \mid \boldsymbol{x} \in \operatorname{dom} f, f(\boldsymbol{x}) \leq t\right\}
$$
is closed.

### 3.2. 函数闭的判定
1. If $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is continuous, and $\operatorname{dom} f$ is closed, then $f$ is closed.

2. If $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is continuous, with $\operatorname{dom} f$ open, then $f$ is closed iff $f$ converges to $\infty$ along every sequence converging to a boundary point of $\operatorname{dom} f$. In other words
   $$
   \lim _{n \rightarrow \infty} \boldsymbol{x}_n=\boldsymbol{x} \in \partial(\operatorname{dom} f), \quad \boldsymbol{x}_n \in \operatorname{dom} f
   $$
   Then
   $$
   \lim _{n \rightarrow \infty} f\left(\boldsymbol{x}_n\right)=\infty
   $$
   

