## 1. 测度
### 1.1. 测度的公理化定义
设 $\mathscr{E}$ 是 $X$ 上的集合系且$\varnothing \in \mathscr{E}$, 如果$\mu$满足
1. $\mu(\cdot)\ge 0$
2. $\mu(\varnothing)=0$
3. $\mu$ 具有可列可加性
   
则称$\mu$为 $\mathscr{E}$ 上的测度. 如果对每个$A\in \mathscr{E}$还有$\mu(A)<\infty$, 则称测度$\mu$是有限的. 

如果对每个$A\in \mathscr{E}$存在满足$\mu(A_n)<\infty$的$\{A_n\in \mathscr{E}\}$, 使得$\bigcup\limits_{n=1}^{\infty}A_n\supset A$, 则称测度$\mu$是$\sigma$有限的. 

### 1.2. 测度的性质
1. **有限可加性**: 设 $\mu$ 是 $\mathscr{E}$ 上的测度, 对$\mathscr{E}$中任意有限个两两不交且满足$\bigcup\limits_{i=1}^nA_i\in \mathscr{E}$的集合$A_1, A_2, \cdots, A_n$, 有
   $$
   \mu\left(\bigcup\limits_{i=1}^nA_i \right) = \sum\limits_{i=1}^{n}\mu(A_i) 
   $$
2. **可减性**: 设$\mu$ 是 $\mathscr{E}$ 上的测度, 对于任何的$A, B\in \mathscr{E}, \ A\subset B, B\backslash A\in \mathscr{E}$, 只要$\mu(A)<\infty$, 就有
   $$
   \mu(B\backslash A) = \mu(B) - \mu(A)
   $$
   
### 1.3. 测度空间
**测度空间**: 空间$X$, 加上由它的子集形成的一个$\sigma$域$\mathscr{F}$, 再加上$\mathscr{F}$上的一个测度$\mu$, 三位一体形成的$(X, \mathscr{F}, \mu)$被称为测度空间. 

**零测集**: 如果 $N \in \mathscr{F}$ 并且 $\mu(N)=0$, 则称 $N$ 为 $\mu$ 的零测集.

**概率空间**: 如果测度空间 $(X, \mathscr{F}, \mathbb{P})$ 满足 $\mathbb{P}(X)=1$, 则称它为概率空间, 对应的 $\mathbb{P}$ 叫作概率测度. 在概率空间 $(X, \mathscr{F}, \mathbb{P})$ 中, $\mathscr{F}$ 中的集合 $A$ 又称为事件, 而 $\mathbb{P}(A)$ 称为事件 $A$ 发生的概率. 

## 2. 半环上的测度
### 2.1. 准分布函数$F$构造的测度
设$X=\mathbb{R}$, $\mathscr{E} = \mathscr{Q}_{\mathbb{R}}$, 而$F$是$\mathbb{R}$上的非降右连续的实值函数(准分布函数). 对任意的$a, b\in \mathbb{R}$, 设
$$
\mu((a, b]) = \begin{cases}  F(b) - F(a) , \quad & a<b \\ 0, \quad & a\ge b \end{cases}
$$
则$\mu$是$\mathscr{E}$上的测度.
___
##### Proof: 
不难证明$\mu(\varnothing)=0$, 因此我们只要验证$\mu$具有可列可加性. 
1. 首先, 我们不难证明$\mu$是有限可加的
2. 其次, 如果$(a_i, b_i)\in \mathscr{Q}_{\mathbb{R}}$两两不交并且
   $$
   \bigcup\limits_{i=1}^{\infty} (a_i, b_i] \subset (a, b]
   $$
   容易证明对任意的$n\ge 1$, 都有
   $$
   \mu((a, b])\ge \sum\limits_{i=1}^{n} \mu((a_i, b_i])
   $$
   取$n\to\infty$可以得到
   $$
   \mu((a, b])\ge \sum\limits_{i=1}^{\infty} \mu((a_i, b_i])\tag{2.1.1}
   $$
