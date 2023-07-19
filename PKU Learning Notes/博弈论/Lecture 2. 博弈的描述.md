## 1. 扩展式博弈
### 1.1. 树状图
树状图是满足下列条件的一个三元组合$(V, E, x^0)$: 
1. $(V, E)$是一个有向图
2. 节点$x^0$是树状图的根, 对每一个节点$x\in V$, 在图形中从$x^0$到$x$的路径是唯一的. 

### 1.2. 完全信息扩展式博弈
完全信息扩展式博弈是一个有序的向量
$$
\Gamma=\left(N, V, E, x^0,\left(V_i\right)_{i \in N}, O, u\right)
$$
其中
1. $N$是参与人的有限集合. 
2. $(V, E, x^0)$是一个树状图, 叫做博弈树.
3. $\left(V_i\right)_{i \in N}$ 是非终节点的集合
4. $O$是可能的博弈结果的集合
5. $u$是将博弈树的每个终节点映射到$O$中结果的函数. 

完全信息扩展式博弈隐含的假定是
1. 当博弈展开到了当前的点, 参与人知道此前所有的行动.
2. 博弈树的深度是有限的. 扩展式博弈的定义可以推广到博弈树深度是无限的情况, 但需要用到测度论等数学工具.  

![image-20230712140850415](./Lecture%202.%20%E5%8D%9A%E5%BC%88%E7%9A%84%E6%8F%8F%E8%BF%B0.assets/image-20230712140850415.png)

例如, 在上面的这个博弈树中
$$
\begin{aligned}
N & =\{\mathrm{I}, \mathrm{II}\} \\
V & =\{r, a, b, c, d, e, f, g, h, i, j, k, l, m, p, q, s, w, y, z\} \\
x^0 & =r \\
V_{\mathrm{I}} & =\{r, f, h, j, k\} \\
V_{\mathrm{II}} & =\{b, c, d, q, w\} \\
O & =\{\mathrm{I} \text { wins, II wins } \} \\ 
u(a)&=u(l)=u(m)=u(p)=u(s)=\text { II wins } \\
u(e)&=u(g)=u(i)=u(y)=u(z)=\text { I wins }
\end{aligned}
$$

### 1.3. 包含随机行动的完全信息扩展式博弈
在模型中加入随机行动意味着在博弈中加入一个新的参与人Nature, 用$0$表示. 对于每个要实施随机行动的节点, 用$p_x$表示在节点$x$处的概率向量. 

正式来说, 包含随机行动的完全信息扩展式博弈是如下的向量: 
$$
\Gamma=\left(N, V, E, x^0,\left(V_i\right)_{i \in N}, (p_x)_{x\in V_0},O, u\right)
$$
其中
1. $N$是参与人的有限集合. 
2. $(V, E, x^0)$是博弈树.
3. $\left(V_i\right)_{i \in N\cup \{0\}}$ 是非终节点的集合.
4. 对于每个$x\in V_0$, $p_x$是从$x$出发的边的集合的概率分布.
5. $O$是可能的博弈结果的集合.
6. $u$是将博弈树的每个终节点映射到$O$中结果的函数. 

包含随机行动的完全信息扩展式博弈额外隐含的假设: 所有参与人都知道随机行动的概率, 即便是博弈的行动涉及下雨的概率, 地震的概率或是股市暴跌的概率. 


### 1.4. 信息集
假设$\Gamma = (N, V, E, x^0, (V_i)_{i\in N\cup \{0\}}, (p_x)_{x\in V_0}, O, u)$是一个扩展式博弈. 参与人$i$的信息集是二元组$(U_i, A(U_i))$, 满足
1. $U_i= \{x_i^1, x_i^2, \cdots, x_i^m\}$是$V_i$的子集, 在$U_i$的每个节点, 参与人$i$拥有相同数量的行动$l_i = l_i(U_i)$, 即
   $$
   \left|A\left(x_i^j\right)\right| = l_i, \forall j=1,2,\cdots, m
   $$
   其中$A(x)$是在节点$x$处所有可能的行动的集合. 
