## 1. $\pi$系族
### 1.1. $\pi$系
如果 $X$ 上的非空集合系 $\mathscr{F}$ 对交的运算是封闭的, 即
$$
A, B \in \mathscr{F} \Longrightarrow A \cap B \in \mathscr{F}
$$
则称 $\mathscr{F}$ 为 $\pi$ 系

### 1.2. 半环
满足下列条件的 $\pi$ 系 $\mathscr{Q}$ 称为半环: 对任意 $A, B \in \mathscr{Q}$ 且 $A \supset B$, 存在有限个两两不交的 $\left\{C_k \in \mathscr{Q}, k=1,2, \cdots, n\right\}$, 使得
$$
A \backslash B=\bigcup_{k=1}^n C_k
$$

### 1.3. 环
如果非空集合系 $\mathscr{R}$ 对并和差的运算是封闭的, 即 
$$
A, B \in \mathscr{R} \Longrightarrow A \cup B, A \backslash B \in \mathscr{R}
$$ 
则称 $\mathscr{R}$ 为环. 显然, 环一定是半环. 
___
##### Proof 
由于 
$$
A \cap B=A \cup B \backslash[(A \backslash B) \cup(B \backslash A)] \in \mathscr{R}
$$
故环必然是半环. 
#####
___

### 1.4. 域
满足下列条件的集合系 $\mathscr{A}$ 称为域, 也称为代数(algebra)
1. $X \in \mathscr{A}$
2. $A, B \in \mathscr{A} \Longrightarrow A \cap B \in \mathscr{A}$
3. $A \in \mathscr{A} \Longrightarrow A^c \in \mathscr{A}$

显然, 域一定是环
___
##### Proof  
不难证明
$$
A\cup B = (A^c \cap B^c)^c \in \mathscr{A}, \quad A\backslash B = A \cap B^c \in \mathscr{A}
$$
因此域一定是环
#####
___

## 2. 单调系族
### 2.1. 单调系
如果对集合系 $\mathscr{M}$ 中的任何单调序列 $\left\{A_n, n=1,2, \cdots\right\}$, 均有 $\lim\limits _{n \rightarrow \infty} A_n \in \mathscr{M}$, 则把 $\mathscr{M}$ 称为单调系

### 2.2. $\lambda$ system
集合系 $\mathscr{L}$ 称为 $\lambda$ 系, 如果它满足下列条件
1. $X \in \mathscr{L}$
2. $A, B \in \mathscr{L}$ 且 $A \supset B \Longrightarrow A \backslash B \in \mathscr{L}$
3. $A_n \in \mathscr{L}$ 且 $A_n \uparrow \Longrightarrow \bigcup\limits_{n=1}^{\infty} A_n \in \mathscr{L}$

显然, $\lambda$系一定是单调系
___
##### Proof
根据条件1和2, 可以得到若$A\in \mathscr{L}$, 则有$A^c\in \mathscr{L}$. 因此若$A_n\downarrow$, 则有$A_n^c\uparrow$
$$
\bigcap\limits_{n=1}^{\infty} A_n = \left(\bigcup\limits_{n=1}^{\infty} A_n^c\right)^c\in \mathscr{L} 
$$
因此$\lambda$系一定是单调系
#####
___

### 2.3. Dynkin system
集合系 $\mathscr{D}$ 称为 Dynkin 系, 如果它满足下列条件
1. $X \in \mathscr{D}$
2. $A \in \mathscr{D} \Longrightarrow A^c \in \mathscr{D}$
3. 如果$A_1, A_2, \cdots \in \mathscr{D}$并且$A_i\cap A_j = \varnothing$对任意的$i\neq j$成立, 则$\bigcup\limits_{n\in \mathbb{N}}^{} A_n\in \mathscr{D}$

Dynkin系是$\lambda$系的等价定义
___
##### Proof
1. 首先证明Dynkin系是$\lambda$系. 设$\mathscr{D}$是一个Dynkin系. 显然$\mathscr{D}$满足$\lambda$系的第一个条件. 而对于$A, B\in \mathscr{L}$且$A\supset B$, 我们有
   $$
   A \backslash B = A \cap B^c = (A^c \cup B)^c \in \mathscr{D}
   $$
   因此$\mathscr{D}$也满足$\lambda$系的第二个条件. 最后, 对于$A_n\in \mathscr{D}$且$A_n \uparrow$. 令$B_1 = A_1$, $B_i = A_i\backslash A_{i-1},\ i\ge 2$. 显然$B_i$两两不交. 运用性质$3$即可以得到
   $$
   \bigcup\limits_{n=1}^{\infty} A_n = \bigcup\limits_{n=1}^{\infty} B_n \in \mathscr{D}
   $$
   这就证明了Dynkin系是$\lambda$系.
