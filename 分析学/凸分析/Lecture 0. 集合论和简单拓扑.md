## 1. 集合基础
### 1.1. 集合的运算性质
1. 交换律: 
   $$
   A \cap B=B \cap A,\quad  A \cup B=B \cup A
   $$
2. 结合律: 
   $$
   A \cap (B \cap C)=(A \cap B) \cap C,\quad A \cup (B \cup C)=(A \cup B) \cup C
   $$
3. 分配律: 
   $$
   A \cap (B \cup C)=(A \cap B) \cup (A \cap C),\quad A \cup (B \cap C)=(A \cup B) \cap (A \cup C)
   $$
4. De. Morgan's Law: 
   $$
   \left(\bigcup_{\alpha\in I} A_{\alpha}\right)^c=\bigcap_{\alpha\in I}A^c_{\alpha},\quad  \left(\bigcap_{\alpha\in I} A_{\alpha}\right)^c=\bigcup_{\alpha\in I}A^c_{\alpha}
   $$

### 1.2. 集合的极限
1. **极限集**: 设$\{A_k\}$是一个集合列, 若
   $$
   A_1\supset A_2\supset \cdots\supset A_k\supset \cdots
   $$
   则称此集合列为递减集合列, 此时称其交集$\bigcap\limits_{k=1}^{\infty}A_k$为集合列$\{A_k\}$的极限集, 记作$\lim\limits_{k\to\infty} A_k$. 若$\{A_k\}$满足
   $$
   A_1\subset A_2\subset \cdots\subset A_k\subset \cdots
   $$
   则称此集合列为递增集合列, 此时称其交集$\bigcup\limits_{k=1}^{\infty}A_k$为集合列$\{A_k\}$的极限集, 记作$\lim\limits_{k\to\infty} A_k$. 
2. **上下极限集**: 设$\{A_k\}$是一个集合列, 令
   $$
   B_j = \bigcup_{k=j}^{\infty}A_k, \quad j=1,2,\cdots
   $$
   显然有$B_j\supset B_{j+1}, j=1,2,\cdots$, 我们称
   $$
   \lim\limits_{k\to\infty} B_k = \bigcap_{j=1}^{\infty}B_j = \bigcap_{j=1}^{\infty}\bigcup_{k=j}^{\infty}A_k 
   $$
   为集合列$\{A_k\}$的上极限集, 简称上限集, 记为
   $$
   \varlimsup_{k\to\infty}A_k = \bigcap_{j=1}^{\infty}\bigcup_{k=j}^{\infty}A_k 
   $$
   类似地, 称集合$\bigcup\limits_{j=1}^{\infty}\bigcap\limits_{k=j}^{\infty}A_k$为集合列$\{A_k\}$的下极限集, 简称下限集, 记为
   $$
   \varliminf_{k\to\infty}A_k = \bigcup_{j=1}^{\infty}\bigcap_{k=j}^{\infty}A_k 
   $$
   事实上, 我们可以从集合元素的角度来刻画上极限集和下极限集
   $$
   \varlimsup_{k\to\infty}A_k = \{x\mid \forall j\in \mathbb{N}, \exists k\ge j, x\in A_k\}
   $$
   $$
   \varliminf_{k\to\infty}A_k = \{x\mid \exists j_0, \forall k\ge j_0, x\in A_k\}
   $$

### 1.3. 映射与像集
我们有如下的事实
1. $f\left(\bigcup\limits_{\alpha\in I}A_{\alpha}\right) = \bigcup\limits_{\alpha\in I}f(A_{\alpha})$, $f\left(\bigcap\limits_{\alpha\in I}A_{\alpha}\right) \subset \bigcap\limits_{\alpha\in I}f(A_{\alpha})$
2. 若$B_1\subset B_2$, 则$f^{-1}(B_1)\subset f^{-1}(B_2)$
3. $f^{-1}\left(\bigcup\limits_{\alpha\in I}B_{\alpha}\right) = \bigcup\limits_{\alpha\in I}f^{-1}(B_{\alpha})$, $f^{-1}\left(\bigcap\limits_{\alpha\in I}B_{\alpha}\right) = \bigcap\limits_{\alpha\in I}f^{-1}(B_{\alpha})$
4. $f^{-1}(B^c) = \left(f^{-1}(B)\right)^c$