3. 如果$(a_i, b_i)\in \mathscr{Q}_{\mathbb{R}}$两两不交并且
   $$
   \bigcup\limits_{i=1}^{\infty} (a_i, b_i] = (a, b]
   $$
   对任意的$\varepsilon>0$, 根据$F$的右连续性, 我们可以找到$\delta_i>0$, 使得
   $$
   F(b_i+\delta_i) - F(b_i) < \frac{\varepsilon}{2^i}
   $$
   于是, 对任意的$\eta>0$, 开区间列$\{(a_i, b_i+\delta_i)\}$形成了闭区间$[a+\eta, b]$的一个开覆盖, 因此, 存在$n$使得
   $$
   \bigcup\limits_{i=1}^{n} (a_i, b_i+\delta_i]\supset [a+\eta, b]\supset (a+\eta, b]
   $$
   于是, 我们有
   $$
   \begin{aligned} 
      F(b) - F(a+\eta)&\le  \sum\limits_{i=1}^{n}[F(b_i+\delta_i) - F(a_i)] \\ 
      & \le \sum\limits_{i=1}^{n}[F(b_i) - F(a_i)] +  \varepsilon \\ 
      &\le \sum\limits_{i=1}^{\infty}\mu((a_i, b_i]) +\varepsilon  
   \end{aligned}
   $$
   在这里, 先令$\eta\to 0$, 由$F$的右连续性, 可以得到
   $$
   \mu((a, b]) = F(b) - F(a)\le \sum\limits_{i=1}^{\infty}\mu((a_i, b_i]) +\varepsilon
   $$
   再令$\varepsilon\to 0$, 可以得到
   $$
   \mu((a, b])\le \sum\limits_{i=1}^{\infty}\mu((a_i, b_i])  \tag{2.1.2}
   $$
   结合$(2.1.1)$和$(2.1.2)$, 我们证明了$\mu$是可列可加的, 因此$\mu$是$\mathscr{E}$上的测度.
#####
___

### 2.2. 半环上测度的性质
半环上的测度具有单调性, 可减性, 半可列可加性, 下连续性和上连续性. 其中各个性质的严格定义分别为
1. **单调性**: 如果对任何 $A, B \in \mathscr{E}$ 且 $A \subset B$, 均有 $\mu(A) \leq \mu(B)$, 则称 $\mu$ 具有单调性
2. **可减性**: 如果对任何 $A, B \in \mathscr{E}, A\subset B$, $B\backslash A\in \mathscr{E}$, 只要$\mu(A)<\infty$, 就有
   $$
   \mu(B\backslash A) = \mu(B) - \mu(A)
   $$
   则称非负集函数 $\mu$ 具有可减性. 
3. **半可列可加性**: 如果对任意可列个集合 $A_1, A_2, \cdots \in \mathscr{E}$, 只要 $\bigcup\limits_{n=1}^{\infty} A_n\in \mathscr{E}$ 就一定有
   $$
   \mu\left(\bigcup_{n=1}^{\infty} A_n\right) \leq \sum_{n=1}^{\infty} \mu\left(A_n\right)
   $$
   则称 $\mu$ 是半可列可加的
4. **下连续性**: 如果对任意 $A \in \mathscr{E}$, 只要 $A_n \uparrow A$ 就一定有
   $$
   \lim\limits_{n\to\infty} \mu(A_n) = \mu(A)
   $$
   则称 $\mu$ 具有下连续性
5. **上连续性**: 如果对任意 $A \in \mathscr{E}$, 只要 $A_n \downarrow A$ 且$\mu(A_1)<\infty$
   $$
   \lim\limits_{n\to\infty} \mu(A_n) = \mu(A)
   $$
   则称 $\mu$ 具有上连续性 

___
##### Proof: 
1. **单调性**: 设$A, B\in \mathscr{Q}$而且$A\subset B$, 则存在两两不交的集合$\{C_i\in \mathscr{Q}\}$, 使得$B\backslash A = \bigcup\limits_{i=1}^{n} C_i$, 于是
   $$
   B = A\cup (B\backslash A) = A \cup \bigcup\limits_{i=1}^{n} C_i
   $$
   由于测度具有有限可加性, 由有限可加性可以推出
   $$
   \mu(B) = \mu(A) +\sum\limits_{i=1}^{n} \mu(C_i) \ge \mu(A)
   $$
   单调性得证. 
2. **可减性**: 如果$B\backslash A \in\mathscr{Q}$且$\mu(A)<\infty$, 那么由
   $$
   \mu(B) = \mu(A) +\sum\limits_{i=1}^{n} \mu(C_i) 
   $$
   可以得到
   $$
   \mu(B\backslash A) = \sum\limits_{i=1}^{n} \mu(C_i) = \mu(B) - \mu(A)
   $$
   可减性得证. 
