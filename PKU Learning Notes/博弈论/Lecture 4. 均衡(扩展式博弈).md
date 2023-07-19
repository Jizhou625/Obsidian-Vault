## 1. 信息的价值
### 1.1. 库恩定理
每一个完全信息有限博弈都有至少一个纯策略纳什均衡.
___
##### Proof
采用数学归纳法, 假定对于所有节点数少于$K$的完全信息扩展式博弈, 存在一个纯策略纳什均衡. 下面证明对于节点数为$K$的扩展式博弈, 也存在一个纯策略纳什均衡.
1. 若根节点$v_0$是一个随机行动. 对每个参与人$i$, 如果节点$x^{l}$在第一步被选中, 那么在子博弈$\Gamma(x^l)$中执行策略$s_i^{*l}$. 根据定义, 有
   $$
   u_i(\boldsymbol{s}^*) = \sum\limits_{l=1}^{L} p^l u^l_i(\boldsymbol{s}^{*l})
   $$
   我们将证明策略向量$\boldsymbol{s}^*$是一个纳什均衡. 否则, 假设参与人$j$转向另一个不同的策略$s_j$. 设$s_j^l$将$s_j$限定在$\Gamma(x^l)$. 参与人$j$在策略$(s_j^l, \boldsymbol{s}_{-j}^l)$下的期望收益为
   $$
   \sum\limits_{l=1}^{L} p^l u^l_j(s_j^l, \boldsymbol{s}_{-j}^{*l})
   $$
   因为$\boldsymbol{s}^{*l}$是一个均衡, 因此对于所有的$l=1,2,\cdots, L$, $u_j^l(s_j^l, \boldsymbol{s}_{-j}^{*l})\le u_{j}^l(\boldsymbol{s}^{*l})$. 因此
   $$
   u_j\left(s_j, \boldsymbol{s}_{-j}^*\right)=\sum_{l=1}^L p^l u_j^l\left(s_j^l, \boldsymbol{s}_{-j}^{* l}\right) \leqslant \sum_{l=1}^L p^l u_j^l\left(\boldsymbol{s}^{* l}\right)=u_j\left(\boldsymbol{s}^*\right)
   $$
   这就证明了$j$没有转变策略的动机. 
2. 根节点参与人$i_0$的决策节点. 对每个参与人$i\neq i_0$, 定义策略${s}_i^*$: 如果节点$x^l$在博弈展开的第一个行动中被选用, 在子博弈$\Gamma(x^l)$中执行策略$s_i^{*l}$. 对参与人$i_0$, 定义策略$s_{i0}^*$: 在根节点选择子节点$x^{l_0}$使得实现最大值$\max\limits_{1\le l\le L}u_{i0}^l(\boldsymbol{s}^{*l})$. 不难证明, 没有人有动机偏离这样的策略. 
#####
___

### 1.2. 信息对最大最小值的改善
令 $\Gamma$ 为一个扩展式博弈, 将 $\Gamma$ 中参与人 $i$ 的几个信息集分裂之后得到的新博弈称为 $\Gamma^{\prime}$. 博弈 $\Gamma^{\prime}$ 中参与人 $i$ 的混合策略最大最小值, 大于或等于他在 $\Gamma$ 中的混合策略最大最小值, 而且他在 $\Gamma^{\prime}$ 中的混合策略最小最大值, 大于或等于他在 $\Gamma$ 中的混合策略最小最大值. 也就是说
$$
\underline{v}_i \le \underline{v}^{\prime}_i ,\quad \overline{v}_i \le \overline{v}^{\prime}_i
$$

### 1.3. 信息并不总是改善均衡的结果
![image-20230718003340794](./Lecture%204.%20%E5%9D%87%E8%A1%A1(%E6%89%A9%E5%B1%95%E5%BC%8F%E5%8D%9A%E5%BC%88).assets/image-20230718003340794.png)