## 2. 集合的基数
### 2.1. 对等和基数
设有集合$A$与$B$, 若存在一个从$A$到$B$上的一一映射, 则称集合$A$与集合$B$对等, 记为$A\sim B$, 如果$A\sim B$, 我们就说$A$与$B$的基数(cardinal number)或势是相同的. 几种常见的基数有
1. 自然数集$\mathbb{N}$的基数(可列集)
2. $\mathbb{R}$的基数(不可数集)

### 2.2. 集合在映射下的分解
若有$f: X\to Y$, $g:Y\to X$, 则存在分解
$$
X= A\cup A^{\sim}, \quad Y = B\cup B^{\sim}, \quad A\cap A^{\sim} = B\cap B^{\sim} = \varnothing
$$
其中$f(A) = B, g(B^{\sim}) = A^{\sim}$
___
**Proof**: 对于$X$中的子集$E$(不妨假定$Y\backslash f(E)\neq \varnothing$), 若满足
$$
E\cap g(Y\backslash f(E)) = \varnothing
$$
则称$E$为$X$中的分离集. 现在将$X$中的分离集的全体记为$\Gamma$, 显然$\varnothing\in \Gamma$, 因此$\Gamma$非空. 作并集
$$
A = \bigcup_{E\in \Gamma} E
$$
容易证明$A\in X$, 因此$A$是分离集$\Gamma$中的最大元. 现在设$f(A) = B$, $Y\backslash B = B^{\sim}$以及$g(B^{\sim}) = A^{\sim}$. 