3. **半可列可加性**: 由于$\varnothing\in \mathscr{Q}$, 故由可列可加性
   $$
   \mu(\varnothing) = \mu(\varnothing) + \mu(\varnothing) + \cdots
   $$
   从而$\mu(\varnothing)=0$或$\infty$.  
   
   如果$\mu(\varnothing)=\infty$, 那么对任何$A\in \mathscr{Q}$均有
   $$
   \mu(A) = \mu(A) + \mu(\varnothing) + \mu(\varnothing) + \cdots
   $$
   从而$\mu(A)=\infty$, 无论如何都有半可列可加性, 上连续性和下连续性成立. 
   
   因此可以不妨设$\mu(\varnothing)=0$. 如果$A_1, A_2, \cdots\in \mathscr{Q}$且$\bigcup\limits_{n=1}^{\infty} A_n\in \mathscr{Q}$, 则由环的定义知道
   $$
   A_1, A_2, \cdots \in \mathscr{Q}\subset r(\mathscr{Q}) \Longrightarrow \bigcup\limits_{k=1}^{n-1} A_k \in r(\mathscr{Q}) \Longrightarrow A_n\Big\backslash \left(\bigcup\limits_{k=1}^{n-1} A_k \right) \in r(\mathscr{Q})
   $$
   于是存在两两不交的集合$\{C_{n, k}\in \mathscr{Q}\}$使得
   $$
   A_n\Big\backslash \left(\bigcup\limits_{k=1}^{n-1} A_k \right) = \bigcup\limits_{k=1}^{k_n} C_{n, k}
   $$
   运用同样的推理, 存在两两不交的集合$\{D_{n, l}\in \mathscr{Q}\}$, 使得
   $$
   A_n\Big\backslash \left(\bigcup\limits_{k=1}^{k_n} C_{n,k} \right) = \bigcup\limits_{i=1}^{l_n} D_{n, l}
   $$
   于是我们得到
   $$
   A_n = \bigcup\limits_{k=1}^{k_n} C_{n, k} \cup \bigcup\limits_{i=1}^{l_n} D_{n, l} 
   $$
   其中$\{C_{n, k}\in \mathscr{Q}\}$和$\{D_{n, l}\in \mathscr{Q}\}$两两不交. 这样, 由$\mu$的可列可加性
   $$
   \begin{aligned} 
      \mu\left(\bigcup\limits_{n=1}^{\infty} A_n\right) &= \mu\left(\bigcup\limits_{n=1}^{\infty} \left(A_n \Big\backslash \bigcup\limits_{i=1}^{n-1} A_{i}\right)\right) \\    
      & = \mu\left(\bigcup\limits_{n=1}^{\infty}\sum\limits_{k=1}^{k_n} C_{n, k} \right) \\    
      & = \sum\limits_{n=1}^{\infty} \sum\limits_{k=1}^{k_n} \mu(C_{n, k}) \\   
      & \le \sum\limits_{n=1}^{\infty} \left[\sum\limits_{k=1}^{k_n} \mu(C_{n, k}) + \sum\limits_{k=1}^{k_n} \mu(D_{n, k}) \right] \\    
      & = \sum\limits_{n=1}^{\infty} \mu(A_n)
      \end{aligned}
   $$
   
4. **下连续性**: 如果$A_1, A_2, \cdots \in \mathscr{Q}$, $A_n\uparrow A\in \mathscr{Q}$, 则存在两两不交的集合$\{C_{n, k}\in \mathscr{Q}\}$使得对每个$n=1,2,\cdots$, 有
   $$
   A_n \backslash A_{n-1} = \bigcup\limits_{k=1}^{k_n} C_{n, k}
   $$
   于是由测度的可列可加性和有限可加性
   $$
   \begin{aligned}    
   \mu(A) &= \mu\left(\bigcup\limits_{n=1}^{\infty} A_n\right) = \mu\left(\bigcup\limits_{n=1}^{\infty} (A_n\backslash A_{n-1})\right) = \sum\limits_{n=1}^{\infty} \sum\limits_{k=1}^{k_n} \mu(C_{n, k})  \\    
   & = \lim\limits_{N\to\infty} \sum\limits_{n=1}^{N} \sum\limits_{k=1}^{k_n} \mu(C_{n, k}) = \lim\limits_{N\to\infty} \mu\left(\bigcup\limits_{n=1}^{N} \bigcup\limits_{k=1}^{k_n} C_{n, k}\right) \\   
   & = \lim\limits_{N\to\infty} \mu(A_N)
   \end{aligned}
   $$