在上面的例子中, Game A唯一的均衡是如下的混合策略
$$
\left(\left[\dfrac{1}{2}(l), \dfrac{1}{2}(r)\right]; \left[\dfrac{1}{2}(L), \dfrac{1}{2}(R), 0(M)\right]\right)
$$
而Game B的均衡是
$$
\left((l_1, r_2), \left[0(L), 0(R), 1(M)\right]\right)
$$
尽管参与人I获得了更多的信息, 但是他的收益却降低了.

## 2. 行为策略
### 2.1. 行为策略的定义
在扩展式博弈中, 一个参与人的行为策略是一个函数, 这个函数将他的每个信息集映射到那个信息集中可能行动集合的概率分布
$$
b_i : \mathcal{U}_i \to \bigcup_{U_i\in \mathcal{U}_i}\Delta(A(U_i)),\quad b_i(U_i)\in \Delta(A(U_i))
$$
我们用$\mathcal{B}_i$表示参与人$i$的行为策略集合.


### 2.2. 等价的定义
用$\rho(x;\boldsymbol{\sigma})$表示策略向量为$\boldsymbol{\sigma}$时, 博弈的展开到访节点$x$的概率. 在扩展式博弈中, 如果对参与人 $N \backslash\{i\}$ 的每个混合 (或行为) 策略向量 $\boldsymbol{\sigma}_{-i}$ 以及博弈树的每个节点 $x$, 下式成立, 那么, 参与人 $i$ 的混合策略 $\sigma_i$ 和行为策略 $b_i$ 互相等价:
$$
\rho\left(x ; \sigma_i, \boldsymbol{\sigma}_{-i}\right)=\rho\left(x ; b_i, \boldsymbol{\sigma}_{-i}\right)
$$

### 2.3. 行为策略和混合策略的差异
1. 下面的例子表明存在混合策略, 其没有等价的行为策略

   ![image-20230718005335410](./Lecture%204.%20%E5%9D%87%E8%A1%A1(%E6%89%A9%E5%B1%95%E5%BC%8F%E5%8D%9A%E5%BC%88).assets/image-20230718005335410.png)
   不难验证, 混合策略
   $$
   \sigma_{\mathrm{I}}=\left[\frac{1}{2}\left(T_1 T_2\right), 0\left(T_1 B_2\right), 0\left(T_2 B_1\right), \frac{1}{2}\left(B_1 B_2\right)\right]
   $$
   不存在对应的行为策略.

2. 下面的例子表明存在行为策略, 其没有等价的混合策略

   ![image-20230718005649099](./Lecture%204.%20%E5%9D%87%E8%A1%A1(%E6%89%A9%E5%B1%95%E5%BC%8F%E5%8D%9A%E5%BC%88).assets/image-20230718005649099.png)

   考虑行为策略$\left[\dfrac{1}{2}(L), \dfrac{1}{2}(R)\right]$, 其导致结果的概率分布为
   $$
   \left[\frac{1}{4}\left(O_1\right), \frac{1}{4}\left(O_2\right), \frac{1}{2}\left(O_3\right)\right]
   $$
   而纯策略只能导致$O_3$和$O_1$. 因此混合策略不能以正的概率导致$O_2$.