用反证法, 如果$A\cup A^{\sim}\neq X$, 则存在$x_0\in X$但$x_0\notin A\cup A^{\sim}$. 现在设$A_0 = A\cup\{x_0\}$, 我们有
$$
B = f(A)\subset f(A_0), \quad B^{\sim} \supset Y\backslash f(A_0)
$$
从而我们有
$$
A^{\sim} = g(B^{\sim})\supset g(Y\backslash f(A_0)) 
$$
因为$A\cap A^{\sim} = \varnothing$, 且$\{x_0\}\notin A^{\sim}$, 因此
$$
A_0\cap g(Y\backslash f(A_0)) = \varnothing
$$
这和$A$是$\Gamma$中的最大元矛盾! 于是我们得到了$A\cup A^{\sim} = X$. 
### 2.3. Cantor-Bernstein 定理
若集合$X$与$Y$的某个真子集对等, $Y$与$X$的某个真子集对等, 则$X\sim Y$
___
**Proof**: 根据题设可以得到存在单射$f:X\to Y$和单射$g: Y\to X$, 根据[[#2.2. 集合在映射下的分解]], 存在分解
$$
X = A\cup A^{\sim},\quad  Y = B\cup B^{\sim}, \quad f(A) = B, \quad g(B^{\sim}) = A^{\sim}
$$
由于这里的$f: A\to B$和$g^{-1}: A^{\sim}\to B^{\sim}$是一一映射, 因此可以作$X$到$Y$上的一一映射$F$
$$
F(x) = \begin{cases} f(x), \quad & x\in A \\ g^{-1}(x), & x\in A^{\sim}  \end{cases}
$$
这说明了$X\sim Y$

### 2.4. 可列集的性质
1. 任何一个无限集$E$必然包含一个可列子集
2. 若$A_n,\ n=1,2,3,\cdots$为可列集, 则并集
   $$
   A = \bigcup_{n=1}^{\infty}A_n
   $$
   也是可列集
3. 设$A$是无限集且其基数为$\alpha$, 若$B$是至多可列集, 则$A\cup B$的基数仍然为$\alpha$
4. 集合$A$为无限集的充分必要条件是$A$与其某个真子集对等. 

### 2.5. 连续基数
我们称$[0,1]$的基数为连续基数. 设有集合列$\{A_k\}$, 若每个$A_k$的基数都是连续基数, 则其并集$\bigcup\limits_{k=1}^{\infty}A_k$的基数是连续基数. 

### 2.6. 无最大基数定理
若$A$是非空集合, 则$A$与其幂集$\mathscr{P}(A)$不对等. 
___
**Proof**: 假设$A$与其幂集$\mathscr{P}(A)$对等, 即存在一个一一映射$f: A\to\mathscr{P}(A)$, 我们作集合
$$
B = \{x\in A\mid x\notin f(x)\}
$$
显然$B\subset A\implies B\in \mathscr{P}(A)$. 于是根据假设, 存在$y\in A, f(y)=B$. 
1. 若$y\in B$, 则由$B$的定义可以得到, $y\notin f(y) = B$, 矛盾!
2. 若$y\notin B$, 则根据$B$的定义可以得到, $y\in f(y) = B$, 矛盾!
   
这导致了矛盾! 因此$A$与其幂集$\mathscr{P}(A)$不对等



## 3. 极限点和导集
### 3.1. 极限点和导集的定义
设$E\subset \mathbb{R}^n, \boldsymbol{x}\in \mathbb{R}^n$, 若存在$E$中的互异点列$\{\boldsymbol{x}_k\}$使得
$$
\lim\limits_{k\to\infty}\|\boldsymbol{x}_k - \boldsymbol{x}\| = 0
$$
则称$\boldsymbol{x}$为$E$的极限点, $E$的极限点的全体记为$E^{\prime}$, 称为$E$的导集. 

### 3.2. 极限点的判定
若$E\subset \mathbb{R}^n$, 则$\boldsymbol{x}\in E^{\prime}$当且仅当对任意的$\delta>0$, 有
$$
(\mathbb{B}(\boldsymbol{x}, \delta)\backslash \{\boldsymbol{x}\})\cap E \neq \varnothing
$$

### 3.3. 并集的导集等于导集的并集
设$E_1, E_2\subset \mathbb{R}^n$, 则
$$
(E_1\cup E_2)^{\prime} = E_1^{\prime}\cup E_2^{\prime}
$$

### 3.4. Bolzano-Weierstrass 定理
$\mathbb{R}^n$中任意一个有界无限点集$E$至少有一个极限点.

## 4. $\mathbb{R}^n$中的基本点集
### 4.1. 开集
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
**Proof**: 
1. 设$G$是$\mathbb{R}$中的开集, 对于$G$中的任意一点$a$, 由于$a$是$G$的内点, 因此存在$\varepsilon>0$使得$(a-\varepsilon, a+\varepsilon)\subset G$. 现在设
   $$
   a^{\prime} = \inf\{x\mid (x, a)\subset G\}, \quad a^{\prime\prime} = \inf\{x\mid (a, x)\subset G\}
   $$
   显然$a^{\prime}<a< a^{\prime\prime}$且$(a^{\prime}, a^{\prime\prime})\subset G$. 我们称这样的开区间$(a^{\prime}, a^{\prime\prime})$为$G$关于点$a$的构成区间$I_{a}$. 考虑构成区间$I_a$和$I_b$, 不妨设$a<b$. 若有$I_a\cap I_b\neq \varnothing$, 则有$b^{\prime}< a^{\prime\prime}$, 取$x\in I_a\cap I_b$, 则有$I_x = I_a=I_b$, 这就证明了所有的构成区间或者重合, 或者互不相交. 最后, 我们知道$\mathbb{R}$中互不相交的区间族是可数的(有理数是可数的). 
2. 

### 4.2. 闭集
**Definition**: A subset $\mathcal{C}$ of $\mathbb{R}^n$ is called closed, if its complement $\mathcal{C}^c=\mathbb{R}^n \backslash \mathcal{C}$ is open.

**Examples**:
$$
\{x \mid a \leq x \leq b\},\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\},\{\boldsymbol{x} \mid \boldsymbol{x} \geq \mathbf{0}\}, \mathbb{S}_{+}^n=\{X \mid X \succeq \mathbf{0}\}
$$

**运算性质**: 
1. 有限多个闭集的并集还是闭集, 也就是说, 如果$F_1, F_2, \cdots, F_k$是$\mathbb{R}^n$中的闭集, 则其并集$\bigcup\limits_{i=1}^{k}F_i$也是闭集. 但是, 可数个闭集的并未必是闭集. 考虑集合列$\left\{F_k = \left[\dfrac{1}{n}, 1\right]\right\}$, 我们有$\bigcup\limits_{k=1}^{\infty}F_k = \left(0, 1\right]$不是闭集
2. 任意多个闭集的交集仍然是闭集. 也就是说, 如果$\{F_{\alpha}\mid \alpha \in I\}$是$\mathbb{R}^n$中的一个闭集族, 则其交集$F = \bigcap\limits_{\alpha\in I}F_{\alpha}$是闭集. 

### 4.3. 有界集
**Definition**: A subset $\mathcal{C}$ of $\mathbb{R}^n$ is called bounded, if $\exists R>0$ such that $\|\boldsymbol{x}\|<R,\ \forall \boldsymbol{x} \in \mathcal{C}$.

**Examples**: 
$$
\{x \mid a \leq x<b\},\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\},\{\boldsymbol{x} \mid \mathbf{1}>\boldsymbol{x} \geq \mathbf{0}\},\{X \mid I \succeq X \succ 0\}
$$


