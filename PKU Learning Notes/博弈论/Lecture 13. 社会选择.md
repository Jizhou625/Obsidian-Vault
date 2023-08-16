## 1. 社会选择的合理特征
### 1.1. 社会福利函数
社会福利函数是一个函数$F$, 它将每个严格偏好簇$P^N = (P_i)_{i\in N}\in (\mathcal{P}(A))^N$映射到$\mathcal{P}^*(A)$内的一个偏好关系(表示为$F(P^N)$). 其中, 所有严格偏好簇的组合是笛卡尔乘积
$$
(\mathcal{P}(A))^N=\mathcal{P}(A) \times \mathcal{P}(A) \times \cdots \times \mathcal{P}(A)
$$
$\mathcal{P}^*(A)$表示$A$上所有偏好关系的集合. 

### 1.2. 社会福利函数的合理特征
1. **一致同意性**: 对任意两个备选方案$a, b\in A$和严格偏好簇$P^N=(P_i)_{i\in N}$. 如果$a\succ_{P_i} b$对每个$i\in N$成立, 那么$a\succ_{F(P^N)}b$. 这个条件称为社会福利函数$F$的一致同意性
2. **无关选项的独立性**: 对于任意两个备选方案$a, b\in A$和每两个严格偏好簇$P^N$和$Q^N$, 如果
   $$
   a\succ_{P_i} b \iff a\succ_{Q_i} b, \quad \forall i\in N
   $$
   那么
   $$
   a\succeq_{F(P^N)} b \iff a\succeq_{F(Q^N)} b
   $$
   这个条件称为无关候选项的独立性(Independence of Irrelevant Alternatives, IIA).
3. **非独裁性**: 社会福利函数$F$是独裁的, 如果不存在个人$i\in N$, 使得$F(P^N)=P_i$对每个严格偏好簇$P^N$成立. 换言之, 存在备选方案$a, b\in A$和某个严格偏好簇$P^N$, 使得
   $$
   a\succ_{P_i} b, \quad a\prec_{F(P^N)} b
   $$
   

### 1.3. 社会选择函数
社会选择函数是函数$G: (\mathcal{P}(A))^n\to A$. 社会选择函数将每个严格偏好簇和一个备选方案联系起来. 这个方案叫作社会最偏好的方案.

### 1.4. 社会选择函数的合理特征
1. **一致同意性**: 对任意$a\in A$和严格偏好簇$P^N = (P_i)_{i\in N}$, 如果$a\succ_{P_i} b$对每个$i\in N$和每个方案$b\neq a$成立, 那么$G(P^N)=a$. 这个条件称为社会选择函数$G$的一致同意性. 
2. **单调性**: 设严格偏好簇$P^N$和$Q^N$满足
   $$
   a\succ_{P_i} c\implies a\succ_{Q_i} c,\quad\forall c\neq a,\ \forall i\in N
   $$
   如果$G(P^N) = a$, 那么 $G(Q^N) = a$. 这个条件称为社会选择函数$G$的单调性. 
3. **非独裁性**: 社会选择函数$G$是非独裁的, 如果不存在个人$i\in N$, 使得对每个严格偏好簇$P^N$, $G(P^N)$都是个人$i$最偏好的方案. 


## 2. 不存在满足所有合理特征的社会选择
### 2.1. Arrow不可能定理
如果$|A|\ge 3$, 那么每个满足一致同意和无关候选项独立性的社会福利函数都是独裁的. 也就是说, 不存在一个社会福利函数, 满足一致同意、无关候选项的独立性和非独裁性.
___
##### Proof
首先给出极化候选项的定义

___
**极化候选项**: 如果对$\forall i\in N$, 都有
$$
a \succ_{P_i} b,\  \forall b \in A\backslash \{a\} \mid a \prec_{P_i} b, \ \forall b \in A\backslash \{a\}
$$
那么$a$就是一个极化候选项. 
___
如果$a$是一个极化候选项, 那么
$$
a \succ_{F(P^N)} b,\  \forall b \in A\backslash \{a\} \mid a \prec_{F(P^N)} b, \ \forall b \in A\backslash \{a\}
$$
否则, 假设
$$
b\succ_{F(P^N)} a\succ_{F(P^N)} c
$$
将所有个人排序$P_i$中的$c$移动到$b$前面, 由一致同意性可以得到$c\succ_{F(P^N)} b$. 但是由IIA我们可以得到$b\succ_{F(P^N)} a\succ_{F(P^N)} c$, 这就产生了矛盾! 