2. 再证明$\lambda$系也是一个Dynkin系. 设$\mathscr{L}$是一个$\lambda$系. 不难验证$\mathscr{L}$满足Dynkin系的前2个条件. 对于任意的$A\cap B = \varnothing$, 我们有
   $$
   (A\cup B)^c = A^c \cap B^c = A^c \backslash B \in \mathscr{L}
   $$
   因此有$A\cup B \in\mathscr{L}$. 对任意的$A_1, A_2, \cdots \in \mathscr{L}$并且$A_i\cap A_j = \varnothing$对任意的$i\neq j$成立, 设
   $$
   D_n = A_1\cup \cdots \cup A_n \in \mathscr{L}
   $$
   则$D_n\uparrow$, 根据$\lambda$系的第三条性质可以得到
   $$
   D_1\cup D_2\cup\cdots = A_1\cup A_2\cup \cdots \in \mathscr{L}
   $$
   这就证明了$\lambda$系也是一个Dynkin系.
#####
___
## 3. $\sigma$-代数
### 3.1. $\sigma$-代数
集合系 $\mathscr{F}$ 称为 $\sigma$ 域, 如果它满足下列条件
1. $X \in \mathscr{F}$
2. $A \in \mathscr{F} \Longrightarrow A^c \in \mathscr{F}$
3.  $A_n \in \mathscr{F} \Longrightarrow \bigcup\limits_{n=1}^{\infty} A_n \in \mathscr{F}$

可以证明, $\sigma$-代数一定是代数, 也一定是$\lambda$系. 
___
##### Proof
1. 首先证明$\sigma$代数是一个代数. 由于$X\in\mathscr{F}$, 故$\varnothing\in F$. 因此$\bigcup\limits_{k=1}^nA_k\in \mathscr{F}$. 利用德摩根律, 可以得到$\bigcap\limits_{k=1}^nA_k\in \mathscr{F}$, 这就证明了$\sigma$-代数是代数
2. 再证明$\sigma$代数是一个$\lambda$系: 由于$A\backslash B = A\cap B^c$, 因此这就证明了$\sigma$-代数是$\lambda$系. 
#####
___



### 3.2. $\sigma$代数的判定
1. 一个既是单调系又是域的集合系必然是$\sigma$代数
2. 一个既是$\lambda$系又是$\pi$系的集合系必然是$\sigma$代数

___
##### Proof
1. 用$\mathscr{F}$表示这个集合系, 由于$\mathscr{F}$是域, 因此只要证明
   $$
   A_n\in \mathscr{F} \Longrightarrow \bigcup\limits_{n=1}^{\infty} A_n \in \mathscr{F}
   $$
   设$B_n = \bigcup\limits_{k=1}^{n}A_k\in \mathscr{F}$, 则我们有
   $$
   \bigcup\limits_{n=1}^{\infty}A_n = \bigcup\limits_{n=1}^{\infty}\bigcup\limits_{k=1}^{n}A_k = \lim\limits_{n\rightarrow\infty}B_n\in \mathscr{F}  
   $$
   这就证明了$\mathscr{F}$是$\sigma$代数
2. 用$\mathscr{F}$表示这个集合系, 由于$\mathscr{F}$是$\lambda$系, 因此
   $$
   \begin{aligned} 
        & X\in \mathscr{F} \\ 
        & A\in\mathscr{F} \Longrightarrow A^c = X \backslash A \in \mathscr{F}
   \end{aligned}
   $$
   再加上$\mathscr{F}$是$\pi$系, 因此$\mathscr{F}$是域. 再加上$\mathscr{F}$是$\lambda$系因此一定也是单调系, 我们得到了$\mathscr{F}$是一个$\sigma$代数. 

#####
___