2. $A\left(U_i\right) = \alpha_i^1\cup \alpha_i^2 \cup \cdots \cup \alpha_i^{l_i}$ 是对集合$\bigcup\limits_{j=1}^m A\left(x_i^j\right)$的一个分划. $\alpha_i^k$是从$A\left(x_i^j\right), \forall j=1,2,\cdots, m$分别取一个元素组成的$m$元集合.  分划 $A\left(U_i\right)$ 就叫做参与人 $i$ 在信息集 $U_i$ 中的行动集.

当博弈的展开到达信息集$U_i$的节点$x$时(信息集是已知的, 节点$x$是不知道的). 参与人无法选择一个从节点$x$出发的边. 分划$A\left(U_i\right)$的元素$\alpha_i^1, \alpha_i^2, \cdots, \alpha_i^{l_i}$是参与人可以选择的行动. 如果参与人$i$从$\alpha_i^k$中选择了一个元素, 博弈就沿着$\alpha_i^k \cap A(x)$中唯一的边继续展开. 

### 1.5. 包含随机行动的不完全信息扩展式博弈
包含随机行动的不完全信息扩展式博弈是如下的向量
$$
\Gamma=\left(N, V, E, x^0,\left(V_i\right)_{i \in N}, (p_x)_{x\in V_0},\left(U_i^j\right)_{i\in N}^{j=1,\cdots, k_i}, O, u\right)
$$
其中
1. $N$是参与人的有限集合. 
2. $(V, E, x^0)$是博弈树.
3. $\left(V_i\right)_{i \in N\cup \{0\}}$ 是非终节点的集合.
4. 对于每个$x\in V_0$, $p_x$是从$x$出发的边的集合的概率分布.
5. 对每一个$i\in N$, $\left(U_i^j\right)^{j=1,\cdots, k_i}$是$V_i$的一个分划.
6. 对每一个 $i \in N$ 以及 $j \in\{1,2, \cdots, k\},\left(U_i^j, A\left(U_i^j\right)\right)$ 是参与人 $i$ 的一个信息集
7. $O$是可能的博弈结果的集合.
8. $u$是将博弈树的每个终节点映射到$O$中结果的函数. 

如果参与人$i$的每个信息集都只包含一个节点. 那么这样的扩展式博弈就叫做参与人$i$的完全信息博弈. 如果一个扩展式博弈对所有的参与人而言都是完全信息博弈, 那么这个博弈就叫做完全信息博弈. 因此完全信息博弈是实际上是不完全信息博弈的一个退化特例, 

### 1.6. 子博弈
令$\Gamma=\left(N, V, E, x^0,\left(V_i\right)_{i \in N}, (p_x)_{x\in V_0},\left(U_i^j\right)_{i\in N}^{j=1,\cdots, k_i}, O, u\right)$为包含随机行动和不完全信息的扩展式博弈. 令$x\in V$是博弈树中的一个节点, 从$x$出发的子博弈$\Gamma(x)$就是扩展式博弈
$$
\Gamma(x) = \left(N, V(x), E(x), x,\left(V_i(x)\right)_{i \in N}, (p_y)_{y\in V_0},\left(U_i^j\right)_{i\in N}^{j=s_1,\cdots, s_{t_j}}, O, u\right)
$$
这里
1. 参与人的集合$N$与在博弈$\Gamma$中一样
2. 节点的集合$V(x)$包含$x$, 包括博弈树$(V, E, x^0)$中$x$的所有子节点. 对于每个参与人$i$的每一个信息集$(U_i, A(U_i))$. $U_i$要么全在$V(x)$中, 要么全不在$V(x)$中.
3. 边的集合$E(x)$包括$E$中连接$V(x)$中节点的所有边.
4. 参与人$i$是决策者的节点集合为$V_i(x) = V_i\cap V(x)$.
5. Nature的概率分布是在博弈$\Gamma$中Nature的概率分布. 
6. $\left(U_i^j\right)_{i\in N}^{j=s_1,\cdots, s_{t_i}}$是$V(x)$的一个分划, $\{s_1,\cdots, s_{t_i}\}$是从$\{1,2, \cdots, k_i\}$中抽取的指标集合. 
7. 子博弈可能结果的集合是博弈$\Gamma$中可能结果的集合.
8. 将终节点映射到结果的函数是函数 $u$, 不过其定义域限制在博弈树 $(V(x), E(x), x)$ 中终节点的集合.
  
