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

## 3. Borel集
### 3.1. $F_{\sigma}, G_{\delta}$集
若$E\subset \mathbb{R}^n$是可数个闭集的并集, 则称$E$是$F_{\sigma}$集, 若$E\subset \mathbb{R}^n$是可数个开集的交集, 则称$E$是$G_{\delta}$集.

### 3.2. Baire定理
设$E\subset \mathbb{R}^n$是$F_{\sigma}$集, 即$E = \bigcup\limits_{k=1}^nF_k$, $F_k$是闭集, 若每个$F_K$均无内点, 则$E$也没有内点. 

### 3.3. 稠密集和纲
设$E\subset \mathbb{R}^n$, 若$\bar{E}=\mathbb{R}^n$, 则称$E$是$\mathbb{R}^n$中的稠密集; 若$\bar{E}^{\circ}=\varnothing$, 则称$E$是$\mathbb{R}^n$中的无处稠密集. 可数个无处稠密集的并集称为贫集或第一纲集, 不是第一纲集称为第二纲集.