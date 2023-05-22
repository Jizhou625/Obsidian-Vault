## 1. 群在集合上的作用
### 1.1. 群作用
设$G$是一个群, $M$是一个集合, 如果有映射
$$
\begin{aligned} 
\rho : G\times M &\to M\\ 
     (g, m) &\mapsto \rho(g, m) =gm
\end{aligned}
$$
满足对$\forall m\in M$和$\forall g_1, g_2\in G$有
1. $em = m$, 其中$e$是$G$的单位元
2. $g_1(g_2m) = (g_1g_2)m$

则称$G$在$M$上有群作用. 这个映射$\rho$称为一个群作用 (这里$gm$是$\rho(g,m)$的简写, 并不代表群$G$上定义的乘法)

### 1.2. 群作用的例子
1. **初等行变换**: 设$G = \mathrm{GL}_n(\mathbb{F})$, $M = M_n(\mathbb{F})$. 对任意的$C\in G, A\in M$, 定义$\rho_1(C, A) = CA$. 则$\rho_1$是$G$在$M$上的一个群作用. 这个群作用是用可逆矩阵$C$去左乘矩阵$A$. 相当于对$A$做了一系列的初等行变换. 
2. **初等列变换**: 设$G = \mathrm{GL}_n(\mathbb{F})$, $M = M_n(\mathbb{F})$. 对任意的$C\in G, A\in M$, 定义$\rho_2(C, A) = AC^{-1}$. 则$\rho_2$是$G$在$M$上的一个群作用. 这个群作用是用可逆矩阵$C^{-1}$去右乘矩阵$A$. 相当于对$A$做了一系列的初等列变换. 
3. **相似变换**: 设$G = \mathrm{GL}_n(\mathbb{F})$, $M = M_n(\mathbb{F})$. 对任意的$C\in G, A\in M$, 定义$\rho_3(C, A) = CAC^{-1}$. 则$\rho_3$是$G$在$M$上的一个群作用. 这个群作用是对矩阵做相似变换. 
4. **合同变换**: 设$G = \mathrm{GL}_n(\mathbb{F})$, $M = S_n(\mathbb{F})$是数域$\mathbb{F}$上的所有$n$阶对称矩阵组成的集合. 对任意的$C\in G, A\in M$, 定义$\rho(C, A) = CAC^{\prime}$. 则$\rho$是$G$在$M$上的一个群作用. 这个群作用是对矩阵做合同变换
5. **共轭作用**: 设$H<G$, 定义群$H$在$G$上的作用为
   $$
   \rho_1(h, g) = hg,\quad  h\in H, g\in G
   $$
   称$\rho_1$为$G$的子群$H$在群$G$上的左乘作用. 类似地, 我们可以定义右乘作用为$\rho_2(h, g) = gh^{-1}$. 同样地, 可以定义$H$在$G$上的共轭作用为$\rho_3(h, g) = hgh^{-1}$

### 1.3. 群作用和群同态
群$G$在集合$M$上有群作用的充分必要条件是$G$到$M$的全变换群$S_M$存在群同态. 
___
##### Proof
先证必要性: 设$\rho: G\times M\to M$是一个群作用. 对于固定的$g\in G$, 定义
$$
T(g): M\to M,\quad T(g)(m) = gm,\quad m\in M
$$
则容易验证
$$
T(g)T(g^{-1}) = T(g^{-1})T(g) = \mathrm{id}_M
$$
因此我们有$T(g)\in S_M$. 再定义映射$T: G\to S_M$为$g\mapsto T(g), \forall g\in G$, 容易验证$T$为$G$到$S_M$的同态.

再证充分性: 设 $T: G \rightarrow S_M$ 为群同态, 定义映射 $\rho: G \times M \rightarrow M$ 为 
$$
\rho(g, m)=g m=T(g)(m)
$$ 
则 $\rho$ 就是群 $G$ 在 $M$ 上的一个作用.
#####
___ 

### 1.4. 等价关系
设$M$是一个集合, $M\times M$的任一子集称为$M$上的一个二元关系. 设$R\subset M\times M$是$M$上的一个二元关系. 对于$a, b\in M$, 若$(a, b)\in R$, 则也记为$aRb$, 或称$a$与$b$具有关系$R$. 若$M$上的一个二元关系满足
1. **反身性**: 即对任意的$a\in M$, 有$aRa$
2. **对称性**: 即对任意的$a, b\in M$, 若$aRb$, 则有$bRa$
3. **传递性**: 即对任意的$a, b, c\in M$, 若$aRb$且$bRc$, 则有$aRc$

则称$R$是$M$上的一个等价关系. 