### 1.7. 策略
参与人$i$的策略$s_i$是一个函数: 
$$
s_i : \mathcal{U}_i \mapsto  \bigcup\limits_{j=1}^{k_i}  A\left(U_i^j\right),\quad \mathcal{U}_i = \{U_i^1, \cdots, U_i^{k_i}\}
$$
对每一个信息集$U_i^j\in \mathcal{U}_i$
$$
s_i(U_i^j) \in A\left(U_i^j\right)
$$

策略向量是参与人策略的罗列$\boldsymbol{s} = (s_i)_{i\in N}$. 一个策略向量决定了博弈结果上的概率分布. 


## 2. 策梅洛定理
### 2.1. 策梅洛定理
在任何的完全信息有限的两人博弈中, 如果结果集为$O=\{\text{I wins}, \text{II wins}, \text{Draw}\}$, 那么下面的三种情况有且仅有一种成立
1. 参与人I有必胜策略.
2. 参与人II有必胜策略.
3. 参与人I和参与人II都有至少保证和局的策略. 
___
##### Proof
考虑该完全信息有限博弈的博弈数$\Gamma$, 对于$\Gamma$的任何一个子博弈$\Gamma(x)$, 用$n_x$表示子博弈$\Gamma(x)$的节点数. 我们对$n_x$进行归纳. 

当$n_x=1$时, $x$是一个终局的节点. 由于结果集为$O=\{\text{I wins}, \text{II wins}, \text{Draw}\}$, 因此$\varnothing$分别是三种不同的结果的情况下I的必胜策略, II的必胜策略和双方至少保证和局的策略. 

接下来, 假设对于任意的$\Gamma(y)$满足$n_y< n_x$的节点$y$, 都有结论成立. 不失一般性, 假设参与者I在$\Gamma(x)$先做出决策. 用$C(x)$表示参与者I从$x$出发进行一次行动所能到达的所有节点的集合. 
1. 如果存在$y_0\in C(x)$使得参与者I在$\Gamma(y_0)$中有一个必胜策略, 那么参与者I在$\Gamma(x)$中有一个必胜策略.
2. 如果对于每一个节点$y\in C(x)$, 参与者在$\Gamma(y)$都有一个必胜策略, 那么无论如何, 那么参与者II在$\Gamma(x)$中都有一个必胜策略.
3. 否则, 1,2都不成立. 1不成立意味着对任意的$y\in C(x)$, 根据归纳假设, 或者参与者II在$\Gamma(y)$中有必胜策略, 或者双方在$\Gamma(y)$中都有至少保证和局的策略. 2不成立意味着存在节点$y_0\in C(x)$使得参与者II在$\Gamma(y_0)$中没有必胜策略. 因此, 双方在$\Gamma(y_0)$中都有一个至少保证和局的策略. 此时参与者I选择行动到达$y_0$. 
#####
___

### 2.2. 大卫-盖尔博弈(Chomp)
考虑一块$n\times m$的棋盘, 每个方格是由一对坐标$(i, j)$表示$(1\le i\le n, 1\le j\le m)$. 按照以下的规则, 每个参与人依次占领方格: 如果在某个阶段方格$(i_0, j_0)$被占领了, 那么所有$i\ge i_0, j\ge j_0$的方格$(i, j)$都可以被视为从棋盘中移走了. 对任意一个有限的$n\times m$棋盘$(m\times n>1)$, 开局的参与人I有必胜策略. 
___
##### Proof
因为Chomp博弈中没有和局, 因此根据策梅洛定理, 该博弈只有可能有如下的两种可能性:
1. 参与人I有必胜策略
2. 参与人II有必胜策略