取一个候选项$a$, 从任意一个偏好簇$P^{(0)N}$开始, $P^{(0)N}$满足$a$在它所有个人排序中都是最后一个. 对于$P^{(i)N}, 1\le i\le N$, 设
1. $a$在其所包含的个人排序$P_1^{(i)},P_2^{(i)},\cdots, P_i^{(i)}$都是第一位
2. $a$在其所包含的个人排序$P_{i+1}^{(i)}, P_{i+2}^{(i)}, \cdots, P_{N}^{(i)}$都是最后一位
3. 所有其他候选项的次序都如同$P^{(0)N}$中的次序

根据一致同意性, $a$必须在社会福利函数$F(P^{(0)N})$的最后一位, 而在社会福利函数$F(P^{(N)N})$的第一位. 因此, 沿着这个序列, 存在第一个严格偏好簇$P^{(j)N}$, $a$在其社会福利函数$F(P^{(j)N})$的第一个位置. 下面我们证明$j$实际上是个独裁者. 

令$Q^N$为任意一个严格偏好簇, $b$和$c$是不等于$a$的候选项. 并且有
$$
b \succ_{Q_j} c
$$
我们构造一个附加组合: 对于$i=1,2,\cdots, j$, 将$a$移动到$i$的个人排序$Q_i$的最前面, 对于$i=j+1, \cdots, N$, 将$a$移动到$i$的个人排序$Q_i$的最后面. 得到辅助偏好簇$P^{\prime N}$. 对任意的$x\neq a$, 根据IIA, 我们有
$$
a\succ_{F(P^{\prime N})} x \iff a\succ_{F(P^{(j) N})} x
$$
因为$a$在$F(P^{(j) N})$中的位置是第一位, 所以$a$在$F(P^{\prime N})$中的位置也是第一位.

然后, 我们再将$b$移动到$j$的个人排序$P_j^{\prime}$的最前面. 得到辅助偏好簇$Q^{\prime N}$. 

1. 考虑$a, c$, 根据IIA, 我们有
   $$
   a\succ_{F(P^{\prime N})}c \implies a\succ_{F(Q^{\prime N})}c
   $$
2. 考虑$a,b$, 根据IIA, 我们有
   $$
   b\succ_{F(P^{(j-1)N})} a \implies b\succ_{F(Q^{\prime N})} a
   $$
   因此我们有
   $$
   b\succ_{F(Q^{\prime N})} a\succ_{F(Q^{\prime N})}c
   $$
3. 考虑$b, c$, 根据IIA, 我们有
   $$
   b\succ_{F(Q^N)} c \impliedby b\succ_{F(Q^{\prime N})} c
   $$
   这样, 我们就证明了
   $$
   b \succ_{Q_j} c \implies b\succ_{F(Q^N)} c
   $$

接下来, 以$b\neq a$为极化候选项, 重复上述过程, 有
$$
\begin{aligned} 
a\succ_{Q_j} c &\implies a\succ_{F(Q^N)} c, \quad \forall c\neq a, b \\ 
c \succ_{Q_j} a &\implies c\succ_{F(Q^N)} a, \quad \forall c\neq a, b
\end{aligned}
$$
最后, 对于$a$和$b$的偏好关系, 这只需要取极化候选项$c\neq a, b$. 
#####
___

### 2.2. 偏好关系的拼接
设$P$和$Q$为备选方案集$A$上的两个严格偏好关系, $R$是备选方案集$A$上的一个子集. 在$A$上定义一个严格的偏好关系, 将$R$内的元素放置在不在$R$内的元素之前. 在$R$内的元素上的严格偏好关系是$P$给出的, 不在$R$内的元素上的严格偏好关系是$Q$给出的. 这个严格偏好关系表示为$Z(P, Q; R)$. 也就是说
$$
\begin{aligned} 
a\succ_{Z_{(P, Q; R)}} b &\iff a \succ_{P} b ,\quad &a, b\in R\\ 
a\succ_{Z_{(P, Q; R)}} b &\iff a \succ_{Q} b ,\quad &a, b\in A\backslash R \\  
&a\succ_{Z_{(P, Q; R)}} b , &\quad a\in R, b\in A\backslash R
\end{aligned}
$$
![image-1](Lecture%2013.%20社会选择.assets/偏好关系的拼接.png)  