设$R$是$M$上的一个等价关系, $a\in M$, 称集合$\bar{a} = \{b\in M\mid aRb\}$为$a$关于$R$的等价类

### 1.5. 等价类的性质
设$R$是$M$上的一个等价关系, 则有
1. 若$b\in \bar{a}$, 那么$\bar{a} = \bar{b}$
2. $\bar{a}$与$\bar{b}$或相等或不相交
3. 在$M$的每个等价类中取一个元组成$M$的一个子集$I$, 称为$M$的等价类的代表元集, 则$M = \bigcup\limits_{a\in I}^{} \bar{a}$且其中各个$\bar{a}$互不相交. 


## 2. 群作用的轨道
### 2.1. 轨道
设群$G$作用在集合$M$上, 对$x\in M$, 称$M$的子集
$$
O_x = \{gx\mid g\in G\}
$$
为$x$在$G$作用下的轨道, 或简称过$x$的轨道.

### 2.2. 轨道作为等价类
设群$G$作用在集合$M$上, 对于$x, y\in M$, 定义$xRy\iff y\in O_x$, 则$R$是$M$上的一个等价关系且$x$的等价类$\bar{x} = O_x$
___
##### Proof:
1. **反身性**: 对任意 $x \in M$, 由于 $x=e x$, 所以 $x \in O_x$, 即 $x R x$. 
2. **对称性**: 对于 $x, y \in M$, 若 $x R y$, 即 $y \in O_x$, 则存在 $g \in G$ 使得 $y=g x$, 故 
   $$
   g^{-1}y=g^{-1}(g x)=\left(g^{-1} g\right) x=e x=x
   $$
   所以 $x \in O_y$, 即 $y R x$. 
3. **传递性**: 对 于 $x, y, z \in M$, 若 $x R y$ 且 $y R z$, 即 $y \in O_x$ 且 $z \in O_y$, 所以存在 $g, h \in G$ 使得 $y=g x$ 且 $z=h y$, 故 $z=h(g x)=(h g) x$, 从而 $z \in O_x$, 即 $x R z$. 

这便证出 $R$ 满足反身性, 对称性和传递性, 所以 $R$ 为等价关系. 由定义知道对于$x\in M$, 有
$$
\bar{x} = \{y\in M\mid xRy\} = \{y\in M\mid y\in G_x\} = G_x
$$
#####
___


## 3. 陪集
### 3.1. 陪集的定义
设$G$为群, $H< G$, 则$H$在$G$上左乘和右乘作用. 考虑$H$在$G$上的左乘作用, 对于$x\in G$, 这个群作用下过$x$的轨道为
$$
O_x = \{hx\mid h\in H\} = Hx
$$
这称为$H$在$G$中的一个右陪集. 而$H$在$G$上右乘作用下过$x$的轨道为
$$
\left\{x h^{-1} \mid h \in H\right\}=\{x h \mid h \in H\}:=x H,
$$
称为 $H$ 在 $G$ 中的一个左陪集.


### 3.2. 群的陪集分解
设 $I$ 是 $G$ 关于子群 $H$ 的左陪集代表元集, 而 $J$ 是 $G$ 关于子群 $H$ 的右陪集代表元集, 则有
$$
G=\bigcup_{x \in I} x H=\bigcup_{y \in J} H y .
$$

### 3.3. 子群的指数
将子群$H$在$G$中左(右)陪集的个数称为子群$H$在$G$中的指数, 记为$[G: H]$

### 3.4. 拉格朗日定理
1. 设 $G$ 为群, $H \leq G$, 则 $|G|=[G: H]|H|$. 特别地, 若 $G$ 为有限群, $H \leq G$, 则 $|H|$ 整除 $|G|$.
2. 设群$K<H<G$, 则$[G:K] = [G:H]\cdot [H:K]$
3. 设$G$为有限群, $H, K$是$G$的子群, 则
   $$
   |H|\cdot |K| = |HK|\cdot |H \cap K|
   $$
   其中$HK = \{hk\mid h\in H, k\in K\}$
4. 设 $G$ 为有限群, $H, K$ 为 $G$ 的子群, 则 
   $$
   [G: H \cap K] \leq[G: H][G: K]
   $$
   且等号成立当且仅当 $H K=G$. 特别地, 若 $[G: H]$ 与 $[G: K]$ 互素,则等号一定成立.