5. **上连续性**: 如果$A_1, A_2, \cdots \in \mathscr{Q}$, $A_n \downarrow A\in \mathscr{Q}$, 且$\mu(A_1)<\infty$, 则存在两两不交的集合$\{C_{n, k}\in \mathscr{Q}\}$使得对每个$n=1,2,\cdots$, 有
   $$
   A_n\backslash A_{n+1} = \bigcup\limits_{k=1}^{k_n} C_{n, k}
   $$
   易见
   $$
   \{A\in\mathscr{Q},  C_{n, k}\in \mathscr{Q}\mid k=1,2,\cdots, k_n;\  n=1,2,\cdots\}
   $$
   两两不交且
   $$
   A_n=\bigcup\limits_{i=n}^{\infty} (A_i\backslash A_{i+1})\cup A =\bigcup\limits_{i=n}^{\infty}\bigcup\limits_{k=1}^{k_i} C_{n, k}\cup A
   $$ 
   故由可列可加性得
   $$
   \mu(A_n) = \sum\limits_{i=n}^{\infty} \sum\limits_{k=1}^{k_i} \mu(C_{n, k}) + \mu(A)
   $$ 
   特别地, 当$n=1$时
   $$
   \sum\limits_{i=1}^{\infty} \sum\limits_{k=1}^{k_i} \mu(C_{n, k}) \le  \mu(A_1) <\infty
   $$
   从而
   $$
   \lim\limits_{n\to\infty} \sum\limits_{i=n}^{\infty} \sum\limits_{k=1}^{k_i} \mu(C_{n, k}) = 0
   $$
   这样就得到了
   $$
   \lim\limits_{n\to\infty} \mu(A_n) = \mu(A)
   $$
#####
___

### 2.3. 环上有限可加的非负集函数的性质
对于环$\mathscr{R}$上的有限可加非负集函数$\mu$, 有下面的结论成立:

$\mu$是可列可加 $\iff \mu$半可列可加 $\iff \mu$下连续 $\implies\mu$上连续 $\implies \mu$在$\varnothing$上连续, 即对任何满足$A_n\downarrow \varnothing$和$\mu(A_1)<\infty$的
   $\{A_n\in \mathscr{R}\}$有
   $$
   \lim\limits_{n\to\infty} \mu(A_n) = 0
   $$
如果$\mu$是有限的, 则上面的所有$\implies$全部变为$\iff$
___
##### Proof:  我们只证明部分结论

1. $\mu$半可列可加$\implies$ $\mu$可列可加: 如果$\{A_n\in \mathscr{R}\}$两两不交且$A = \bigcup\limits_{n=1}^{\infty} A_n\in \mathscr{R}$, 则由$\mu$的单调性和有限可加性知
   $$
   \mu(A)\ge \mu\left(\bigcup\limits_{n=1}^{N} A_n\right) =\sum\limits_{n=1}^{N} \mu(A_n)
   $$
   对每个$N=1,2,\cdots$成立, 从而
   $$
   \mu(A)\ge \sum\limits_{n=1}^{\infty} \mu(A_n)
   $$
   此式加上$\mu$的半可列可加性即得证
2. $\mu$下连续$\implies$ $\mu$可列可加: 如果$\{A_n\in \mathscr{R}\}$两两不交, 则
   $$
   \bigcup\limits_{n=1}^{N} A_n \uparrow \bigcup\limits_{n=1}^{\infty} A_n
   $$
   从而当$\bigcup\limits_{n=1}^{\infty} A_n\in \mathscr{R}$时由下连续性和有限可加性
   $$
   \mu\left(\bigcup\limits_{n=1}^{\infty} A_n\right) = \lim\limits_{N\to\infty} \mu\left(\bigcup\limits_{n=1}^{N} A_n\right) = \lim\limits_{N\to\infty} \sum\limits_{n=1}^{N} \mu(A_n) = \sum\limits_{n=1}^{\infty} \mu(A_n)
   $$
3. 当$\mu$是有限时, 如果$\{A_n\in \mathscr{R}\}$两两不交且$\bigcup\limits_{n=1}^{\infty} A_n\in\mathscr{R}$, 则
   $$
   \bigcup\limits_{n=N+1}^{\infty} A_n  = \bigcup\limits_{n=1}^{\infty} A_n \Big\backslash \bigcup\limits_{n=1}^{N} A_n \in \mathscr{R}
   $$
   从而由$\bigcup\limits_{n=1}^{\infty} A_n = \bigcup\limits_{n=1}^{N} A_n\cup \bigcup\limits_{n=N+1}^{\infty} A_n$和有限可加性得到
   $$
   \mu\left(\bigcup\limits_{n=1}^{\infty} A_n\right) = \sum\limits_{n=1}^{N}\mu(A_n) + \mu\left(\bigcup\limits_{n=N+1}^{\infty} A_n\right)
   $$
   由于$\mu$有限且在$\varnothing$上连续, 故$\bigcup\limits_{n=N+1}^{\infty} A_n\downarrow \varnothing$蕴含$\lim\limits_{N\to\infty} \mu\left(\bigcup\limits_{n=N+1}^{\infty} A_n\right) = 0$. 