令$P^N$和$Q^N$是两个严格偏好簇, $R\subseteq A$为备选方案的子集. 用$Z(P^N, Q^N;R)$表示严格偏好簇: 对每个$i\in N$, 参与人$i$的严格偏好是$Z(P_i, Q_i; R)$

### 2.3. 社会选择函数的Arrow不可能定理
如果$|A|\ge 3$, 那么所有满足一致同意和单调性的社会选择函数都是独裁的. 
___
##### Proof
我们首先证明两个引理
___
**Lemma1**: 设$G$是一个单调的社会选择函数, 令$P^N$和$Q^N$是两个严格偏好簇, $R\subseteq A$. 如果$a\in R$且$G(P^N)=a$, 那么$G(Z(P^N, Q^N; R))=a$. 等价地, 如果$G(Z(P^N, Q^N; R))\neq a$和$a\in R$, 那么$G(P^N)\neq a$.  ^eb801a
___
**Proof**: 因为$a\in R$, 因此对任意的$b\notin R$和$i\in N$, 都有
$$
a\succ_{P_i} b \implies a\succ_{Z(P_i, Q_i; R)} b, \quad b\notin R
$$ 
对于任意的$b\in R$, 其在$Z(P^N, Q^N; R)$中的排序是由$P^N$决定的, 这意味着
$$
a\succ_{P_i} b \iff a\succ_{Z(P_i, Q_i; R)} b, \quad b\in R
$$
由于$G$是单调的, 我们有$G(Z(P^N, Q^N; R))=a$.

___
**Lemma2**: 设$G$是一个单调的社会选择函数, 满足一致同意特征, 令$P^N$为严格偏好簇, $a, b\in A$. 如果  ^aaf0b6
$$
a\succ_{P_i} b,\quad \forall i\in N
$$
那么$G(P^N)\neq b$. 
___
**Proof**: 定义$Q^N = Z(P^N, P^N; \{a\})$. 在偏好簇$Q^N$中, 所有的个人都将$a$排在最高, 由一致同意性, 我们有$G(Q^N)=a$. 用反证法, 假设$G(P^N)=b$. 对于偏好簇$P^N$和偏好簇$Q^N$, 我们有
$$
b\succ_{P_i}c \iff b \succ_{Q_i} c, \quad \forall c \in A\backslash \{a\} 
$$
又因为所有人都认为$a\succ_{P_i}b$且$a\succ_{Q_i} b$. 因此, 我们有
$$
b\succ_{P_i}c \implies b \succ_{Q_i} c, \quad \forall  c \in A
$$
根据单调性, 我们有
$$
G(P^N) = b\implies G(Q^N) = b
$$
这与$G(Q^N)=a$矛盾. 因此, 我们有$G(P^N)\neq b$.
___

设$W^N\in (\mathcal{P}(A))^N$是一个严格偏好簇. 对于每个严格偏好簇$P^N$, 对于任意的$a, b\in A$, 运用Lemma2, 我们可以得到
$$
G\left(Z\left(P^N, W^N ;\{a, b\}\right)\right) \in \{a, b\}
$$
定义
$$
\begin{aligned}
& G\left(Z\left(P^N, W^N ;\{a, b\}\right)\right)=a \quad \Longrightarrow \quad a \succ_{F\left(P^N\right)} b \\
& G\left(Z\left(P^N, W^N ;\{a, b\}\right)\right)=b \quad \Longrightarrow \quad b \succ_{F\left(P^N\right)} a
\end{aligned}
$$
显然, 这样定义的关系是完备的. 此外, 要让这个关系是自反的, 定义
$$
a\succeq_{F(P^N)} a, \quad \forall a\in A  
$$
接下来, 要证明$F$是一个社会福利函数, 只需要证明$F$是传递的. 利用反证法, 假设对$a, b, c\in A$, 有
$$
a\succ_{F(P^N)} b, \quad b\succ_{F(P^N)} c, \quad c\succ_{F(P^N)} a
$$
因为$a\succ_{F(P^N)} b$, 我们有$G(Z(P^N, W^N, \{a, b\})) = a$. 显然, 我们还有
$$
G\left(Z\left(Z\left(P^N, P^N ;\{a, b, c\}\right)\right), W^N ;\{a, b\}\right)=a
$$
根据Lemma1可以得到
$$
G(Z(P^N, P^N; \{a, b, c\})) \neq b
$$
这样, 我们证明了
$$
a\succ_{F(P^N)} b\implies G(Z(P^N, P^N; \{a, b, c\})) \neq b
$$
同理, 我们可以证明
$$
G(Z(P^N, P^N; \{a, b, c\})) \neq c, \quad G(Z(P^N, P^N; \{a, b, c\})) \neq a
$$
这就证明了
$$
G(Z(P^N, P^N; \{a, b, c\})) \notin \{a, b, c\}
$$
另一方面, 根据Lemma2, 我们有
$$
G(Z(P^N, P^N; \{a, b, c\})) \in \{a,b,c\}
$$
矛盾! 因此, 我们证明了$F$是传递的. 这就证明了$F$是一个社会福利函数.