于是我们只需要证明如果II有必胜策略, 那么I也有必胜策略. 假设参与人II有必胜策略$s_{\mathrm{II}}$. 假设参与人第一步占领了最右上方的方格$(n,m)$, 策略$s_{\mathrm{II}}$保证参与人II胜利. 假设根据策略$s_{\mathrm{II}}$的下一个行动是占领方格$(i_0, j_0)$. 剩下的子博弈让II有必胜策略. 但I可以选择第一步占领$(i_0, j_0)$, 这就意味着I有必胜策略. 
#####
___

## 3. 策略式博弈
### 3.1. (纯策略)策略式博弈
纯策略策略式博弈是一个有序向量$G = (N, (S_i)_{i\in N}, (u_i)_{i\in N})$, 其中
1. $N=\{1,2, \cdots, n\}$ 是参与人的有限集合
2. 对每个参与人 $i \in N, S_i$ 是参与人 $i$ 的策略集合. 我们用 $S=S_1 \times S_2 \times \cdots \times S_n$ 表示所有策略向量的集合
3. 对每个参与人 $i \in N, u_i: S \rightarrow \mathbb{R}$ 是连接策略向量 $\boldsymbol{s}=\left(s_i\right)_{i \in N}$ 和参与人 $i$ 的效用 $u_i(\boldsymbol{s})$ 的函数


### 3.2. 混合策略集
令 $G=\left(N,\left(S_i\right)_{i \in N},\left(u_i\right)_{i \in N}\right)$ 是一个策略式博弈, 其每个参与人的策略集都是有限的。参与人 $i$ 的混合策略集是其策略集 $S_i$ 的概率分布。参与人 $i$ 的混合策略集记作:
$$
\Sigma_i =\left\{\sigma_i: S_i \mapsto [0,1] \ \Big| \   \sum_{s_i \in S_i} \sigma_i\left(s_i\right)=1\right\}
$$
每个纯策略都可以$s_i$都可以被看成是一个混合策略$\sigma_i = [1(s_i)]$. 


### 3.3. (混合策略)策略式博弈
令 $G=\left(N,\left(S_i\right)_{i \in N},\left(u_i\right)_{i \in N}\right)$ 为策略式博弈, 对于每一个参与人 $i \in N$, 纯策略集 $S_i$ 是非空、有限集合. 用 $S:=S_1 \times S_2 \times \cdots \times S_n$ 表示纯策略向量的集合。 $G$ 的混合扩展就是如下的博弈
$$
\Gamma=\left(N,\left(\Sigma_i\right)_{i \in N},\left(U_i\right)_{i \in N}\right)
$$
这里, 对每个 $i \in N$, 参与人 $i$ 的策略集是 $\Sigma_i=\Delta\left(S_i\right)$, 其中$\Delta(S_i)$表示$S_i$上的所有概率分布. 参与人 $i$的收益函数是函数 $U_i: \Sigma \rightarrow \mathbb{R}$, 这个函数将每个策略向量 $\boldsymbol{\sigma}=\left(\sigma_1, \cdots, \sigma_n\right) \in \Sigma=\Sigma_1 \times \cdots \times \Sigma_n$ 和如下的收益函数连接起来:
$$
U_i(\boldsymbol{\sigma})=\mathbb{E}_{\boldsymbol{\sigma}}\left[u_i(\boldsymbol{s})\right]=\sum_{\left(s_1, \cdots, s_n\right) \in S} u_i\left(s_1, \cdots, s_n\right) \sigma_1\left(s_1\right) \sigma_2\left(s_2\right) \cdots \sigma_n\left(s_n\right)
$$