#####
___
   
## 3. 外测度
### 3.1. 外测度的定义
由$X$的所有子集组成的集合系$\mathscr{T}$到$\overline{\mathbb{R}}$的函数$\tau$称为$X$上的外测度, 如果它满足

1. **空集测度为$\boldsymbol{0}$**: $\tau(\varnothing) = 0$
2. **单调性**: 对任何$A\subset B \subset X$有$\tau(A)\le \tau(B)$
3. **半可列可加性**: 对任何$\{A_n\in \mathscr{T}\}$有$\tau\left(\bigcup\limits_{n=1}^{\infty} A_n\right) \le \sum\limits_{n=1}^{\infty} \tau(A_n)$

### 3.2. 生成外测度
设$\mathscr{E}$是一个集合系且$\varnothing\in \mathscr{E}$, 如果$\mathscr{E}$上的非负集函数$\mu$满足$\mu(\varnothing)=0$. 对每个$A\in \mathscr{T}$, 设
$$
\tau(A) = \inf\left\{\sum\limits_{n=1}^{\infty} \mu(B_n)\mid B_n\in \mathscr{E}, \bigcup\limits_{n=1}^{\infty} B_n\supset A\right\}
$$
则$\tau$是一个外测度, 称为由$\mu$生成的外测度. 其中, 空集的下确界定义为$\infty$
___
##### Proof: 
不难验证, 生成的外测度$\tau$满足条件1和2. 下面证明其满足条件3. 我们只需要证明$\tau(A_n)<\infty$的情况. 取$\{B_{n,k}\in \mathscr{E}\}$使得$\bigcup\limits_{k=1}^{\infty} B_{n, k}\supset A_n$且
$$
\sum\limits_{k=1}^{\infty} \mu(B_{n, k}) < \tau(A_n)+ \dfrac{\varepsilon}{2^n}
$$
便有$\bigcup\limits_{n=1}^{\infty} \bigcup\limits_{k=1}^{\infty} B_{n, k}\supset \bigcup\limits_{n=1}^{\infty} A_n$, 从而
$$
\tau\left(\bigcup\limits_{n=1}^{\infty} A_n \right) \le \sum\limits_{n=1}^{\infty} \sum\limits_{k=1}^{\infty} \mu(B_{n,k})\le \sum\limits_{n=1}^{\infty} \tau(A_n) +\varepsilon
$$
由$\varepsilon$的任意性即得证
#####
___
### 3.3. $\tau$可测集和完全测度空间
**$\tau$可测集**: 设$\tau$是$X$上的外测度, $\mathscr{T}$是由$X$的所有子集组成的集合系, 我们把满足
$$
\tau(D) = \tau(D\cap A) + \tau(D\cap A^c), \quad \forall D\in \mathscr{T}
$$
的$X$的子集$A$称为$\tau$可测集, 把由全体$\tau$可测集组成的集合系记为$\mathscr{F}_{\tau}$. 

**完全测度空间**: 对于测度空间$(X, \mathscr{F}, \mu)$, 如果$\mu$的任意零测集合的子集还属于$\mathscr{F}$, 即
$$
A\in \mathscr{F}, \mu(A) = 0 \Longrightarrow B\subset \mathscr{F}, \forall B\subset A
$$
则称$(X, \mathscr{F}, \mu)$是完全测度空间. 

### 3.4. Caratheodory定理
如果$\tau$是外测度, $\mathscr{F}_{\tau}$是由全体$\tau$可测集组成的集合系, 则$\mathscr{F}_{\tau}$是一个$\sigma$代数, 且$(X, \mathscr{F}_{\tau}, \tau)$是完全测度空间. 
___
##### Proof: 
我们首先证明$\mathscr{F}_{\tau}$是一个$\sigma$-代数. 分为以下几个部分

1. $\mathscr{F}$是个域
   - $X \in \mathscr{F}_{\tau}$, 这是因为$\tau(D\cap X) +\tau(D\cap \varnothing) = \tau(D) +\tau(\varnothing) = \tau(D)$
   - 若$A\in \mathscr{F}_{\tau}$, 则$A^c\in \mathscr{F}_{\tau}$. 这是因为$\tau$可测集的定义关于$A$和$A^c$是对称的. 
   - 若$A_1, A_2\in \mathscr{F}_{\tau}$, 则有$A_1\cap A_2\in \mathscr{F}_{\tau}$. 这是因为   
     $$
     \begin{aligned}       
     \tau(D) &= \tau(D\cap A_1) + \tau(D\cap A_1^c) \\       
     & = \tau(D\cap A_1 \cap A_2) + \tau(D \cap A_1 \cap A_2^c) + \tau(D\cap A_1^c)\\       
     & = \tau(D\cap A_1 \cap A_2) + \tau(D \cap (A_1\cap A_2)^c \cap A_1) + \tau(D\cap (A_1\cap A_2)^c\cap A_1^c)\\       
     & = \tau(D\cap A_1 \cap A_2) + \tau(D\cap (A_1\cap A_2)^c)   
     \end{aligned}   
     $$
