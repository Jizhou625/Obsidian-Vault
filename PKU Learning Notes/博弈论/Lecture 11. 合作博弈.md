## 1. 合作博弈
### 1.1. 具有可转移效用的合作博弈
具有可转移效用的合作博弈(TU博弈)是一个组合$(N; v)$, 使得
1. $N = \{1,2,\cdots, n\}$是参与人的一个有限集合, $N$的一个子集叫作一个联盟, 所有可能的联盟的集合记作$2^N$.
2. $v: 2^N\to \mathbb{R}$是一个函数, 将每个联盟$S$和一个实数$v(S)$联系起来, 满足$v(\varnothing)=0$. 这个函数叫作博弈的联盟函数. 

实数$v(S)$叫作联盟$S$的值. 这个值的意义在于, 如果$S$的成员同意成立一个联盟$S$, 那么结果是他们可以生产$v(S)$单位的效用. 这和非联盟$S$中的参与人的行为无关. 

### 1.2. 合作博弈的策略等价
合作博弈$(N; v)$策略等价于$(N; w)$, 当且仅当存在正数$a$和向量$\boldsymbol{b}\in \mathbb{R}^N$, 使得对每个联盟$S\subseteq N$, 有
$$
w(S) = av(S) +\sum\limits_{i\in S}^{} b_i 
$$
策略等价是一个等价关系. 即它是自反的, 对称的和传递的.

### 1.3. 合作博弈的标准化
合作博弈$(N; v)$是0-1标准化的, 如果$v(N)=1$, 并且对每个参与人$i\in N$, 都有$v(i)=0$成立. 合作博弈$(N;v)$是0-0标准化的, 如果$v(N)=0$, 并且对每个参与人$i\in N$, 都有$v(i)=0$成立. 合作博弈$(N;v)$是0-$(-1)$标准化的, 如果$v(N)=-1$, 并且对每个参与人$i\in N$, 都有$v(i)=0$成立.

令$(N; v)$是一个合作博弈
1. $(N; v)$策略等价于一个0-1标准化的合作博弈, 当且仅当$v(N)>\sum\limits_{i\in N}^{} v(i)$
2. $(N; v)$策略等价于一个0-0标准化的合作博弈, 当且仅当$v(N)=\sum\limits_{i\in N}^{} v(i)$
3. $(N; v)$策略等价于一个0-$(-1)$标准化的合作博弈, 当且仅当$v(N)<\sum\limits_{i\in N}^{} v(i)$

___
##### Proof
不妨设$v(i) = 0$对任意的$i\in N$成立, 否则可以设$w(i) = v(i) -v(i)$, $b_i = v(i)$. 这样, 根据策略等价的定义, 我们知道$w$和$v$是策略等价的. 此时只要证明
1. $(N; v)$策略等价于一个$0$-$1$标准化的合作博弈, 当且仅当$v(N)>0$
2. $(N; v)$策略等价于一个$0$-$0$标准化的合作博弈, 当且仅当$v(N)=0$
3. $(N; v)$策略等价于一个$0$-$(-1)$标准化的合作博弈, 当且仅当$v(N)<0$

再进行度量单位的标准化, 就得到了原结论成立. 
#####
___

### 1.4. 特殊的合作博弈
#### 1.4.1. sup-additive
合作博弈$(N; v)$是sup-additive的, 如果对任意一组不相交的联盟$S$和$T$, 都有
$$
v(S) +v (T) \le v(S\cup T)
$$

#### 1.4.2. 单调性
合作博弈$(N; v)$是单调的, 如果对任意的联盟$S\subseteq T$, 都有
$$
v(S) \le v(T)
$$

### 1.5. 解的概念和联盟结构
令$\mathcal{U}$是一族合作博弈(基于任意的参与人集合). $\mathcal{U}$上的解的概念是一个函数$\phi$, 将每个合作博弈$(N; v)\in \mathcal{U}$和$\mathbb{R}^N$中的一个子集$\boldsymbol{\varphi}(N; v)$联系起来. 

