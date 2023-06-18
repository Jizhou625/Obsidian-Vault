## 1. 测度
### 1.1. 测度的公理化定义
设 $\mathscr{E}$ 是 $X$ 上的集合系且$\varnothing \in \mathscr{E}$, 如果$\mu$具有下列性质: 
1. $\mu(\cdot)\ge 0$
2. $\mu(\varnothing)=0$
3. $\mu$ 具有可列可加性
   
则称$\mu$为 $\mathscr{E}$ 上的测度. 

如果对每个$A\in \mathscr{E}$还有$\mu(A)<\infty$, 则称测度$\mu$是有限的. 如果对每个$A\in \mathscr{E}$存在满足$\mu(A_n)<\infty$的$\{A_n\in \mathscr{E}\}$, 使得$\bigcup\limits_{n=1}^{\infty}A_n\supset A$, 则称测度$\mu$是$\sigma$有限的. 

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
空间$X$, 加上由它的子集形成的一个$\sigma$域$\mathscr{F}$, 再加上$\mathscr{F}$上的一个测度$\mu$, 三位一体形成的$(X, \mathscr{F}, \mu)$被称为测度空间. 

如果测度空间 $(X, \mathscr{F}, \mathbb{P})$ 满足 $\mathbb{P}(X)=1$, 则称它为概率空间, 对应的 $\mathbb{P}$ 叫作概率测度. 在概率空间 $(X, \mathscr{F}, \mathbb{P})$ 中, $\mathscr{F}$ 中的集合 $A$ 又称为事件, 而 $\mathbb{P}(A)$ 称为事件 $A$ 发生的概率. 

### 1.4. 零测集
如果 $N \in \mathscr{F}$ 并且 $\mu(N)=0$, 则称 $N$ 为 $\mu$ 的零测集.

## 2. 半环上的测度
### 2.1. 半环上测度的性质
半环$\mathscr{Q}$上的测度具有单调性, 可减性, 半可列可加性, 下连续性和上连续性. 其中各个性质的严格定义分别为
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

### 2.2. 环上有限可加的非负集函数的性质
对于环$\mathscr{R}$上的有限可加非负集函数$\mu$, 有下面的结论成立:

$\mu$是可列可加 $\iff \mu$半可列可加 $\iff \mu$下连续 $\implies\mu$上连续 $\implies \mu$在$\varnothing$上连续, 即对任何满足$A_n\downarrow \varnothing$和$\mu(A_1)<\infty$的$\{A_n\in \mathscr{R}\}$有
   $$
   \lim\limits_{n\to\infty} \mu(A_n) = 0
   $$
如果$\mu$还是有限的, 则上面的所有$\implies$全部变为$\iff$
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
   
