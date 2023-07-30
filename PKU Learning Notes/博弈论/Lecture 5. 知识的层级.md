## 1. Aumann模型
### 1.1. 不完全信息的Aumann模型
令$S$是有限的自然状态集合(我们用自然状态来描述影响参与人收益的所有参数), 一个不完全信息的Aumann模型包括四个要素$(N, Y, (\mathcal{F}_i)_{i\in N}, \mathfrak{s})$, 其中
1. $N$是有限的参与人的集合.
2. $Y$是有限要素的集合, 称为状态.
3. 对每个$i\in N$, $\mathcal{F}_i$是$Y$的一个分划. 包含状态$\omega$的分划$\mathcal{F}_i$中的元素表示为$F_i(\omega)$.
4. $\mathfrak{s}: Y\to S$将每个状态和一个自然状态联系起来. 

在状态集$S$上, 一个不完全信息的Aumann场景是五元组$(N, Y, (\mathcal{F}_i)_{i\in N}, \mathfrak{s}, \omega_*)$, 其中$(N, Y, (\mathcal{F}_i)_{i\in N}, \mathfrak{s})$是不完全信息Aumann模型, $\omega_*\in Y$是真实的状态.

### 1.2. 知识算子$K_i$
设$A\subseteq Y$是一个事件, 定义算子$K_i: 2^Y\to 2^Y$为
$$
K_i(A) = \{\omega\in Y\mid F_i(\omega)\subseteq A\}
$$
这是参与人$i$知道事件$A$的所有可能的状态的集合.


### 1.3. Kripke's S5 System
如果运算子$K: 2^Y\to 2^Y$满足以下五条性质, 那么我们称$K$是Kripke's S5 System: 
1. $K_i Y = Y$: 参与人知道$Y$是所有状态的集合
2. $K_iA \cap K_iB = K_i(A\cap B)$: 参与人知道事件$A$和事件$B$, 当且仅当知道事件$A\cap B$.
3. $K_iA \subseteq A$: 如果参与人知道事件$A$, 那么事件$A$成立
4. $K_iK_iA = K_iA$: 如果参与人知道事件$A$, 那么他知道他知道事件$A$. 反之亦然. 
5. $(K_iA)^c = K_i((K_iA)^c)$: 如果参与人不知道事件$A$, 那么他知道他不知道事件$A$. 反之亦然.