解的概念叫作点解, 如果对每个合作博弈$(N; v)\in \mathcal{U}$, 集合$\boldsymbol{\varphi}(N; v)$只包含一个元素. 

### 1.6. 配置集
令$(N, v)$是一个合作博弈, $\mathcal{B}$是一个联盟结构(即参与人集合$N$的一个分化). 我们称向量$\boldsymbol{x}\in \mathbb{R}^n$对联盟结构$\mathcal{B}$是
1. **有效率的**: 如果对每个联盟$S\in \mathcal{B}$, 都有
   $$
   x(S) = v(S)
   $$
2. **个体理性的**: 如果对每个参与人$i\in N$, 都有
   $$
   x_i \ge v(i)
   $$

如果向量$\boldsymbol{x}\in \mathbb{R}^N$对联盟结构$\mathcal{B}$是有效率的且个体理性的, 那么我们称$\boldsymbol{x}$是联盟结构$\mathcal{B}$的一个配置. 联盟结构$\mathcal{B}$所有配置组成的集合叫作配置集, 记作$\mathcal{X}(\mathcal{B}; v)$. 一个可能的解的概念是
$$
\boldsymbol{\varphi}(N; v; \mathcal{B}) = \mathcal{X}(\mathcal{B}; v)
$$

## 2. 核
### 2.1. 联盟的核
令$(N; v)$是一个合作博弈, 配置$\boldsymbol{x}\in \mathcal{X}(N;v)$是联盟理性的, 如果对每个联盟$S\subseteq N$, 都有
$$
x(S) \ge v(S)
$$

合作博弈$(N ;v)$的核是所有联盟理性的配置组成的集合, 记作$\mathcal{C}(N; v)$.
$$
\mathcal{C}(N; v) = \{\boldsymbol{x}\in \mathcal{X}(N;v)\mid x(S)\ge v(S), \forall S\subseteq N\}
$$

### 2.2. 联盟的核的性质
1. **凸紧集**: 合作博弈$(N; v)$的核$\mathcal{C}(N; v)$是有限数量半空间的交集, 合作博弈的核是凸紧集.
2. **协变性**: 联盟博弈的核在策略等价下是协变的, 即对任意的$a>0$和每个$\boldsymbol{b}\in \mathbb{R}^N$
   $$
   \mathcal{C}(N; av+\boldsymbol{b}) = a\mathcal{C}(N; v )+ \boldsymbol{b}
   $$
___
##### Proof
1. 对每个联盟$S$, 集合$\{\boldsymbol{x}\in \mathbb{R}^N\mid x(S)\ge v(S)\}$是一个封闭的半空间. 核是$2^n-1$个半空间的交集. 因此核是一个凸集. 又因为每个半空间都是闭集, 因此核也是一个闭集. 最后, 因为核是$\mathcal{X}(N;v)$的子集, 因此是有界的. 根据$\mathbb{R}^N$中的有界闭集是紧集的定理, 核是一个紧集.
2. 令$(N;u)$是一个策略等价于$(N, v)$的联盟博弈
   $$
   u(S) = av(S) +b(S), \quad \forall S\subseteq N
   $$
   令$\boldsymbol{x}\in \mathcal{C}(N;v)$, 则有
   $$
   x(S)\ge v(S),\ \forall S\subseteq N, \quad x(N) = v(N)
   $$
   因为$a>0$, 我们有
   $$
   \begin{aligned} 
   ax(S) +b(S) &\ge av(S) +b(S) = u(S), \quad \forall S\subseteq N \\ 
   ax(N) +b(N) &= av(N) +b(N) = u(N)
   \end{aligned}
   $$
   也就是说$a\boldsymbol{x}+\boldsymbol{b}\in \mathcal{C}(N;u)$. 因此我们证明了$a\mathcal{C}(N;v) + \boldsymbol{b}\subseteq \mathcal{C}(N; u)$. 同样地, 我们可以证明$a\mathcal{C}(N;u) + \boldsymbol{b}\supseteq \mathcal{C}(N; u)$. 因此我们证明了$a\mathcal{C}(N;v) + \boldsymbol{b} = \mathcal{C}(N; av+\boldsymbol{b})$.