## 4. $\sigma$代数的生成
### 4.1. 集合的生成
称 $\mathscr{S}$ 是由集合系 $\mathscr{E}$ 生成的环 (或单调系, 或 $\lambda$ 系, 或 $\sigma$ 域), 如果下列条件被满足
1. $\mathscr{S} \supset \mathscr{E}$
2. 对任一环 (或单调系, 或 $\lambda$ 系, 或 $\sigma$ 域) $\mathscr{S}^{\prime}$ 均有
$$
\mathscr{S}^{\prime} \supset \mathscr{E} \Longrightarrow \mathscr{S}^{\prime} \supset \mathscr{S}
$$
由集合系 $\mathscr{E}$ 生成的环 (或单调系, 或 $\lambda$ 系, 或 $\sigma$ 域), 也就是包含 $\mathscr{E}$ 的最小的环 (或单调系, 或 $\lambda$ 系, 或 $\sigma$ 域). 我们把由集合系 $\mathscr{E}$ 生成的环, 单调系, $\lambda$ 系和 $\sigma$ 域分别记作 $r(\mathscr{E}), m(\mathscr{E}), \lambda(\mathscr{E}), \sigma(\mathscr{E})$

### 4.2. 集合生成的存在性
对于任意集合系 $\mathscr{E}$, 一定存在由 $\mathscr{E}$ 生成的环, 单调系, $\lambda$ 系和 $\sigma$ 域.
___
##### Proof
我们只对环的存在性进行证明. 其他三种情况的证明可以完全类似. 

令$\mathscr{T}$是由$X$中的全体集合所组成的集合系. $\mathscr{T}$是一个$\sigma$域自然也是一个环. 用$A$表示包含集合系$\mathscr{E}$的环的全体, 则$A$非空.  

不难看出, $\mathscr{S} = \bigcap\limits_{\mathscr{A}\in A}\mathscr{A}$还是一个环(区别于$\pi$系和半环的核心). 并且满足生成的两个条件. 
#####
___

### 4.3. 半环的生成环
如果 $\mathscr{Q}$ 是半环, 则
$$
r(\mathscr{Q})=\bigcup_{n=1}^{\infty}\left\{\bigcup_{k=1}^n A_k\ \Big|\ A_k \in \mathscr{Q}, A_i\cap A_j=\varnothing \right\}
$$
___
##### Proof: 
记
$$
r = \bigcup_{n=1}^{\infty}\left\{\bigcup_{k=1}^n A_k\ \Big|\ A_k \in \mathscr{Q}, A_i\cap A_j=\varnothing \right\}
$$
由于环对有限并的封闭性, 我们可以得到$r(\mathscr{Q})\supset r$. 

于是只要证明$r(\mathscr{Q})\subset r$, 也就是说, 只要证明$r$是一个环. 设$A, B\in r$, 则存在两两不交的$\{A_i\in \mathscr{Q}, i=1,2,\cdots, n\}$和两两不交的$\{B_j\in \mathscr{Q}, j=1,2,\cdots, m\}$, 使得
$$
A=\bigcup\limits_{i=1}^n A_i,\quad  B=\bigcup\limits_{j=1}^m B_j 
$$
根据半环的性质, 我们知道, 存在$k_{ij}$个两两不交的集合$C^{(i, j)}_l\in \mathscr{Q}$, 满足
$$
A_i \backslash (A_i\cap B_j) = \bigcup\limits_{l=1}^{k_{ij}} C^{(i, j)}_l
$$
于是$A\backslash B$可以表示为
$$
\begin{aligned}
A \backslash B & =A \cap B^c=\bigcup_{i=1}^n\left(A_1 \cap B^c\right)=\bigcup_{i=1}^n \bigcap_{j=1}^m\left(A_i \cap B_j^c\right) \\
& =\bigcup_{i=1}^n \bigcap_{j=1}^m\left[A_i \backslash\left(A_i \cap B_j\right)\right]=\bigcup_{i=1}^n \bigcap_{j=1}^m \bigcup_{l=1}^{k_{ij}} C_l^{(i, j)} \\
& =\bigcup_{i=1}^n \bigcup_{\substack{l_1=1, \cdots, k_{i, 1} \\
\cdots\cdots \\
l_m= 1, \cdots, k_{i, m}}}\left(C_{l_1}^{(i, 1)} \cap \cdots \cap C_{l_m}^{(i, m)}\right) .
\end{aligned}
$$
根据半环的性质, $C_{l_1}^{(i, 1)} \cap \cdots \cap C_{l_m}^{(i, m)}\in \mathscr{Q}$. 因此$A\backslash B\in r$. 同样地
$$
A\cup B = B\cup (A\backslash B) = \left\{\bigcup\limits_{j=1}^m B_j \right\}\cup \left\{\bigcup_{i=1}^n \bigcup_{\substack{l_1=1, \cdots, k_{i, 1} \\
\cdots\cdots \\
l_m= 1, \cdots, k_{i, m}}}\left(C_{l_1}^{(i, 1)} \cap \cdots \cap C_{l_m}^{(i, m)}\right)\right\} \in r
$$
这就证明了$r$是一个环.
#####
___