### 4.4. 紧集
**Definition**: A subset $\mathcal{C}$ of $\mathbb{R}^n$ is called compact, if it is both bounded and closed.

**Examples**:
$$
\{x \mid a \leq x \leq b\},\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\},\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x} \geq \mathbf{0}\}, \mathbb{S}_{+}^n=\{X \mid I \succeq X \succeq \mathbf{0}\}
$$

**性质**: 

设$E\in\mathbb{R}^n$, 则$E$的任意一个开覆盖都包含有限子覆盖的充要条件是$E$是紧集.
### 4.5. 内点集
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


### 4.6. 闭包
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


### 4.7. 边界点集
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


## 5. Borel集
### 5.1. $F_{\sigma}, G_{\delta}$集
若$E\subset \mathbb{R}^n$是可数个闭集的并集, 则称$E$是$F_{\sigma}$集, 若$E\subset \mathbb{R}^n$是可数个开集的交集, 则称$E$是$G_{\delta}$集.







### 8. Closedness for function
**Definition**: A function $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is said to be closed if, for each $\alpha \in \mathbb{R}$, the sublevel set
$$
\{\boldsymbol{x} \in \operatorname{dom} f \mid f(\boldsymbol{x}) \leq \alpha\}
$$
is closed. This is equivalent to the condition that the epigraph of $f$
$$
\text { epi } f=\left\{(\boldsymbol{x}, t) \in \mathbb{R}^{n+1} \mid \boldsymbol{x} \in \operatorname{dom} f, f(\boldsymbol{x}) \leq t\right\}
$$
is closed.
**Properties**: 
1. If $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is continuous, and $\operatorname{dom} f$ is closed, then $f$ is closed.

2. If $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is continuous, with dom $f$ open, then $f$ is closed iff $f$ converges to $\infty$ along every sequence converging to a boundary point of $\operatorname{dom} f$. In other words, if
   $$
   \lim _{i \rightarrow \infty} \boldsymbol{x}_i=\boldsymbol{x} \in \partial(\operatorname{dom} f), \quad \boldsymbol{x}_i \in \operatorname{dom} f
   $$
   Then
   $$
   \lim _{i \rightarrow \infty} f\left(\boldsymbol{x}_i\right)=\infty
   $$
   