### 2.4. 行为策略均衡
在一个有限扩展式博弈中, 如果所有的参与人都有完美记忆, 那么这个博弈有行为策略纳什均衡. 
___
##### Proof
根据[[Lecture 3. 均衡(策略式博弈)#2.4. 纳什定理]], 这个博弈有混合策略纳什均衡$\boldsymbol{\sigma}^* = (\sigma_i^*)_{i\in N}$. 因为博弈中所有的参与人都有完美记忆, 根据[[#3.3. 库恩定理(Perfect Recall)]], 对每个参与人$i$, 存在等价于$\sigma_i^*$的行为策略$b_i^*$. 于是
$$
u_i(\boldsymbol{\sigma}^*) = u_i(\boldsymbol{b}^*), \quad i\in N
$$
根据[[#3.1. 行为策略转化为混合策略(Path Intersection)]], 对于每一个行为策略$b_i$, 存在等价于$b_i$的混合策略$\sigma_i$.
$$
u_i(\boldsymbol{b}^*) = u_i(\boldsymbol{\sigma}^*) \ge u_i(\sigma_i, \boldsymbol{\sigma}_{-i}^*) = u_i(b_i, \boldsymbol{b}_{-i}^*)
$$
因此, $\boldsymbol{b}^*$是一个行为策略纳什均衡.
#####

___


## 3. 行为策略和混合策略相互转化的条件
### 3.1. 行为策略转化为混合策略(Path Intersection)
令$\Gamma = (N, V, E, v_0, (V_i)_{i\in N\cup \{0\}}, (p_x)_{x\in V_0}, (\mathcal{U}_i)_{i\in N}, O, u)$是一个扩展式博弈, 满足在每个节点上至少有两个行动. 参与人$i$的每个行为策略有一个等价的混合策略, 当且仅当参与人$i$的每个信息集和从根节点出发的每条路径最多相交一次. 
___
##### Note
在每个节点上至少有两个行动的条件是为了保证当一条路径穿过一个信息集两次时, $x_1$和$\widehat{x}_1$可以选择不同的行动来导向同一节点. 否则, 下面的证明中关于必要性的部分将不成立. 
#####
___
##### Proof
首先证明必要性. 我们证明它的逆否命题, 假设存在一个根节点到节点$x$的路径, 与参与人$i$的同一信息集$U_i$至少相交两次, 则存在参与人$i$的一个行为策略, 没有与之等价的混合策略. 

设$x_1$和$\widehat{x}_1$为上面所描述的两个不同的节点. 用$a$表示从$x_1$导向$x$的行动, $b$是$x_1$处不同于$a$的行动. 如果在节点$\widehat{x}_1$处, 参与人$i$选择的行动是$b$, 那么我们令$x_2$表示博弈展开到达的节点. 从根节点到$x_2$的路径穿过节点$x_1$和$\widehat{x}_1$, 从 $x_1$ 导向 $x_2$ 的行动是 $a$, 从 $\widehat{x}_1$ 导向 $x_2$ 的行动是 $b$. 这就意味着参与人$i$的行为策略没有等价的混合策略. 

![image-20230719114111430](./Lecture%204.%20%E5%9D%87%E8%A1%A1(%E6%89%A9%E5%B1%95%E5%BC%8F%E5%8D%9A%E5%BC%88).assets/image-20230719114111430.png)


接下来证明充分性. 对每个节点$x$, 我们用$L_i^x$表示从根节点到$x$(不包括$x$)的路径上的节点的个数. 这条路径上的节点表示为$x_i^1, x_i^2, \cdots, x_i^{L_i^x}$. 如果参与人$i$选择行为策略$b_i$, 则他选择导向$x$的行动的概率为
$$
\rho_i\left(x ; b_i\right):= \begin{cases}\prod\limits_{l=1}^{L_i^x} b_i\left(a_i\left(x_i^l \rightarrow x\right) ; U_i\left(x_i^l\right)\right) & \text { If } L_i^x>0 \\ 1 & \text { If } L_i^x=0\end{cases}
$$
令$S_i^*(x)\subset S_i$表示参与人$i$在每个信息集$U_i(x_i^l)$选择行动$a(U_i(x_i^l)\to x)$的全部纯策略. 如果参与人$i$实行了混合策略$\sigma_i$, 则他选择导向$x$的行动的概率为
$$
\rho_i\left(x ; \sigma_i\right):= \begin{cases} \sum\limits_{s_i\in S_i^*(x)} \sigma_i(s_i),  & \text { If } S_i^*(x)\neq \varnothing \\ 0, & \text { If } S_i^*(x) =  \varnothing\end{cases}
$$

给定参与人$i$的纯策略$s_i$和行为策略$b_i$, 根据$b_i$选择这个纯策略的概率为
$$
\sigma_i(s_i) = \prod\limits_{U_i\in \mathcal{U}_i}^{} b_i(s_i(U_i); U_i) 
$$
因为每条路径只和信息集$U_i$相交至多一次, 所以$\sigma_i = (\sigma_i(s_i))_{s_i\in S_i}$是$S_i$上的一个概率分布. 因而是一个混合策略. 于是, 我们只需要验证$\sigma_i$和$b_i$是等价的. 令$x$是一个节点, 对任意$\boldsymbol{\sigma}_{-i}$, 有
$$
\begin{aligned} 
\rho\left(x ; b_i, \boldsymbol{\sigma}_{-i}\right)&=\rho_i\left(x ; b_i\right) \times \prod_{j \neq i} \rho_j\left(x ; \sigma_j\right) \\ 
    \rho\left(x ; \sigma_i, \boldsymbol{\sigma}_{-i}\right)&=\rho_i\left(x ; \sigma_i\right) \times \prod_{j \neq i} \rho_j\left(x ; \sigma_j\right)
\end{aligned}
$$
将参与人$i$的信息集组合一分为二, $\mathcal{U}_i^1$包含从根节点到$x$的路径穿过的所有信息集; $\mathcal{U}_i^2$包含不穿过的所有信息集. 于是
$$
\begin{aligned}
\rho_i\left(x ; \sigma_i\right) & =\sum_{s_i \in S_i^*(x)} \sigma_i\left(s_i\right) \\
& =\sum_{s_i \in S_i^*(x)} \prod_{U_i \in \mathcal{U}_i} b_i\left(s_i\left(U_i\right) ; U_i\right) \\
& =\sum_{s_i \in S_i^*(x)}\left(\prod_{U_i \in \mathcal{U}_i^1} b_i\left(s_i\left(U_i\right) ; U_i\right) \times \prod_{U_i \in \mathcal{U}_i^2} b_i\left(s_i\left(U_i\right) ; U_i\right)\right) \\ 
& = \sum_{s_i \in S_i^*(x)}\left(\prod_{l=1}^{L_i^x} b_i\left(a_i\left(x_i^l \rightarrow x\right) ; U_i\left(x_i^l\right)\right) \times \prod_{U_i \in \mathcal{U}_i^2} b_i\left(s_i\left(U_i\right) ; U_i\right)\right) \\ 
& = \rho_i\left(x ; b_i\right) \times\left(\sum_{s_i \in S_i^*(x)} \prod_{U_i \in \mathcal{U}_i^2} b_i\left(s_i\left(U_i\right) ; U_i\right)\right)\\ 
& = \rho_i\left(x ; b_i\right) \times\sum_{\left\{\left(a_{U_i}\right)_{U_i \in \mathcal{U}_i^2} \in \operatorname*{\times}\limits_{U_i \in \mathcal{U}_i^2} A\left(U_i\right)\right\}} \prod_{U_i \in \mathcal{U}_i^2} b_i\left(a_{U_i} ; U_i\right) \\
& = \rho_i\left(x ; b_i\right) 
\end{aligned}
$$
因此我们证明了
$$
\rho_i\left(x ; \sigma_i\right) = \rho_i\left(x ; b_i\right) 
$$
这意味着行为策略$b_i$和混合策略$\sigma_i$是等价的.
#####
___


### 3.2. 完美记忆(Perfect Recall)
如果下面的条件得到满足, 那么参与人$i$具有完美记忆:
1. 参与人$i$的每个信息集和从根节点到终节点的每条路径最多相交一次.
2. 对于参与人$i$的每个信息集$U_i$和$U_i$中的每对结点$x, \widehat{x}$, 如果参与人$i$在从根节点到$x$的路径上的决策节点是$x_i^1, x_i^2, \cdots, x_i^{L} =x$, 他在从根节点到$x$的路径上的决策节点是$\widehat{x}_i^1, \widehat{x}_i^2, \cdots, \widehat{x}_i^{\widehat{L}} =\widehat{x}$, 那么对所有的$1\le l\le L$, 有
   $$
   U_i(x_i^l) = U_i(\widehat{x}_i^l), \quad a_i(x_i^{l}\to x) = a_i(\widehat{x}_i^{l}\to \widehat{x})
   $$

如果一个博弈的所有参与人都有完美记忆, 那么这个博弈就叫做具有完美记忆的博弈.

### 3.3. 库恩定理(Perfect Recall)

混合策略转化为行为策略(Perfect Recall)




## 4. 子博弈完美均衡
### 4.1. 子博弈完美均衡
在扩展式博弈$\Gamma$中, 策略向量$\boldsymbol{\sigma}^*$叫做子博弈完美均衡, 当且仅当局限在每个子博弈的策略向量$\boldsymbol{\sigma}^*$是那个子博弈的纳什均衡: 即对每个参与人$i\in N$, 每个策略$\sigma_i$和每个子博弈$\Gamma(x)$. 
$$
u_i(\boldsymbol{\sigma}^*\mid x) \ge u_i(\sigma_i, \boldsymbol{\sigma}^*_{-i}\mid x)
$$

### 4.2. 子博弈的纳什均衡
令$\boldsymbol{\sigma}^*$为扩展式博弈$\Gamma$的纳什均衡, 令$\Gamma(x)$是$\Gamma$的一个子博弈. 如果$\mathbb{P}_{\boldsymbol{\sigma}^*}(x)>0$, 那么局限于子博弈$\Gamma(x)$的策略向量$\boldsymbol{\sigma}^*$是子博弈$\Gamma(x)$的纳什均衡. 
___
##### Proof
令$\Gamma(x)$为$\Gamma$中从节点$x$出发的子博弈, 令$\boldsymbol{\sigma}^*$为满足$\mathbb{P}_{\boldsymbol{\sigma}^*}(x)>0$的$\Gamma$的纳什均衡. 令$\sigma_i^{\prime}$是子博弈$\Gamma(x)$中参与人$i$的策略. 用$\sigma_i$表示参与人$i$与$\boldsymbol{\sigma}^*$完全重叠的策略(除了在子博弈$\Gamma(x)$中). 
$$
\mathbb{P}_{\boldsymbol{\sigma}^*}(x) = \mathbb{P}_{(\sigma_i, \boldsymbol{\sigma}_{-i}^*)}(x)
$$
用$\widehat{u}_i$表示参与人$i$的预期收益, 条件是当参与人执行策略向量$\boldsymbol{\sigma}^*$时, 博弈展开后没有到达子博弈$\Gamma(x)$, 那么
$$
u_i(\boldsymbol{\sigma}^*) = \mathbb{P}_{\boldsymbol{\sigma}^*}(x)u_i(\boldsymbol{\sigma}^* \mid x) + (1-\mathbb{P}_{\boldsymbol{\sigma}^*}(x))\widehat{u}_i
$$
对策略向量$(\sigma_i, \boldsymbol{\sigma}_{-i}^*)$, 有
$$
u_i(\sigma_i, \boldsymbol{\sigma}_{-i}^*) = \mathbb{P}_{\boldsymbol{\sigma}^*}(x)u_i\left((\sigma_i^{\prime}, \boldsymbol{\sigma}_{-i}^*)\mid x\right) + (1 -  \mathbb{P}_{\boldsymbol{\sigma}^*}(x))\widehat{u}_i
$$
因为$\boldsymbol{\sigma}^*$是均衡的
$$
\begin{aligned} 
\mathbb{P}_{\boldsymbol{\sigma}^*}(x) u_i(\boldsymbol{\sigma}^* \mid x) + (1 - \mathbb{P}_{\boldsymbol{\sigma}^*}(x))\widehat{u}_i &=u_i(\boldsymbol{\sigma}^*) \\ 
   &\ge u_i(\sigma_i, \boldsymbol{\sigma}_{-i}^*) \\
   & = \mathbb{P}_{\boldsymbol{\sigma}^*}(x) u_i\left((\sigma_i^{\prime}, \boldsymbol{\sigma}_{-i}^*) \mid x\right) + (1 - \mathbb{P}_{\boldsymbol{\sigma}^*}(x)) \widehat{u}_i
\end{aligned}
$$
于是, 我们有
$$
u_i(\boldsymbol{\sigma}^*\mid x)\ge u_i(\sigma_i, \boldsymbol{\sigma}_{-i}^*\mid x)
$$
因此, 在子博弈$\Gamma(x)$中, 策略向量$\boldsymbol{\sigma}^*$是纳什均衡.
#####
___

## 5. 完美均衡


## 6. 序贯均衡