#####
___

### 2.3. 关联向量和关联矩阵
对每个联盟$S$, 联盟的关联向量是向量$\boldsymbol{r}^S\in \mathbb{R}^N$, 定义为
$$
r^S_i = \begin{cases}1, \quad & i \in S \\ 0 & i \notin S\end{cases}
$$
令$\mathcal{D} =\{S_1, S_2, \cdots, S_k\}$是非空联盟的组合. $\mathcal{D}$的关联矩阵是$k\times n$的矩阵$R^\mathcal{D}$, 其中第$i$行是联盟$S_i$的关联向量$\boldsymbol{r}^{S}_i$. 换言之. 关联矩阵的第$(i, j)$单元格包含的是$1$当且仅当参与人$j$属于联盟$S_i$.

### 2.4. 平衡组合 
联盟组合$\mathcal{D}$是平衡组合, 如果存在正数向量$(\delta_{S})_{S\in \mathcal{D}}$使得
$$
\sum\limits_{S\in \mathcal{D}; i\in S}^{} \delta_S =1, \quad \forall i\in N
$$
其中
$$
\sum\limits_{S\in \mathcal{D}}^{}\delta_S\boldsymbol{r}^S = \boldsymbol{1}
$$
下图所列举的联盟组合都是平衡的. 

| Coalition| Incidence Matrix | Coefficients| 
| :---: | :---: | :---: |
|$\begin{array}{c}\{1\} \\\{2\} \\\{3\}\end{array}$| $\left(\begin{array}{lll}1 & 0 & 0 \\0 & 1 & 0 \\0 & 0 & 1\end{array}\right)$| $\begin{array}{c}1 \\1 \\1\end{array}$ |
|$\begin{array}{c}\{1,2\} \\\{3\}\end{array}$| $\left(\begin{array}{lll}1 & 1 & 0 \\0 & 0 & 1\end{array}\right)$| $\begin{array}{c}1 \\1\end{array}$ |
|$\begin{array}{c}\{1,3\} \\\{2\}\end{array}$| $\left(\begin{array}{lll}1 & 0 & 1 \\0 & 1 & 0\end{array}\right)$| $\begin{array}{c}1 \\1\end{array}$ |
|$\begin{array}{c}\{2,3\}\\ \{1\}\end{array}$| $\left(\begin{array}{lll}0 & 1 & 1 \\ 1&0&0\end{array}\right)$| $\begin{array}{c}1\\ 1\end{array}$ |
|$\begin{array}{c}\{1,2\}\\ \{1,3\}\\ \{2,3\}\end{array}$| $\left(\begin{array}{lll}1 & 1 & 0 \\ 1 & 0& 1\\ 0 &1 &1\end{array}\right)$| $\begin{array}{c}\frac{1}{2}\\ \frac{1}{2}\\ \frac{1}{2}\end{array}$ |



### 2.5. Bondareva-Shapley Theorem 
合作博弈$(N;v)$的核是非空的充分必要条件是, 对联盟的每个平衡组合$\mathcal{D}$和$\mathcal{D}$的每个平衡权重向量$(\delta_S)_{S\in \mathcal{D}}$, 都有
$$
v(N) \ge \sum\limits_{S\in \mathcal{D}}^{} \delta_S v(S)
$$
___
##### Proof
我们首先证明一个论断: 联盟的组合$\mathcal{D}$是平衡的, 当且仅当对每个向量$\boldsymbol{x}\in \mathbb{R}^N$, 有
$$
\sum\limits_{S\in\mathcal{D}}^{} \delta_S x(S) = x(N) \tag{1}
$$
如果$\mathcal{D}$是一个平衡的联盟组合, 平衡权重是$(\delta_S)_{S\in \mathcal{D}}$. 令$\boldsymbol{x}\in \mathbb{R}^N$, 则
$$
\begin{aligned} 
\sum\limits_{S\in \mathcal{D}}^{} \delta_Sx(S) & = \sum\limits_{S\in \mathcal{D}} (\delta_S \sum\limits_{i\in S} x_i) \\ 
& = \sum\limits_{i\in N} x_i \sum\limits_{\{S\in \mathcal{D}\mid i\in S\}}^{} \delta_S \\ 
& = \sum\limits_{i\in N} x_i \\
& = x(N)     
\end{aligned}
$$
现在假设存在一个正数向量$(\delta_S)_{S\in \mathcal{D}}$, 使得对每个$\boldsymbol{x}\in \mathbb{R}^N$, 都有
$$
\sum\limits_{S\in \mathcal{D}}^{} \delta_S x(S) = x(N)
$$
令$\boldsymbol{x} = \mathcal{X}^{\{i\}}$, 就可以得到
$$
\sum\limits_{\{S\in \mathcal{D}\mid i\in S\}}^{} \delta_S = 1, \quad \forall i\in N
$$