___
##### Proof:
1. 定理1是定理2的特例, 因此我们只要证明定理2. 设 $G$ 关于 $H$ 以及 $H$ 关于 $K$ 的左陪集分解分别为
   $$
   G=\bigcup_{x \in I} x H, \quad H=\bigcup_{y \in J} y K 
   $$
   则 $G=\bigcup\limits_{(x, y) \in I \times J} x y K$. 进一步地, 对于 $(x, y),\left(x^{\prime}, y^{\prime}\right) \in I \times J$, 若 $x y K=x^{\prime} y^{\prime} K$, 则 $x H \cap x^{\prime} H \neq \varnothing$, 所以 $x=x^{\prime}$, 这样 $y K=y^{\prime} K$, 故 $y=y^{\prime}$. 这便证出上述为不交并, 所以 $\{x y \mid(x, y) \in I \times J\}$ 是 $G$ 关 于子群 $K$ 的左陪集代表元集, 所以 
   $$
   [G: K]=[G: H] \cdot[H: K]
   $$

2. 再证明定理3, 设$H\cap K = L$. 设$H$关于$L$的左陪集代表元集为$I$, 而$K$关于$L$的右陪集代表元集为$J$, 则
   $$
   HK = \bigcup_{x\in I} xL \cdot \bigcup_{y\in J} Ly = \bigcup_{(x, y)\in I\times J} xLy
   $$
   进一步地, 若对 $x, x^{\prime} \in I$ 和 $y, y^{\prime} \in J$ 有 $x L y \cap x^{\prime} L y^{\prime} \neq \varnothing$, 则存在 $a, b \in L$, 使得$x a y=x^{\prime} b y^{\prime}$, 即 $\left(x^{\prime}\right)^{-1} x a=b y^{\prime} y^{-1}$. 上式左边在 $H$ 中而右边在 $K$ 中，所以 
   $$
   \left(x^{\prime}\right)^{-1} x, y^{\prime} y^{-1} \in L
   $$ 
   故 $x=x^{\prime}$ 且 $y=y^{\prime}$. 显然对任意 $x \in I, y \in J$ 有 $|x L y|=|L|$. 从而 
   $$
   |H K|=|I||J||L| = \dfrac{|H|}{|L|}\dfrac{|K|}{|L|}|L| = \dfrac{|H|\cdot |K|}{|H\cap K|}
   $$
3. 最后证明定理4. 不等式
   $$
   [G: H \cap K] \leq[G: H][G: K]
   $$
   等价于
   $$
   |H\cap K| \cdot |G| \ge |H|\cdot |K|
   $$
   由于$|HK|\le |G|$, 所以由定理3可以得到该不等式成立. 特别地, 由于$[G:H]$和$[G:K]$都是$[G: H\cap K]$的因子, 如果它们互素, 则等号成立. 
#####
___

## 4. 稳定化子
### 4.1. 稳定化子的定义
设群$G$作用在集合$M$上, 对于$x\in M$, 定义
$$
G_x = \{g\in G\mid gx = x\}
$$
称它是群$G$作用下$x$的稳定化子, 容易验证$G_x$是$G$的子群. 

### 4.2. 轨道和稳定化子
设$G$为有限群, $G$作用在集合$M$上, 则过$x$的轨道$O_x$的长度等于$G_x$在$G$中的指数, 即
$$
|O_x| = [G: G_x] = \dfrac{|G|}{|G_x|}
$$
此外, 同一轨道上的两个元素的稳定化子是共轭的. 也就是说, 若$y\in O_x$, 则存在$g\in G$, 使得$G_y = gG_xg^{-1}$.
___
##### Proof
定义
$$
\phi: O_x\to (G/G_x)_l, \quad \phi(gx) = gG_x
$$
容易验证这是一个一一对应, 于是$|O_x|=[G:G_x]$

若$y\in O_x$, 则存在$g\in G$, 使得$y=gx$. 任取$h\in G_x$, 则有
$$
(ghg^{-1})y = ghx = gx = y
$$
也就是说, $(ghg^{-1})\in G_y$, 这意味着$gG_xg^{-1}\subset G_y$. 同理, 可以得到$gG_xg^{-1}\supset G_y$. 这就证明了$gG_xg^{-1} =  G_y$
#####
___

### 4.3. Burnside引理
设$G$作用在集合$M$上, 对于$g\in G$, 用$\psi(g) = \{x\in M\mid gx=x\}$表示被$g$固定的$M$中元素的集合, 则$G$作用的轨道个数是
$$
\dfrac{1}{|G|}\sum_{g\in G}|\psi(g)|
$$
___
##### Proof
计算有序对$(g,x)$的个数, 其中$g\in G, x\in M$并且$gx=x$. 一方面, 这个数为$\sum\limits_{g\in G}^{} |\psi(g)|$. 另一方面, 对于$x\in M$, 有$|G_x|$个$g\in G$使得$gx=x$, 于是这个数为$\sum\limits_{x\in M}^{} |G_x|$. 由于$|O_x|= \dfrac{|G|}{|G_x|}$, 所以
$$
\sum_{g \in G}|\psi(g)|=\sum_{x \in M}\left|G_x\right|=|G| \sum_{x \in M} \frac{1}{\left|O_x\right|}
$$
又因为$G$的轨道划分了$M$并且$\sum\limits_{y \in O_x} \dfrac{1}{\left|O_y\right|}=1$. 所以$\sum\limits_{x\in M}^{} \dfrac{1}{|O_x|}$为轨道的个数. 
#####
___