### 3.4. 混合策略的收益函数
令 $G=\left(N,\left(S_i\right)_{i \in N},\left(u_i\right)_{i \in N}\right)$ 是一个策略式博弈, 每个参与人的策略集 $S_i$ 是有限的, 令 $\Gamma=\left(N,\left(\Sigma_i\right)_{i \in N},\left(U_i\right)_{i \in N}\right)$ 是其混合扩展。那么对于每个参与人 $i \in N$, 函数 $U_i$ 是 $n$ 个变量 $\left(\sigma_i\right)_{i \in N}$ 的多线性函数, 即对每个参与人 $i$, 对每个 $\sigma_i, \sigma_i^{\prime} \in \Sigma_i$, 对每个 $\lambda \in[0,1]$
$$
U_i\left(\lambda \sigma_i+(1-\lambda) \sigma_i^{\prime}, \boldsymbol{\sigma}_{-i}\right)=\lambda U_i\left(\sigma_i, \boldsymbol{\sigma}_{-i}\right)+(1-\lambda) U_i\left(\sigma_i^{\prime}, \boldsymbol{\sigma}_{-i}\right),\quad  \forall \boldsymbol{\sigma}_{-i} \in \Sigma_{-_i}
$$
___
##### Proof
因为
$$
U_i(\boldsymbol{\sigma})=\sum_{\left(s_1, \cdots, s_n\right) \in S} u_i\left(s_1, \cdots, s_n\right) \sigma_1\left(s_1\right) \sigma_2\left(s_2\right) \cdots \sigma_n\left(s_n\right)
$$
对每个$i\in N$和$1\le j \le m_i$, 对每个$\boldsymbol{s} = (s_1, s_2, \cdots, s_n)$, 函数
$$
\sigma_i(s_i^j) \mapsto u_i(s_1, s_2, \cdots, s_n)\sigma_1(s_1)\sigma(s_2)\cdots \sigma_n(s_n)
$$
是一个常数函数(如果$s_i\neq s_i^j$)或者是$\sigma_i(s_i^j)$的线性函数(如果$s_i=s_i^j$). 因此, 函数 $U_i$, 作为 $\sigma_i\left(s_i^j\right)$ 的线性函数的加总, 也是 $\sigma_i\left(s_i^j\right)$ 的线性函数. 这意味着, 对每个 $i \in N$, 函数 $U_i\left(\cdot, \boldsymbol{\sigma}_{-i}\right)$ 对每个 $\sigma_i$ 的每个坐标 $\sigma_i\left(s_i^j\right)$ 是线性的, 对所有的 $\boldsymbol{\sigma}_{-i} \in \Sigma_{-i}$, 对每 个 $\lambda \in[0,1]$, 每个 $\sigma_i, \sigma_{i^{\prime}} \in \Sigma_i$ :
$$
U_i\left(\lambda \sigma_i+(1-\lambda) \sigma_i^{\prime}, \boldsymbol{\sigma}_{-i}\right)=\lambda U_i\left(\sigma_i, \boldsymbol{\sigma}_{-i}\right)+(1-\lambda) U_i\left(\sigma_i^{\prime}, \boldsymbol{\sigma}_{-i}\right)
$$
#####
___


### 3.5. 策略等价
两个策略式博弈 $\left(N,\left(S_i\right)_{i \in N},\left(u_i\right)_{i \in N}\right)$ 和 $\left(N,\left(S_i\right)_{i \in N},\left(v_i\right)_{i \in N}\right)$, 拥有相同的参与人集合和相同的纯策略集, 如果对每一个参与人 $i$, 函数 $v_i$ 是函数 $u_i$ 的正向仿射变换,那么这两个博弈是策略等价的。换言之, 存在 $\alpha_i>0, \beta_i \in \mathbb{R}$ 使得
$$
v_i(s)=\alpha_i u_i(s)+\beta_i,\quad  \forall s \in S
$$

令$G$和$\widehat{G}$是两个策略等价的策略式博弈. 博弈$G$的每一个混合策略均衡$\boldsymbol{\sigma}=(\sigma_1, \cdots, \sigma_n)$也是博弈$\widehat{G}$的混合策略均衡. 