### 4.4. 域的生成单调系是$\sigma$代数
如果$\mathscr{A}$是域, 则 $\sigma(\mathscr{A}) = m(\mathscr{A})$. 

或者, 我们也可以写成, 如果$\mathscr{A}$是域, $\mathscr{M}$是单调系, 则
$$
\mathscr{A}\subset \mathscr{M}\Longrightarrow \sigma(\mathscr{A})\subset \mathscr{M}
$$
___
##### Proof: 
显然, $\sigma(\mathscr{A})\supset m(\mathscr{A})$. 下面只要证明$m(\mathscr{A})$是一个$\sigma$域, 而$m(\mathscr{A})$已经是一个单调系, 因此只要证明$m(\mathscr{A})$是域. 又因为$X\in \mathscr{A}\subset m(\mathscr{A})$, 我们只要证明$m(\mathscr{A})$是环. 

对任意的$A\in \mathscr{A}$, 设
$$
\mathscr{G}_A = \{B\in m(\mathscr{A})\mid A\cup B, A\backslash B \in m(\mathscr{A})\}
$$
显然, $\mathscr{A}\subset \mathscr{G}_A$. 对于单调序列$\{B_k\}\in \mathscr{G}$, 设其极限为$B\in m(\mathscr{A})$, 我们有$\{A\cup B_k\}\in m(\mathscr{A})$是单调序列, 因此$A\cup B\in m(\mathscr{A})$, 同理$A\backslash B\in m(\mathscr{A})$. 因此$B\in \mathscr{G}_A$, 这表明$\mathscr{G}_A$是单调系. 因此$\mathscr{G}_A\supset m(\mathscr{A})$. 这表明了
$$
A\in \mathscr{A}, B\in m(\mathscr{A}) \Longrightarrow A\cup B, A\backslash B \in m(\mathscr{A})
$$
对任意的$B\in m(\mathscr{A})$, 令
$$
\mathscr{H}_B = \{A \in m(\mathscr{A})\mid A\cup B, A\backslash B\in m(\mathscr{A})\}
$$
这仍然是一个单调系. 我们又已经证明了$\mathscr{A}\subset \mathscr{H}_B$. 因此我们就得到了$\mathscr{H}_B\supset m(\mathscr{A})$, 即$m(\mathscr{A})$确实是一个环. 
#####
___

### 4.5 $\pi$系的生成$\lambda$系是$\sigma$代数(Dynkin's $\pi-\lambda$ Theorem)
如果$\mathscr{P}$是$\pi$系, 则$\sigma(\mathscr{P}) = \lambda(\mathscr{P})$. 

或者, 我们也可以写成, 如果$\mathscr{P}$是$\pi$系, $\mathscr{L}$是$\lambda$系, 则
$$
\mathscr{P}\subset \mathscr{L}\Longrightarrow \sigma(\mathscr{P})\subset \mathscr{L}
$$
___
##### Proof: 
显然, $\sigma(\mathscr{P})\supset \lambda(\mathscr{P})$. 于是只要证明$\lambda(\mathscr{P})$是一个$\pi$系, 对于任意的$A\in \mathscr{P}$, 设
$$
\mathscr{G}_A = \{B\in \lambda(\mathscr{P})\mid A\cap B\in \lambda(\mathscr{P})\}
$$
易证$\mathscr{G}_A$是一个$\lambda$系, $\mathscr{G}_A\supset \mathscr{P}$, 从而$\mathscr{G}_A\supset \lambda(\mathscr{P})$. 这说明
$$
A\in \mathscr{P}, B\in \lambda(\mathscr{P}) \Longrightarrow A\cap B\in \lambda(\mathscr{P})
$$
再对任意的$B\in \lambda(\mathscr{P})$, 设
$$
\mathscr{H}_B = \{A\in \lambda(\mathscr{P})\mid A\cap B\in \lambda(\mathscr{P})\}
$$
同样地, 我们可以得到$\mathscr{H}_B\supset \lambda(\mathscr{P})$, 即
$$
A, B\in \lambda(\mathscr{P}) \Longrightarrow A\cap B\in \lambda(\mathscr{P})
$$
这就证明了$\lambda(\mathscr{P})$是一个$\pi$系.
#####
___