## 5. 类方程
### 5.1. 共轭类与共轭子群
**共轭类**: 设 $G$ 为有限群, 考虑 $G$ 在自身上的共轭作用, 此作用的轨道称为 $G$ 的共轭类, 含元素 $x \in G$ 的共轭类记为 $C_x$, 即
$$
C_x=\left\{g x g^{-1} \mid g \in G\right\}
$$
设 $G$ 的全部互不相同的共轭类为 $C_{x_1}, C_{x_2}, \cdots, C_{x_n}$, 则 $G=\bigcup\limits_{i=1}^n C_{x_i}$.

**共轭子群**: 设$H<G$, 则对任意$g\in G$, $gHg^{-1}$也是$G$的一个子群, 称为$H$的一个共轭子群. 用$M_H= \{gHg^{-1}\mid g\in G\}$表示所有共轭子群的集合. 

### 5.2. 中心化子
对于$x\in G$, $x$在$G$的共轭作用下的稳定化子称为$x$在$G$中的中心化子, 记为$C_G(x)$, 即
$$
C_G(x) = \{g\in G\mid gxg^{-1}=x\} = \{g\in G\mid gx=xg\}
$$
设
$$
Z(G) = \bigcap\limits_{x\in G}^{} C_G(x) = \{g\in G\mid gx=xg,\ \forall x\in G\}
$$ 
称$Z(G)$为群$G$的中心. $Z(G)$是与$G$中所有元素都可交换的$G$中元素组成的集合, $Z(G)$是$G$的子群. 


### 5.3. 类方程
$G$中含有$x$的共轭类中的元素个数, 即类长等于$C_G(x)$在$G$中的指数, 也就是说
$$
|C_x| = [G: C_G(x)]
$$
设$G$中互不相同的共轭类为$C_{x_1}, C_{x_2}, \cdots, C_{x_n}$, 则
$$
|G| = \sum_{i=1}^n |C_{x_i}| = \sum_{i=1}^n [G: C_G(x_i)]
$$
这称为$G$的类方程. 由于$Z(G)$中的每个元素恰含一个元素的共轭类. 因此类方程可以写成
$$
|G|=|Z(G)|+\sum_{i=1}^m\left[G: C_G\left(y_i\right)\right] ,\quad y_i \notin Z(G)
$$

### 5.4. 正规化子
对于$H\in M_H$, $H$的稳定化子为
$$
N_G(H) = \{g\in G\mid gHg^{-1} = H\}
$$
称$N_G(H)$为$H$的正规化子. 同样地, 可以得到$H$的共轭子群的个数为$[G: N_G(H)]$

## 6. 正规子群
### 6.1. 正规子群的定义
设$H$为群$G$的子群, 如果对任意的$g\in G$, 都有$gH=Hg$. 那么称$H$为$G$的正规子群, 记为$H\triangleleft G$. 

这也等价对与任意的$g\in G$, 有
$$
gHg^{-1} = H
$$
或者等价于, 对任意的$g\in G$, $h\in H$, 都有
$$
ghg^{-1} \in H
$$

### 6.2. 同态核是正规子群
设$G\to G^{\prime}$为群同态, 则$\ker \sigma \triangleleft G$
___
##### Proof
对任意$g\in G$, $h\in \ker \sigma$, 由于
$$
\sigma(ghg^{-1}) = \sigma(g)\sigma(h)\sigma(g^{-1}) = \sigma(g)e^{\prime}\left(\sigma(g)\right)^{-1} = e^{\prime}
$$
所以$ghg^{-1} \in \ker \sigma$. 因此$\ker \sigma \triangleleft G$
#####
___


### 6.3. 商群
设$H\triangleleft G$, 在集合$G/H$上定义运算如下
$$
(g_1H)(g_2H) = (g_1g_2)H
$$
容易验证$G/H$在上面定义的运算下构成一个群, 其中单位元为$eH = H$, 元素$gH$的逆元为$g^{-1}H$. 称$G/H$为群$G$关于正规子群$H$的商群.