下面证明Bondareva-Shapley Theorem的必要性. 令$\boldsymbol{x}\in \mathcal{C}(N; v)$是合作博弈$(N;v)$的核中的一个配置. 特别地, 对每个联盟$S\subseteq N$, 有$x(N) = v(N)$和$x(S)\ge v(S)$成立. 令$\mathcal{D}$是一个平衡的联盟组合, 平衡权重是$(\delta_S)_{S\in \mathcal{D}}$. 因此
$$
\delta_S v(S) \le \delta_S x(S), \quad \forall S\in \mathcal{D}
$$
在$S\in\mathcal{D}$上求和, 结合结论(1), 就可以得到
$$
\sum\limits_{S\in \mathcal{D}}^{} \delta_S v(S) \le \sum\limits_{S\in \mathcal{D}}^{} \delta_S x(S) = x(N) = v(N) 
$$

再证明Bondareva-Shapley Theorem的充分性. 显然, 平衡条件和联盟博弈的核的非空性在策略等价的意义下都是不变的. 根据[1.3. 合作博弈的标准化](#1.3.%20合作博弈的标准化), 每个博弈都策略等价于一个标准化的博弈, 因此我们只要分3类标准化的情形进行讨论即可.
1. $0$-$(-1)$标准化的证明: $0$-$(-1)$标准化的博弈是不平衡的. 
2. $0$-$0$标准化的证明: 当一个博弈是$0$-$0$标准化, 唯一的配置是$\boldsymbol{x}=(0,0,\cdots, 0)$. 用反证法, 如果核是空的, 则存在联盟$S$, 满足$v(S)>0$. 用$\{i_1, i_2, \cdots, i_{n-|S|}\}$表示不在$S$内的参与人集合, 定义联盟组合
   $$
   \mathcal{D} = \{S, \{i_1\}, \{i_2\}, \cdots, \{i_{n-{|S|}}\}\}
   $$
   这个组合是平衡的, 平衡的权重是$\delta_R=1, \forall R\in\mathcal{D}$. 但是
   $$
   \sum\limits_{R\in \mathcal{D}} \delta_R v(R) = v(S) + \sum\limits_{i\not\in S}^{} v(\{i\}) = v(S) > 0 = v(N) 
   $$
   因此该博弈不是平衡的.   
3. $0$-$1$标准化的证明: 我们证明其逆否命题, 即博弈的核是空的$\implies$ 存在某个平衡组合$\mathcal{D}$和权重向量$(\delta_S)_{S\in \mathcal{D}}$, 使得
   $$
   v(N) < \sum\limits_{S\in \mathcal{D}}^{} \delta_S v(S)
   $$ 
   我们首先定义一个辅助性的二人零和策略式博弈, 参与人I的纯策略集是$\{1,2,\cdots, n\}$, 我们将此解释为参与人I在合作博弈$(N; v)$中选择一个参与人. 参与人II的策略集是$\{S\subseteq N\mid v(S)>0\}$, 即合作博弈$(N;v)$中值为正的联盟的组合. 因为博弈是$0$-$1$标准化的, $v(N)=1$, 因此参与人II的策略集非空. 辅助博弈的收益是
   $$
   u_1(i, S) = \begin{cases}  \dfrac{1}{v(S)},\quad &i\in S \\ 0, & i
   \notin S \end{cases}
   $$
   上面的博弈是一个零和博弈, 每个参与人具有有限数目的纯策略. 因此, 根据[二人零和博弈的值](Lecture%203.%20均衡(策略式博弈).md#3.3.%20二人零和博弈的值)和[纳什定理](Lecture%203.%20均衡(策略式博弈).md#2.4.%20纳什定理), 我们可以得到该博弈有一个混合策略的值, 用$\lambda$表示. 考虑参与人I的混合策略$\left(\dfrac{1}{n}, \dfrac{1}{n}, \cdots, \dfrac{1}{n}\right)$, 这个策略保证了他的收益为正并且收益至少为$\dfrac{1}{n}\min\left\{\dfrac{1}{v(S)}\mid v(S)>0\right\}$. 因此, $\lambda$是正的. 设$\boldsymbol{x}=(x_1, x_2, \cdots, x_n)$是参与人I的混合策略, 因为博弈$(N;v)$是0-1标准化的, 所以策略$\boldsymbol{x}$是这个博弈的一个配置. 又因为核是空的, 因此存在联盟$S$使得$v(S)> x(S)\ge 0$. 因为$v(S)>0$, 这意味着$S$是参与人II的一个纯策略, 当参与人I选择混合策略$\boldsymbol{x}$, 参与人II选择纯策略$S$时, 参与人I的收益是
   $$
   u_1(\boldsymbol{x},S) = \sum\limits_{i\in S}^{}  x_iu(i,S) = \sum\limits_{i\in S}^{} \dfrac{x_i}{v(S)} = \dfrac{x(S)}{v(S)} <1
   $$
   这意味着$\lambda<1$. 综上所述, 我们证明了$0<\lambda <1$.
   
   最后, 我们证明合作博弈$(N;v)$是不平衡的. 也就是说, 存在平衡组合$\mathcal{D}$, 满足
   $$
   v(N)< \sum\limits_{S\in \mathcal{D}} \delta_S v(S) 
   $$
   令$\boldsymbol{y}=(y_S)_{\{S\mid v(S)>0\}}$是参与人II在辅助博弈中的最佳策略. 对参与人I的每个混合策略, 这样一个策略保证了期望收益最多为$\lambda$. 考虑
   $$
   \mathcal{D} = \{S\subseteq N\mid v(S)>0\} \cup \{\{1\}, \{2\}, \cdots, \{n\}\}
   $$
   权重是
   $$ 
   \begin{aligned} 
   \delta_S &= \dfrac{y_S}{\lambda v(S)}, \quad v(S)>0\\ 
   \delta_{\{i\}} &= 1 - \sum\limits_{\{S\subseteq N\mid i\in S, v(S)>0\}}^{} \delta_S,\quad \forall i\in N
   \end{aligned}
   $$
   又因为对每个参与人$i\in N$, 都有
   $$
   \sum\limits_{\{S\subseteq N\mid i\in S, v(S)>0\}}^{} \delta_S = \dfrac{1}{\lambda}\sum\limits_{\{S\subseteq N\mid i\in S, v(S)>0\}}^{} \dfrac{y_S}{v(S)} = \dfrac{1}{\lambda} u_1(i, \boldsymbol{y}) \le 1
   $$
   因此, 我们证明了$\mathcal{D}$是一个弱平衡组合. 然而
   $$
   \begin{aligned} 
       \sum\limits_{S\in \mathcal{D}} \delta_S v(S) &= \sum\limits_{j\in N}
   \delta_{\{j\}} v(j) + \sum\limits_{\{S\subseteq N\mid v(S)>0\}}^{} \delta_Sv(S) \\ 
   & = \sum\limits_{\{S\subseteq N\mid v(S)>0\}}^{}  \dfrac{y_S}{\lambda v(S)}v(S) \\ 
   & = \dfrac{1}{\lambda}\\ 
   & >1 = v(N)
   \end{aligned}
   $$
   这就证明了我们想证的结论.
#####
___

### 2.6. 平衡与完全平衡
设$(N; v)$是合作博弈, 如果$(N;v)$的核是非空的, 那么就称$(N;v)$是平衡的.

如果$(N;v)$的每个子博弈的核都是非空的, 那么就称$(N;v)$是完全平衡的.
___
##### Example 平衡博弈不一定是完全平衡的:
设$(N;v)$是一个合作博弈, 这里$N=\{1,2,3\}$, 合作函数$v$给出如下的收益分配
$$
v(1) =v(2) = v(3)=10, v(1,2) = v(1,3)=v(2,3)=15, v(1,2,3)=90
$$ 
配置$\boldsymbol{x} = (30,30,30)$在博弈的核中. 但是另一方面, 局限在$\{1,2\}$上的博弈$(\{1,2\}; v)$的核是空的, 因此, $(N;v)$是平衡的, 但不是完全平衡的.
#####
___
### 2.7. 平衡覆盖与完全平衡覆盖
合作博弈$(N;v)$的平衡覆盖是定义如下的合作博弈$(N; \widetilde{v})$, 其中$\mathcal{P}(N) = \{S\subseteq N\mid S\not= \varnothing\}$表示非空联盟的组合. 
$$
\widetilde{v}(S):= \begin{cases}v(S) & \text { if } S \neq N \\ \max \left\{\sum\limits_{S \in \mathcal{P}(N)} \delta_S v(S)\right\} & \text { if } S=N\end{cases}
$$

合作博弈$(N;v)$的完全平衡覆盖是定义如下的合作博弈$(N; \widehat{v})$, 对每个非空联盟$S\subseteq N$, 有
$$
\widehat{v}(S) = \max\left\{\sum\limits_{\{R\subseteq S\mid R\not=\varnothing\}}^{} \delta_Rv(R)\ \Big| \ \sum\limits_{\{R\subseteq S\mid R\not=\varnothing\}}^{}\delta_R\boldsymbol{r}^R=\boldsymbol{r}^S, \delta_R\ge 0, \forall R\subseteq S\right\}
$$
并且$\widehat{v}(\varnothing)=0$

合作博弈$(N;v)$是平衡的, 当且仅当$\widetilde{v}(N) = v(N)$; 合作博弈$(N;v)$是完全平衡的, 当且仅当$\widehat{v}(N) = v(N)$.
___
##### Proof
我们首先证明$\widetilde{v}(N) > v(N)$. 因为$\{N\}$是一个平衡组合, 因此根据定义, 有$\widetilde{v}(N) \ge  v(N)$. 于是我们只需要证明合作博弈$(N;v)$具有一个非空核, 当且仅当$\widetilde{v}(N) \le  v(N)$. 根据[2.5. Bondareva-Shapley Theorem](#2.5.%20Bondareva-Shapley%20Theorem%20), 合作博弈的核是非空的, 当且仅当
$$
v(N) \geq \sum_{S \in \mathcal{P}(N)} \delta_S v(S), \quad \forall \delta\in P
$$
即当且仅当
$$
v(N) \geq \max \left\{\sum_{S \in \mathcal{P}(N)} \delta_S v(S) \right\}=\widetilde{v}(N)
$$
合作博弈$(N;v)$是平衡的, 当且仅当$\widetilde{v}(N) = v(N)$

合作博弈$(N;v)$是完全平衡的, 当且仅当对每个非空联盟$S\subseteq N$, 合作博弈$(S, v)$是平衡的. 假设$S\subseteq N$是非空联盟. 博弈$(S;v)$是平衡的, 当且仅当
$$
v(S) =\max \left\{\sum_{R \in \mathcal{P}(N)} \delta_R v(R) \right\}=\widehat{v}(S)
$$
因为$v(\varnothing)=0=\widehat{\varnothing}$, 这意味着博弈$(N;v)$是完全平衡的, 当且仅当$\widehat{v}(S) = v(S)$对每个$S\subseteq N$成立. 
#####
___

## 3. 完全平衡博弈的几个刻画
### 3.1. 市场博弈
#### 3.1.1. 市场的定义
市场是由向量$(N, L, (\boldsymbol{a}_i, u_i)_{i\in N})$给出的, 这里
1. $N=\{1,2,\cdots, n\}$是生产者集
2. $L =\{1,2,\cdots, l\}$是商品集
3. 对每个$i\in N$, $\boldsymbol{a}_i\in \mathbb{R}^L_+$是生产者$i$的初始禀赋, 这意味着市场上每种商品的量都是有限的. 
4. 对每个$i\in N$, $u_i\in \mathbb{R}^L_+\to \mathbb{R}$是生产者$i$的效用函数

联盟$S$的一个配置是商品组合的一个集合$(\boldsymbol{x}_i)_{i\in S}$, 这里$\boldsymbol{x}_i\in \mathbb{R}_+^L$是生产者$i$的商品组合. 满足$x(S) = a(S)$. 我们用$X^S$表示联盟$S$的所有配置的集合
$$
X^S = \left\{(\boldsymbol{x}_i)_{i\in S}\in \mathbb{R}_+^{L}\ \Big|\ \forall i\in S, x(S)=a(S)\right\} \subseteq \mathbb{R}_+^{S\times L}
$$

#### 3.1.2. 市场博弈
联盟博弈$(N;v)$是一个市场博弈, 如果存在正数$l$, 对每个参与人$i\in N$, 存在一个初始禀赋$\boldsymbol{a}_i\in \mathbb{R}^L_+$和一个连续concave函数$u_i: \mathbb{R}_+^L\to \mathbb{R}$ ($L=\{1,2,\cdots, l\}$), 使得下式对每个联盟$S\in \mathcal{P}(N)$成立
$$
v(S) = \max \left\{\sum\limits_{i\in S}^{} u_i(x_i)\ \Big| \ \boldsymbol{x}=(x_i)_{i\in S}\in X^S\right\} \tag{2}
$$
___
##### Proof
为了说明这个定义是有效的, 我们必须证明$(2)$中的$\max$是有意义的, 也就是说, $(2)$所定义的集合的极大值是能取到的. 因为所有的生产函数$(u_i)_{i\in N}$都是连续的, 函数$\sum\limits_{i\in S}^{} u_i$作为有限个连续函数的加总, 也是连续函数. 因为连续函数在紧急上的最大值总能取到, 又因为$X^S$是有界闭集因此也是紧的, 于是我们推断出, 当生产函数$u_i$是连续的时候, 由$(2)$定义的极大值总是能取到的. 
#####
___

#### 3.1.3. 市场博弈和完全平衡博弈
市场博弈$(N;v)$的子博弈$(S;v)$仍然是市场博弈, 并且, 合作博弈$(N;v)$是一个市场博弈, 当且仅当它是完全平衡的. 
___
##### Proof
首先证明市场博弈$(N;v)$的子博弈$(S;v)$仍然是市场博弈. 设$(N, L, (\boldsymbol{a}_i, u_i)_{i\in N})$是一个市场, $(N;v)$是基于此的市场博弈. 假设剩下的生产者是联盟$S$的成员, 这形成了一个新市场$(S, L, (\boldsymbol{a}_i, u_i)_{i\in N})$. 如果我们用$(S, \widetilde{v})$表示新的市场博弈, 那么对于每个联盟$T\subseteq S$, 我们有
$$
\widetilde{v}(T)=\max \left\{\sum_{i \in T} u_i\left(x_i\right),\ x_i \in \mathbb{R}_{+}^L\ \Big|\   \forall i \in T, x(T)=a(T)\right\}=v(T)
$$
这表明市场博弈$(N;v)$的子博弈$(S;v)$仍然是市场博弈. 接下来, 我们证明合作博弈$(N;v)$是一个市场博弈, 当且仅当它是完全平衡的. 

首先证明必要性, 也就是说如果合作博弈$(N;v)$是一个市场博弈, 那么它是完全平衡的. 又因为我们已经说明了市场博弈的子博弈仍然是市场博弈, 因此我们只要证明如果合作博弈$(N;v)$是一个市场博弈, 那么它是平衡的. 根据市场博弈的定义, 我们知道, 对每个联盟$S$, 存在一个配置$(\boldsymbol{x}^S_i)_{i\in S}$满足
1. 对每个$i\in N$, $\boldsymbol{x}_i^S\in \mathbb{R}_+^L$成立
2. $\sum\limits_{i\in S}^{} u_i(\boldsymbol{x}_i^S) =v(S)$

令$\boldsymbol{\delta}=(\delta_S)_{S\in \mathcal{P}(N)}\in P$是弱平衡$\mathcal{P}(N)$的系数向量. 对每个$i\in N$, 用$\boldsymbol{z}_i$表示参与人$i$得到的商品组合. 
$$
\boldsymbol{z}_i = \sum\limits_{\{S\in \mathcal{P}(N)\mid i\in S\}}^{} \delta_S \boldsymbol{x}_i^S 
$$
根据$z_i$的定义, 我们有
$$
\begin{aligned} 
z(N) &= \sum\limits_{i\in N}^{} \boldsymbol{z}_i =\sum\limits_{i\in N}^{}\sum\limits_{\{S\in \mathcal{P}(N)\mid i\in S\}}^{}\delta_S\boldsymbol{x}_i^S \\   
  & = \sum\limits_{S\in \mathcal{P}(N)}^{}\delta_S \sum\limits_{i\in S}^{}\boldsymbol{x}_i^S \\ 
  &= \sum\limits_{S\in \mathcal{P}(N)}^{}\delta_S \left(\sum\limits_{i\in N}^{} \boldsymbol{a}_i\right) \\ 
  & = \sum\limits_{i\in N}^{} \boldsymbol{a}_i\sum\limits_{\{S\in \mathcal{P}(N)\mid i\in S\}}^{}\delta_S \\ 
  &= a(N)  
\end{aligned}
$$
再根据函数$v$的定义, 我们有
$$
\begin{aligned} 
   v(N)& \ge \sum\limits_{i\in N}^{} u_i(\boldsymbol{z}_i) \\ 
   & =  \sum\limits_{i\in N}^{} u_i\left(\sum\limits_{\{S\in \mathcal{P}(N)\mid i\in S\}}^{}\delta_S\boldsymbol{x}_i^S\right) \\ 
   & \ge \sum\limits_{i\in N}^{} \sum\limits_{\{S\in \mathcal{P}(N)\mid i\in S\}}^{}\delta_Su_i\left(\boldsymbol{x}_i^S\right) \\ 
   & = \sum\limits_{S\in \mathcal{P}(N)}^{}\delta_S\sum\limits_{i\in S}^{}u_i\left(\boldsymbol{x}_i^S\right) \\
   & = \sum\limits_{S\in \mathcal{P}(N)}^{}\delta_S v(S) \\
\end{aligned}
$$
这就证明了市场博弈$(N;v)$是平衡的.

接下来, 我们证明完全平衡的博弈都是市场博弈. 因为策略等价不影响完全平衡性, 因此我们只要考虑$0$标准化的情形. 
#####
___

### 3.2. 可加的博弈
#### 3.2.1. 可加博弈的定义
合作博弈$(N; v)$是可加的, 如果对下面的每个非空联盟$S$, 都有
$$
v(S) =\sum\limits_{i\in S}^{ } v(\{i\})
$$


### 3.2.2. 可加博弈与完全平衡
合作博弈$(N; v)$是完全平衡的, 当且仅当它是有限数量可加博弈中最小的. 这里, 可加博弈$(N; v_1), (N; v_2), \cdots, (N; v_k)$的最小博弈定义为$(N;v)$, 其中
$$
v(S) = \min\{v_1(S), v_2(S), \cdots, v_k(S)\}, \quad \forall S\subseteq N
$$