下面, 我们验证$F$满足一致同意性和IIA. 首先验证一致同意性. 设$a\neq b$是$A$内的两个备选方案, 令$P^N$是一个严格偏好簇, 满足$a\succ_{P_i} b$对任意的$i\in N$成立.  这意味着, 方案$a$在严格偏好关系$Z(P_i, W_i;\{a, b\})$下是最优的. 因此, 我们有$G(Z(P_i, W_i;\{a, b\}))=a$, 根据$F$的定义, 可以得到$a\succ_{F(P^N)}b$. 这就证明了$F$是一致同意的.

下面验证$F$满足IIA, 设$a, b\in A$是两个不同的备选方案, 令$P^N, Q^N$是两个严格偏好簇满足
$$
a\succ_{P_i} b \iff a\succ_{Q_i} b, \quad \forall i\in N
$$
这意味着对每个$i\in N$
$$
Z(P_i, W_i; \{a, b\}) = Z(Q_i, W_i; \{a, b\})
$$
根据$F$的定义, 我们有
$$
a\succ_{F(P^N)} b \iff a\succ_{F(Q^N)} b
$$
这就证明了$F$满足IIA. 

根据[2.1. Arrow不可能定理](#2.1.%20Arrow不可能定理), 我们有$F$是独裁的. 换言之, 存在个人$i$使得
$$
F(P^N) = P_i, \quad \forall P^N\in (\mathcal{P}(A))^N
$$
设$P^N$是一个严格偏好关系, $a$是个人$i$最偏好的方案, $b\neq a$是任意一个备选方案, 我们有$a\succ_{P_i} b$. 又因为$i$是独裁者, 我们有$a\succ_{F(P^N)} b$. $F$的定义意味着
$$
G(Z(P^N, W^N; \{a, b\})) = a\neq b\implies G(P^N)\neq b, \quad \forall b\in A\backslash \{a\}
$$
于是我们得到了$G(P^N)=a$, 这就证明了$G$是一个独裁者.
#####
___

### 2.4. 社会选择函数$G$的象
定义社会选择函数$G$的象为
$$
\mathrm{range}(G) = \{a\in A\mid \exists P^N\in (\mathcal{P}(A))^N, G(P^N)=a\}
$$
也就是说, $\mathrm{range}(G)$是可能被社会选择的备选方案集合. 显然, 如果社会选择函数$G$满足一致同意性, 那么$\mathrm{range}(G)=A$

### 2.5. 社会选择函数的Arrow不可能定理(在range上的推广)
对任一满足$|\mathrm{range}(G)|\ge 3$的单调的社会选择函数$G$, 存在参与人$i$, 使得对每个严格偏好簇$P^N$, 方案$G(P^N)$是参与人$i$在$\mathrm{range}(G)$内最偏好的方案.
___
##### Proof
[Lemma1](#^eb801a)仍然适用, 利用[Lemma1](#^eb801a), 可以证明下面的Lemma3
___
**Lemma3**: 如果$G$是一个单调的社会选择函数, 那么对于任意两个满足
$$
a\succ_{P_i} b\iff a\succ_{Q_i} b, \quad \forall i\in N, \quad \forall a, b\in \mathrm{range}(G)
$$
严格偏好簇$P^N, Q^N$, 都有
$$
G(P^N) = G(Q^N)
$$
___
**Proof**:  用符号表示$R = \mathrm{range}(G)$, 取任意的$W^N$, 根据$P^N$和$Q^N$的性质, 我们有
$$
Z(P^N, W^N; R) = Z(Q^N, W^N; R) \implies G(Z(P^N, W^N; R)) = G(Z(Q^N, W^N; R))
$$
根据[Lemma1](#^eb801a)和$R = \mathrm{range}(G)$, 我们有$G(P^N) = G(Q^N)$, 这就证明了结论成立. 也就是说, 不在$\mathrm{range}(G)$内的备选方案对于社会选择函数$G$是不可见的.
___
接下来, 我们改造[Lemma2](#^aaf0b6). 事实上, 我们有下面的更强的引理Lemma4
___
**Lemma4**: 设$G$是一个单调的社会选择函数, 令$a\in \mathrm{range}(G)$, $P^N$是一个严格偏好簇, 如果
$$
a\succ_{P_i} b, \quad \forall i\in N
$$
那么$G(P^N)\neq b$
___
当$b\notin \mathrm{range}(G)$时, 结论显然成立. 当$b\in \mathrm{range}(G)$时, 根据Lemma3, 可以不妨设$\mathrm{range}(G)=A$. 用反证法, 假设$G(P^N)=b$. 因为$a\in \mathrm{range}(G)$, 因此存在一个严格偏好簇$Q^N$, 使得$G(Q^N)=a$. 构造辅助偏好簇$P^{\prime N}$如下
$$
P^{\prime N} = Z(P^N, P^N; \{a, b\})
$$
显然, 我们有
$$
b\succ_{P_i} c\implies b\succ_{P^{\prime}_i} c, \quad \forall i\in N, \quad \forall c\neq b
$$
根据单调性条件, 有
$$
G(P^N) = b \implies G(P^{\prime N}) = b
$$
当然也有
$$
a\succ_{Q_i} c\implies a\succ_{P^{\prime}_i} c, \quad \forall i\in N, \quad \forall c\neq a
$$
根据单调性条件, 有
$$
G(Q^N) = a \implies G(P^{\prime N}) = a
$$
矛盾! 这就证明了$G(P^N)\neq b$
___
最后, 综合[Lemma1](#^eb801a), Lemma3和Lemma4, 类似于[2.3. 社会选择函数的Arrow不可能定理](#2.3.%20社会选择函数的Arrow不可能定理)的证明, 我们可以得到原命题成立. 事实上, Lemma1意味着可以删除$A$中所有不在$\mathrm{range}(G)$中的备选项, 而删掉这些备选项以后$G$满足一致同意性. 
#####
___

## 3. 不可操纵性
### 3.1. 不可操纵性的定义
社会选择函数$G$是可操纵的, 条件是, 存在严格偏好簇$P^N$, 个人$i\in N$和严格偏好关系$Q_i$, 满足
$$
G(Q_i, P_{-i}) \succ_{P_i} G(P^N)
$$
也就是说, 存在一个个人, 通过汇报自己虚假的偏好关系, 使得社会选择的方案对自己更加有利. 

### 3.2. 不可操纵性与独裁(Gibbard, Satterthwaite)
设$G$是一个不可操纵的社会选择函数, 满足一致同意特征, 如果$|A|\ge 3$, 那么$G$是独裁的. 

该定理意味着, 如果我们希望应用非独裁的社会选择函数, 那么一定存在一种情形, 使得个人可以通过虚假的汇报来操纵社会选择函数.
___
##### Proof
我们只要证明满足一致同意特征的每个不可操纵的社会选择函数是单调的.  用反证法, 假设$G$不是单调的, 即存在两个不同的严格偏好簇$P^N$和$Q^N$, 两个不同的备选方案$a, b$, 使得
$$
a\succ_{P_i} c\implies a\succ_{Q_i} c, \quad \forall i\in N, \quad \forall c\neq a
$$
而
$$
G(P^N) = a, \quad G(Q^N) = b
$$
用$I_{P^N, Q^N}$表示个人$i$的集合
$$
I_{P^N, Q^N} = \{i\in N\mid P_i\neq Q_i\}
$$
通过取恰当的$P^N, Q^N$, 使得$|I_{P^N, Q^N}|$最小. 设$j\in I_{P^N, Q^N}$, 我们断言$G(P_{j}, Q_{-j})=a$, 用反证法,  假设$G(P_{j}, Q_{-j})=c\neq a$, 此时备选方案组合$a, c$和严格偏好簇$P^N$和$(P_{j}, Q_{-j})$仍然满足非单调性条件, 但是$|I_{P^N, (P_{j}, Q_{-j})}|$更小, 矛盾! 因此, 我们有$G(P_{j}, Q_{-j})=a$. 

由于$G$是不可操纵的, 因此当偏好簇是$Q^N$时, 个人$j$没有动机虚假汇报$P_j$, 因此
$$
b=G(Q^N) \succ_{Q_j} G(P_j, Q_{-j}) = a
$$
类似地, 当偏好簇是$(P_{j}, Q_{-j})$时
$$
a = G(P_j, Q_{-j}) \succ_{P_j} G(Q^N) = b\implies a\succ_{Q_j} b
$$
这就得到了矛盾! 因此$G$是单调的. 
#####
___

## 4. 一些有趣的例子
### 4.1. 孔多塞悖论
即使每个人的偏好是传递的, 群体的偏好也可能是不传递的. 假设我们有三个投票者$1,2,3$和三个候选者$X, Y$和$Z$. 假设$3$个人的偏好如下
$$
\begin{aligned}
&X \succ_1 Y \succ_1 Z\\
&Y>_2 Z>_2 X\\
&Z \succ_3 X>_3 Y
\end{aligned}
$$
应用少数服从多数的法则来定义群体偏好, 我们可以得到$X\succ Y$, $Y\succ Z$以及$Z\succ X$. 

孔多塞悖论指出了少数服从多数表决法则的结果依赖于一种策略议程设置(strategic agenda setting)的行为. 少数服从多数表决法则不满足无关选项的独立性原则. 

### 4.2. 鼓励虚假投票的实验
假设坛子里有10颗弹子, 有 $50 \%$ 的可能, 10 颗弹子都是白色的; 有$50 \%$的可能, 10 颗弹子是 9 颗绿色和 1 颗白色的. 有$A, B, C$三个参与人. 首先, 每个参与人允许从坛子中取出一颗弹子, 然后将它放回去 (不让其他两个人知道). 然后三个人做一次同时的投票, 如果至少有两个人说对了, 则三个人都会得到一笔奖金. 否则, 三个人什么都得不到.

作为参与人, 假设其他两个参与人会诚实地投票, 那么, 当自己的一票起作用的时候, 坛子里一定有绿色的弹子. 因此，无论参与人的私有信息是什么，最优策略就是猜测坛子里有绿色的弹子. 

### 4.3. 陪审团投票的信息建模
假设每个陪审团收到一个独立的私有信号, 建议有罪 $(G)$ 或无辜 $(I)$. 假设嫌疑人有罪的先验概率为$\dfrac{1}{2}$, 对于某个 $q>\dfrac{1}{2}$, 有 
$$
\mathbb{P}\left(G\text{ signal}\mid \text{defendant is guilty}\right) = q, \quad \mathbb{P}\left(I\text{ signal}\mid \text{defendant is innocent}\right) = q
$$
根据贝叶斯法则, 可以得到
$$
\mathbb{P}\left(\text{defendant is guilty}\mid G\text{ signal}\right) = q, \quad \mathbb{P}\left(\text{defendant is innocent}\mid I\text{ signal}\right) = q
$$

在陪审团的模型下(所有陪审团都投有罪才判定有罪), 如果陪审员接受到一个 $(I)$ 的信号, 唯一能影响审判结果的情形是别人都投有罪。假设其他人都会按照自己的信号投票, 被告有罪的概率是
$$
\mathbb{P}\left(\text{defendant is guilty}\mid I\text{ signal}\right) = \dfrac{q^{k-2}}{q^{k-2}+(1-q)^{k-2}}
$$
从这个计算中得到的结论是, 如果陪审员相信其他人都是按照他们的信号投票, 且陪审团足够大, 就总应该忽略自己的信号而投有罪. 

在陪审团模型的纳什均衡中. 将一个无辜被告定罪的概率, 是一个不会随着陪审团规模变大而趋于$0$的正数. 