4. $\mathscr{F}$是个$\sigma$域
   - 如果$\{B_i\}$两两不交, 则对每个$D\in \mathscr{T}$, 有
     $$
     \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)\right) = \sum\limits_{i=1}^{n} \tau(D\cap B_i)
     $$
     这是因为对任意的$D\in \mathscr{T}$, 有
     $$
     \begin{aligned} 
         \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)\right) &= \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)\cap B_1\right) + \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)\cap B_1^c\right)\\ 
         & = \tau(D\cap B_1) + \tau\left(D\cap \left(\bigcup\limits_{i=2}^{n} B_i\right)\right)\\
         & = \sum\limits_{i=1}^n \tau(D\cap B_i)
     \end{aligned}
     $$
   - 如果$\{B_n\in \mathscr{F}_{\tau}\}$两两不交, 则对每个$D\in \mathscr{T}$. 
     $$
     \tau(D)\ge \sum\limits_{n=1}^{\infty} \tau(D\cap B_n) + \tau\left[D\cap \left(\bigcup\limits_{n=1}^{\infty} B_n\right)^c\right]
     $$
     这是因为
     $$
     \begin{aligned} 
         \tau(D) &= \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)\right) + \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)^c\right) \\ 
         & = \sum\limits_{i=1}^{n} \tau(D\cap B_i) + \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)^c\right)\\
         & \ge \sum\limits_{i=1}^{n} \tau(D\cap B_i) + \tau\left(D\cap \left(\bigcup\limits_{i=1}^{\infty} B_i\right)^c\right)
     \end{aligned}
     $$
     取$n\to\infty$即可得到结论成立. 
   - $\mathscr{F}_{\tau}$是一个$\sigma$域. 我们之前已经证明了$\mathscr{F}_{\tau}$是一个域, 下面只需要证明
     $$
     A_n\in \mathscr{F}_{\tau} \Longrightarrow \bigcup\limits_{n=1}^{\infty} A_n\in \mathscr{F}_{\tau}
     $$
     对每个$n=1,2,\cdots$, 令$B_n=A_n\backslash \bigcup\limits_{i=1}^{n-1} A_i$, 则$\{B_n\in \mathscr{F}_{\tau}\}$两两不交并且满足
     $$
       \bigcup\limits_{n=1}^{\infty} A_n = \bigcup\limits_{n=1}^{\infty} B_n
     $$
     因此对任意的$D\in \mathscr{T}$, 有
     $$
     \begin{aligned} 
         \tau(D) &\ge \sum\limits_{n=1}^{\infty} \tau(D\cap B_n) + \tau\left[D\cap \left(\bigcup\limits_{n=1}^{\infty} B_n\right)^c\right] \\ 
         & \ge  \tau\left(D\cap \left(\bigcup\limits_{n=1}^{\infty} B_n\right)\right) + \tau\left[D\cap \left(\bigcup\limits_{n=1}^{\infty} B_n\right)^c\right] \\ 
         & = \tau\left(D\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)\right) + \tau\left[D\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)^c\right] \\ 
     \end{aligned}
     $$
     但是, 根据$\tau$的半可列可加性我们有
     $$
     \tau(D) \le \tau\left(D\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)\right) + \tau\left[D\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)^c\right]
     $$
     于是我们证明了
     $$
     \tau(D) = \tau\left(D\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)\right) + \tau\left[D\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)^c\right]
     $$
     因此$\bigcup\limits_{n=1}^{\infty} A_n\in \mathscr{F}_{\tau}$. 这就证明了$\mathscr{F}_{\tau}$是一个$\sigma$域.
3. $\tau$限制在$\mathscr{F}_{\tau}$上是测度. 这是因为$\{B_n\in \mathscr{F}_{\tau}\}$两两不交. 取$D = \bigcup\limits_{n=1}^{\infty} B_n$, 我们可以得到
   $$
   \tau\left(\bigcup\limits_{n=1}^{\infty} B_n\right) \ge \sum\limits_{n=1}^{\infty} \tau(B_n)
   $$
   再由$\tau$的半可列可加性, 可以得到$\tau$的可列可加性. 这表明$\tau$是一个测度