如果$K_i$是如[1.2. 知识算子$K_i$](#1.2.%20知识算子$K_i$)所定义的知识算子, 那么$K_i$是Kripke's S5 System.

与此同时, 对于任意的Kripke's S5 System $K$, 定义
$$
F(\omega) = \bigcap\limits_{} \{A\subseteq Y\mid \omega\in K(A)\} , \quad \mathcal{F} = \{F(\omega)\mid \omega\in Y\}
$$
则集合族$\mathcal{F}$是$Y$的一个分划, 并且$K$是集合族$\mathcal{F}$上的知识算子.
___
##### Proof
首先证明当$K_i$是知识算子时, Kripke's S5 System成立
1. 根据结论3, 我们有$K_i Y\subseteq Y$, 又因为$\mathcal{F}_i$是$Y$的一个分划, 所以$Y\subseteq K_i Y$. 因此$K_i Y = Y$.
2. 令$\omega\in K_i A \cap K_i B$, 根据知识的定义$F_i(\omega)\subseteq A$并且$F_i(\omega)\subseteq B$, 则$F_i(\omega)\subseteq A\cap B$. 于是有$\omega\in K_i(A\cap B)$. 这意味着
   $$
   K_iA \cap K_iB \subseteq K_i(A\cap B)
   $$
   同理, 我们可以证明反向的包含关系. 因此$K_iA \cap K_iB = K_i(A\cap B)$
3. 令$\omega\in K_i A$, 根据知识的定义, $F_i(\omega)\subseteq A$, 又因为$\omega\in F_i(\omega)$. 这意味着$\omega\in A$. 因此$K_iA\subseteq A$ 
4. 根据结论3我们有$K_iK_i A \subseteq K_i A$. 如果$\omega\in K_iA$, 那么$F_i(\omega)\subseteq A$. 因此, 对每个$\omega^{\prime}\in F_i(\omega)$, 我们有$\omega^{\prime}\in F_i(\omega^{\prime})=F_i(\omega) \subseteq A$. 这意味着$\omega^{\prime}\in K_i A$. 因此$F_i(\omega)\subseteq K_iA$. 这意味着$\omega\in K_iK_i A$. 因此$K_i A\subseteq K_iK_i A$. 我们证明了$K_iK_i A = K_i A$.
5. 根据结论3, 我们有$K_i((K_iA)^c) \subseteq (K_iA)^c$. 如果$\omega\in (K_iA)^c$, 那么$F_i(\omega)\not\subseteq A$. 因此, 对每个$\omega^{\prime}\in F_i(\omega)$, 我们有
   $$
   \omega^{\prime}\in F_i(\omega^{\prime})=F_i(\omega) \not\subseteq A
   $$ 
   这意味着$\omega^{\prime}\not\in K_i A$. 因此$F_i(\omega)\subseteq (K_iA)^c$. 这意味着$\omega\in K_i((K_iA)^c)$. 因此$(K_iA)^c\subseteq K_i((K_iA)^c)$. 我们证明了$K_i((K_iA)^c) = (K_iA)^c$.

接下来, 证明Kripke S5系统刻画了知识算子. 因为$K(A)\subseteq A$, 因此对任意的$\omega\in K(A)$, 都有$\omega\in A$, 于是$\omega\in F(\omega)$. 根据定义和$K(A)\cap K(B) = K(A\cap B)$, 我们有
$$
F(\omega) =\bigcap\limits_{\omega\in K(A)}^{}  A = \argmin_{X\subseteq Y} \{\omega\in K(X)\}
$$
这意味着若$\omega^{\prime}\in F(\omega)$, 则$F(\omega^{\prime})\subseteq F(\omega)$. 如果$\omega \in F(\omega^{\prime})$, 则显然有$F(\omega)\subseteq F(\omega^{\prime})$,这就证明了$F(\omega) = F(\omega^{\prime})$. 如果$\omega \notin F(w^{\prime})$, 设$A = F(\omega^{\prime}), B = F(\omega)$. 则我们有$\omega,\omega^{\prime}\in K(B), \omega\notin K(A), \omega^{\prime}\in K(A)$, 并且$K(A)\subset K(B)$. 于是$\omega \in K^c(A), \omega^{\prime}\notin K^c(A)$
$$
\omega \in K(B) \cap K(K^c(A)) = K(B\cap K^c(A))
$$
因为$B\cap  K^c(A)$比集合$B$至少少一个元素$\omega^{\prime}$. 这与$B$的最小性产生了矛盾! 再根据$K(Y) = Y$, 我们可以得到集合族$\mathcal{F}$是$Y$的一个分划. 

接下来, 只需要证明分划$\mathcal{F}$上的知识算子$K^{\prime}$满足$K^{\prime} = K$. 显然
$$
K^{\prime}(F(\omega^*)) = \{\omega\in Y\mid F(\omega)\subseteq F(\omega^*)\} = K(F(\omega^*))
$$
设$A$是一个集合, 其包含的完整的分划$\mathcal{F}$中的元素有$F_1, \cdots, F_t$. 根据定义
$$
K^{\prime}(A) = K^{\prime}(F_1)\cup \cdots\cup  K^{\prime}(F_t) = K(F_1)\cup \cdots \cup K(F_t) \subseteq K(A)
$$
对$F\not\subseteq A$以及$F$的最小性, 我们有
$$
K(F)\cap K(A) =K(F\cap A) = \varnothing \implies K(F_1)\cup \cdots \cup K(F_t) \supseteq K(A)
$$
这样, 我们就证明了对任意$A\subseteq Y$, 都有$K^{\prime}(A) = K(A)$.
#####
___

### 1.4. 知识的层级
对任意的$A\subseteq Y$和参与人的有限序列$i_1, i_2, \cdots, i_l$, 状态集$Y$上的知识层级是一个回答如下问题对错与否的系统: "在状态$\omega$下, 参与人$i_1$知道参与人$i_2$知道$\cdots$知道参与人$i_l$知道事件$A$吗?" 

在状态$\omega$下, 如果$\omega\in K_{i_1}K_{i_2}\cdots K_{i_l}A$, 那么对问题"在状态$\omega$下, 参与人$i_1$知道参与人$i_2$知道$\cdots$知道参与人$i_l$知道事件$A$吗?" 的回答是肯定的; 否则, 回答是否定的. 

### 1.5. 共同知识
令$(N, Y, (\mathcal{F}_i)_{i\in N}, \mathfrak{s})$为不完全信息Aumann模型, $A\subseteq Y$是一个事件, $\omega\in Y$是一个状态. 如果对参与人的每个有限序列$i_1, i_2, \cdots, i_l$, 都有
$$
\omega \in K_{i_1}K_{i_2}\cdots K_{i_l}A
$$
那么我们说事件$A$在状态$\omega$下是共同知识.

共同知识可以扩展到$S$中的事件, $S$中的事件$C$是状态$\omega$下的共同知识当且仅当事件$\mathfrak{s}^{-1}(C)$是$\omega$中的共同知识.

### 1.6. 不能区分的共同知识
如果事件$A$在状态$\omega$下是共同知识, 并且存在参与人$i\in N$满足$\omega^{\prime}\in F_i(\omega)$, 那么事件$A$在状态$\omega^{\prime}$下也是共同知识.
___
##### Proof
因为事件$A$在状态$\omega$下是共同知识, 因此对参与人的每个有限序列$i_1, i_2, \cdots, i_l$, 都有
$$
\omega \in K_{i_1}K_{i_2}\cdots K_{i_l}A
$$
不难得到
$$
F_i(\omega)\subseteq K_{i_1}K_{i_2}\cdots K_{i_l}A
$$
有因为$\omega^{\prime}\in F_i(\omega^{\prime}) = F_i(\omega)$, 因此$\omega^{\prime}\in K_{i_1}K_{i_2}\cdots K_{i_l}A$. 这意味着事件$A$在状态$\omega^{\prime}$下也是共同知识.
#####
___

### 1.7. 共同知识的图刻画
设$(N, Y, (\mathcal{F}_i)_{i\in N}, \mathfrak{s})$是不完全信息的Aumann模型. 定义图形$G = (Y, E)$, 其中节点的集合就是状态集合$Y$, 节点$\omega$和$\omega^{\prime}$之间存在一条边当且仅当存在参与人$i\in N$满足$\omega^{\prime}\in F_i(\omega)$. 

令$\omega\in Y$是一个状态, $A\subseteq Y$是一个事件. 那么, 当且仅当$A\supseteq C(\omega)$时, 事件$A$是状态$\omega$下的共同知识. 其中$C(\omega)$是图$G$中包含节点$\omega$的连通分量.
___
##### Proof
首先我们证明如果$A$是$\omega$下的共同知识, 那么$C(\omega)\subseteq A$. 利用数学归纳法和[1.6. 不能区分的共同知识](#1.6.%20不能区分的共同知识)的结论即得成立. 接下来, 我们证明如果$C(\omega)\subseteq A$, 那么事件$A$在状态$\omega$下是共同知识. 要证明这一点, 只要证明$C(\omega)$在$\omega$下是共同知识. 因为$C(\omega)$是连通分量, 因此对每个$\omega^{\prime}\in C(\omega)$, 我们有$F_i(\omega^{\prime})\in C(\omega)$. 这意味着
$$
C(\omega)\supseteq \bigcup\limits_{\omega^{\prime}\in C(\omega)}^{} F_i(\omega^{\prime}) \supseteq C(\omega)  
$$
这意味着$K_i(C(\omega)) = C(\omega)$对任意$i\in N$成立. 于是$C(\omega)$是共同知识. 
#####
___


## 2. 具有信念的不完全信息Aumann模型
### 2.1. 具有信念的不完全信息Aumann模型
包含信念的不完全信息Aumann模型包含五个要素$(N, Y, (\mathcal{F}_i)_{i\in N}, \mathfrak{s}, \mathbb{P})$, 其中
1. $N$是有限的参与人的集合.
2. $Y$是有限的状态集合. 
3. 对每个$i\in N$, $\mathcal{F}_i$是$Y$的一个分划.
4. $\mathfrak{s}: Y\to S$将每个状态和一个自然状态联系起来.
5. $\mathbb{P}$是$Y$上的概率分布, 对每个$\omega\in Y$, 满足$\mathbb{P}(\omega)>0$, 概率分布$\mathbb{P}$称为共同先验知识. 

在这个模型中, 真实状态$\omega_*$是根据概率分布$\mathbb{P}$随机生成的.

### 2.2. 知识等价于概率为1的信念
令$(N, Y, (\mathcal{F}_{i})_{i\in N}, \mathfrak{s}, \mathbb{P})$是具有信念的不完全信息Aumann模型. 那么对每个$\omega\in Y$, 每个参与人$i\in N$和每个事件$A\subseteq Y$, 参与人$i$在状态$\omega$下知道事件$A$, 当且仅当他赋予那个事件的概率为1.
$$
\mathbb{P}(A\mid F_i(\omega)) = 1 \iff F_i(\omega) \subseteq A
$$
___
##### Proof
首先假定$F_i(\omega)\subseteq A$, 那么
$$
\mathbb{P}(A\mid F_i(\omega)) \ge \mathbb{P}(F_i(\omega)\mid F_i(\omega)) = 1
$$
因此$\mathbb{P}(A\mid F_i(\omega)) = 1$. 再假设$\mathbb{P}(A\mid F_i(\omega)) = 1$, 那么
$$
\dfrac{\mathbb{P}(A\cap F_i(\omega))}{\mathbb{P}(F_i(\omega))} = \mathbb{P}(A\mid F_i(\omega)) = 1
$$
这就得到了$\mathbb{P}(A \cap  F_i(\omega)) = \mathbb{P}(F_i(\omega))$. 因此$F_i(\omega)\subseteq A$.
#####
___

### 2.3. Aumann同意定理
令$(N, Y, (\mathcal{F}_{i})_{i\in N}, \mathfrak{s}, \mathbb{P})$为具有信念的不完全信息Aumann模型, 假定$n=2$, 令$A\subseteq Y$为一个事件, $\omega\in Y$为一个状态. 如果事件"参与人I赋予A的概率为$q_1$"在$\omega$中是共同知识, 事件"参与人II赋予A的概率为$q_2$"在$\omega$中是共同知识, 那么$q_1= q_2$

Aumann同意定理是说, 如果两个参与人在一开始的时候对世界具有相同的信念, 那么所有的分歧不可能是共同知识. 
___
##### Proof
令$C(\omega)$是对应于给定Aumann模型中$\omega$的连通分量, 根据[1.7. 共同知识的图刻画](#1.7.%20共同知识的图刻画), 事件$C(\omega)$是状态$\omega$下的共同知识. 事件$C(\omega)$可以表示为$\mathcal{F}_1$中元素的并集. $C = \bigcup\limits_{F_1^j\in \mathcal{F}_{1}^j}^{} F_1^{j}$, 这里$\mathcal{F}_1^j\subseteq \mathcal{F}_1$. 

参与人I赋予事件$A$的概率为$q_1$, 这个事件在$\omega$中是共同知识. 这意味着$C(\omega)\subseteq A$, 于是, 对任意的$F_1^j\in \mathcal{F}_1^j$, 有$F_1^j\subseteq A$, 并且
$$
\mathbb{P}(A\mid F_1^j) = \dfrac{\mathbb{P}(A\cap F_1^j)}{\mathbb{P}(F_1^j)} = q_1
$$
根据全概率公式, 有
$$
\mathbb{P}(A\cap C) = \sum\limits_{F_1^j\in \mathcal{F}_1^j} \mathbb{P}(A\cap F_1^j) = q_1\sum\limits_{F_1^j\in \mathcal{F}_1^j}^{} \mathbb{P}(F_1^j) = q_1\mathbb{P}(C)
$$
同理
$$
\mathbb{P}(A\cap C) = q_2\mathbb{P}(C)
$$
因为对任意的$\omega\in Y$, 都有$\mathbb{P}(\omega)>0$, 因此$\mathbb{P}(C)>0$, 于是$q_1 = q_2$.
#####
___


### 2.4. Aumann同意定理的进一步讨论
#### 2.4.1. 一个例子
考虑如下图所示的有共同先验知识的不完全Aumann模型, 在任何状态$\omega$下都是共同知识的唯一事件就是$Y$
![image-1](Lecture%205.%20%E7%9F%A5%E8%AF%86%E7%9A%84%E5%B1%82%E7%BA%A7.assets/Aumann%E5%90%8C%E6%84%8F%E4%B8%80%E4%B8%AA%E4%BE%8B%E5%AD%90.png)  

考虑事件$A = \{\omega_2, \omega_3\}$和情形$\omega = \omega_1$. 
$$
\mathbb{P}(A\mid \{\omega_1, \omega_2\}) = \dfrac{\mathbb{P}(A\cap \{\omega_1, \omega_2\})}{\mathbb{P}(\{\omega_1, \omega_2\})} = \dfrac{2}{3}
$$
同理不难得到在每个状态下, 两个参与人赋予事件$A$的概率是$\dfrac{2}{3}$. 正式地
$$
\left\{\omega\mid q_1 = \mathbb{P}(A\mid F_1(\omega)) = \dfrac{2}{3}\right\}=Y, \quad \left\{\omega\mid q_2 = \mathbb{P}(A\mid F_2(\omega)) = \dfrac{2}{3}\right\}=Y
$$
根据知识算子的定义, 参与人I赋予事件$A$的概率是$\dfrac{2}{3}$是所有状态下的共同知识, 参与人II赋予事件$A$的概率是$\dfrac{2}{3}$是所有状态下的共同知识.  

#### 2.4.2. 不贸易定理
令$(N, Y, (\mathcal{F}_1, \mathcal{F}_2), \mathfrak{s}, \mathbb{P})$为具有信念的不完全信息Aumann模型. 令$f: Y\to\mathbb{R}$是一个函数, $\omega^*\in Y$是$Y$中的状态. 假设
$$
\mathbb{E}(f\mid \mathcal{F}_1)(\omega)\ge 0, \quad \mathbb{E}(f\mid \mathcal{F}_2)(\omega)\le 0
$$
在$\omega^*$中都是共同知识. 那么事件
$$
D = \{\omega\in Y\mid \mathbb{E}(f\mid \mathcal{F}_1)(\omega) = \mathbb{E}(f\mid \mathcal{F}_2)(\omega)=0\}
$$
在$\omega^*$中是共同知识.
## 3. Harsanyi模型
### 3.1. Harsanyi Model
不完全信息的Harsanyi模型是向量$(N, (T_i)_{i\in N}, {p}, S, (\boldsymbol{s}_t)_{t\in \operatorname*{\times}\limits_{i\in N} T_i})$
1. $N$是参与人的有限集合
2. $T_i$是参与人$i$的类型的有限集合
3. ${p}\in \Delta(T)$是类型向量集合上的概率分布, 对每个参与人$i\in N$和每个类型$t_i\in T_i$, 满足
   $$
   p(t_i) = \sum\limits_{\boldsymbol{t}_{-i}\in T_{-i}} p(t_i, \boldsymbol{t}_{-i}) >0
   $$
4. $S$是自然状态集, 每个自然状态$\boldsymbol{s}\in S$是向量
   $$
   \boldsymbol{s} = (N, (A_i)_{i\in N}, (u_i)_{i\in N})
   $$ 
   这里$A_i$是参与人$i$的行动的非空集合, $u_i: \operatorname*{\times}\limits_{i\in N}A_i\to \mathbb{R}$是参与人$i$的效用函数. 
5. $\boldsymbol{s}_{\boldsymbol{t}} = (N, (A_i(t_i))_{i\in N}, (u_i(\boldsymbol{t}))_{i\in N})\in S$. 参与者在$\boldsymbol{s}_t$中的行动集只取决于他的类型$t_i$, 而独立于其他参与人的类型. 

不完全信息博弈按照如下的方式进行.
1. 随机行动根据概率分布$p$选择类型向量$\boldsymbol{t} = (t_1, t_2, \cdots, t_n)$
2. 每个参与人$i$知道为其选定的类型$t_i$, 但不知道其他参与人的类型$\boldsymbol{t}_{-i}$
3. 参与人同时选择自己的行动, 每个参与人$i$, 知道自己的类型$t_i$, 选择行动$a_i\in A_i(t_i)$
4. 每个参与人得到收益$u_i(\boldsymbol{t};\boldsymbol{a})$, 这里$\boldsymbol{a} = (a_1,a_2, \cdots, a_n)$是参与人选择的行动向量. 

### 3.2. Harsanyi模型和扩展式博弈
每个不完全信息Harsanyi博弈可以被描述为一个具有随机行动和信息集的扩展式博弈. 
___
##### Proof

#####
___

### 3.3. 贝叶斯均衡
**条件效用的定义**: 策略向量$\boldsymbol{\sigma}^*$是贝叶斯均衡, 如果对每个参与人$i\in N$, 每个类型$t_i\in T_i$和每个可能的行动$a_i\in A_i(t_i)$, 都有
$$
u_i(\boldsymbol{\sigma}^*\mid t_i) \ge u_i((a_i, \boldsymbol{\sigma}_{-i}^*)\mid t_i)
$$
其中
$$
u_i(\boldsymbol{\sigma}\mid t_i) = \sum\limits_{\boldsymbol{t}_{-i}\in T_{-i}} p(\boldsymbol{t}_{-i}\mid t_i)u_i((t_i, \boldsymbol{t}_{-i}); \boldsymbol{\sigma})
$$

**代理式博弈的定义**: 令$\Gamma(N, (T_i)_{i\in N}, p, S, (s_t)_{t\in T})$为不完全信息的Harsanyi博弈. 对应于$\Gamma$的代理式博弈$\widehat{\Gamma}$是如下的策略式博弈
1. 参与人集是$\bigcup\limits_{i\in N}^{} T_i$: 在$\Gamma$中的每个参与人的每个类型对应于$\widehat{\Gamma}$中的一个参与人
2. 参与人$t_i$在$\widehat{\Gamma}$的纯策略集是$A_i(t_i)$, 在博弈$\Gamma$中是那个类型的可能行动集
3. 参与人$t_i$在$\widehat{\Gamma}$中的收益函数$\widehat{u}_{t_i}$由下式给出
   $$
   \widehat{u}_{t_i}(\boldsymbol{a}):=\sum_{t_{-i} \in T_{-i}} p\left(\boldsymbol{t}_{-i} \mid t_i\right) u_i\left(t_i, \boldsymbol{t}_{-i} ;\left(a_j\left(t_j\right)\right)_{j \in N}\right)
   $$

其中$\boldsymbol{a} = (a_j(t_j))_{j\in N, t_j\in T_j}$表示所有的参与人在$\widehat{\Gamma}$中的行动向量. $\widehat{\Gamma}$中的纳什均衡$\boldsymbol{\sigma}^*$被称为$\Gamma$的贝叶斯均衡.