4. $(X, \mathscr{F}_{\tau}, \tau)$是完全测度空间. 这是因为对任意的$A\in \mathscr{T}$, 当$\tau(A)=0$时, $\forall D\in \mathscr{T}$, 我们有$\tau(D\cap A) = 0$, 因此
   $$
   \tau(D)  \ge \tau(D\cap A^c)  = \tau(D\cap A) + \tau(D\cap A^c)
   $$
   再根据$\tau$的半可列可加性, 我们得到了
   $$
   \tau(D) = \tau(D\cap A) + \tau(D\cap A^c)
   $$
   这就表明了$A\in \mathscr{\mathscr{F}_{\tau}}$. 因此所有的零测集都属于$\mathscr{F}_{\tau}$. 这就证明了$(X, \mathscr{F}_{\tau}, \tau)$是完全测度空间.
#####
___

## 4. 测度的扩张
### 4.1. 扩张的定义
设$\mu$和$\tau$分别为集合系$\mathscr{E}$和集合系$\overline{\mathscr{E}}$上的测度, 而且$\mathscr{E}\subset \overline{\mathscr{E}}$. 如果对每个$A\subset \mathscr{E}$都有
$$
\tau(A) = \mu(A)
$$
则称$\tau$为$\mu$在$\overline{\mathscr{E}}$上的扩张. 
___
##### 利用外测度的扩张
如果在集合系$\mathscr{E}$上有测度$\mu$, 就可以利用[[#3.2. 生成外测度]]在$X$上生成一个外测度$\tau$. 而根据[[#3.4. Caratheodory定理]], 把这个外测度限制在$\sigma$域$\mathscr{F}_{\tau}$上就得到了一个测度. 

但是, $\mathscr{F}_{\tau}$未必比$\mathscr{E}$更大, 例如下面的例子: 

设$X = \{a, b, c\}$, $\mathscr{E}=\{\varnothing, \{a, b\}, \{b, c\}, X\}$ 和
$$
\mu(\varnothing) = 0, \quad \mu(\{a, b\}) = \mu(\{b, c\}) = 1, \quad \mu(X) = 2
$$
显然$\mu$是$\mathscr{E}$上的测度. 根据生成外测度的算法, 我们有
$$
\tau(\varnothing) = 0, \quad \tau(X) = \tau(\{a, c\}) = 2, \tau(\{a\}) = \tau(\{b\}) = \tau(\{c\}) = \tau(\{a, b\}) = \tau(\{b, c\}) = 1
$$
再根据$\tau$可测集的性质可以得到$\mathscr{F}_{\tau}=\{\varnothing, X\}$. 

这意味着如果想要利用外测度对测度进行扩张, 必须对集合系$\mathscr{E}$做出一定的限制.
#####
___

### 4.2. 测度扩张定理
对于半环$\mathscr{Q}$上的测度$\mu$, 存在$\sigma(\mathscr{Q})$上的测度$\tau$使得对每个$A\in \mathscr{Q}$有
$$
\tau(A) = \mu(A)
$$
如果存在两两不交的$\{A_n\in \mathscr{Q}\}$使得$\bigcup\limits_{n=1}^{\infty} A_n = X$且$\mu(A_n)<\infty$, 则使得$\tau(A) = \mu(A)$的$\tau$唯一. 
___
##### Proof: 
设$\tau$为$\mu$通过[[#3.2. 生成外测度]]产生的外测度. 我们按照下面的顺序来进行证明
1. 首先证明对每个$A\in \mathscr{Q}$, 有$\tau(A) = \mu(A)$. 设$A\in \mathscr{Q}$, 对任何满足$\bigcup\limits_{n=1}^{\infty} A_n \supset A$的$\{A_n\in \mathscr{Q}\}$, 均有
   $$
   \mu(A) = \mu\left(\bigcup\limits_{n=1}^{\infty} (A\cap A_n)\right) \le \sum\limits_{n=1}^{\infty} \mu(A\cap A_n) \le \sum\limits_{n=1}^{\infty} \mu(A_n)
   $$
   根据生成外测度的定义
   $$
   \tau(A) = \inf\left\{\sum\limits_{n=1}^{\infty} \mu(A_n)\ \Big|\ A_n\in \mathscr{Q}, \bigcup\limits_{n=1}^{\infty} A_n\supset A\right\}
   $$
   因此
   $$
   \mu(A) = \tau(A)
   $$
2. 对任意的$A, D\in \mathscr{Q}$, 有
   $$
   \tau(D)\ge \tau(D\cap A) + \tau(D\cap A^c)
   $$
   这是因为$D\cap A^c = D\backslash A = \bigcup\limits_{i=1}^{n} B_i$, 其中$\{B_i\in \mathscr{Q}\}$两两不交. 则
   $$
   \begin{aligned} 
      \tau(D) & = \mu(D) \\ 
      & = \mu(D\cap A) + \mu(D\cap A^c) \\ 
      & = \mu(D\cap A) + \sum\limits_{i=1}^{n} \mu(B_i) \\ 
      & \ge \mu(D\cap A) + \tau(D\cap A^c) \\
      & \ge \tau(D\cap A) + \tau(D\cap A^c) 
   \end{aligned}
   $$
3. $\mathscr{Q}\subset \mathscr{F}_{\tau}$. 即对任意$A\in \mathscr{Q}$和$D\in \mathscr{T}$, 有
   $$
   \tau(D) = \tau(D\cap A) + \tau(D\cap A^c)
   $$
   这是因为当$\tau(D) = \infty$时, 显然成立. 当$\tau(D)<\infty$时, 对任意给定的$\varepsilon>0$, 取$\{B_n\in \mathscr{Q}\}$使得$\bigcup\limits_{n=1}^{\infty} B_n\supset D$. 
   $$
   \begin{aligned} 
   \tau(D) + \varepsilon &\ge \sum\limits_{n=1}^{\infty} \mu(B_n) = \sum\limits_{n=1}^{\infty} \tau(B_n) \\ 
   &\ge \sum\limits_{n=1}^{\infty} \left[\tau(B_n\cap A) + \tau(B_n\cap A^c)\right] \\ 
   & \ge  \tau\left(\bigcup\limits_{n=1}^{\infty} B_n\cap A\right)+  \tau\left(\bigcup\limits_{n=1}^{\infty} B_n\cap A^c\right) \\ 
   &\ge \tau(D\cap A) + \tau(D\cap A^c)
   \end{aligned}
   $$
   令$\varepsilon\to 0$, 即可得到
   $$
   \tau(D) \ge \tau(D\cap A) + \tau(D\cap A^c)
   $$
   再根据$\tau$的半可列可加性可以得到
   $$
   \tau(D) = \tau(D\cap A) + \tau(D\cap A^c)
   $$
4. $\tau$是$\sigma(\mathscr{Q})$上的测度. 这是因为$\mathscr{F}_{\tau}$是$\sigma$域, 故$\mathscr{Q}\subset \mathscr{F}_{\tau}\Longrightarrow \sigma(\mathscr{Q})\subset\mathscr{F}_{\tau}$. 但$\tau$限制在$\mathscr{F}_{\tau}$上是测度, 因此$\tau$是$\sigma(\mathscr{Q})$上的测度. 
5. 如果存在两两不交的$\{A_n\in \mathscr{Q}\}$使得$\bigcup\limits_{n=1}^{\infty} A_n = X$且$\mu(A_n)<\infty$, 则使得$\tau(A) = \mu(A)$的$\tau$唯一. 这是我们有因为下面的引理成立
___
**引理**: 设$\mathscr{P}$是一个$\pi$系, 如果$\sigma(\mathscr{P})$上的测度$\mu, \nu$满足
1. 对每个$A\in \mathscr{P}$, 有$\mu(A) = \nu(A)$
2. 存在两两不交的$\{A_n\in \mathscr{P}\}$使得$\bigcup\limits_{n=1}^{\infty} A_n=X$且$\mu(A_n)<\infty$对每个$n=1,2,\cdots$成立
   
则对任何$A\in \sigma(\mathscr{P})$有
$$
\mu(A) = \nu(A)
$$
___
**Proof**: 设
$$
\mathscr{S} = \{A\in \sigma(\mathscr{P})\mid \mu(A\cap B) = \nu(A\cap B), \forall B\in \mathscr{P}, \mu(B)<\infty\}
$$
根据$\pi$系的性质, 显然有$\mathscr{P}\subset \mathscr{S}$. 下面证明$\mathscr{S}$是一个$\lambda$系, 这是因为
1. $X\in \mathscr{S}$
2. 对于$A_1, A_2\in \mathscr{S}$且$A_1\supset A_2$, 根据可列可加性, 我们有
   $$
   \mu(A_1\cap B) = \mu(A_2\cap B) + \mu((A_1\backslash A_2)\cap B)
   $$
   $$
   \nu(A_1\cap B) = \nu(A_2\cap B) + \nu((A_1\backslash A_2)\cap B) 
   $$
   这样, 我们有
   $$
   \mu((A_1\backslash A_2)\cap B) = \nu((A_1\backslash A_2)\cap B) 
   $$
   这表明$A_1\backslash A_2\in \mathscr{S}$
3. 
