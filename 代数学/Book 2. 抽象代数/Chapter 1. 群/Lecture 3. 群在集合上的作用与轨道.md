## 1. 群在集合上的作用
### 1.1. 群作用
设$G$是一个群, $M$是一个集合, 如果有映射
$$
\begin{aligned} 
\rho : G\times M &\to M\\ 
     (g, m) &\mapsto \rho(g, m) 
\end{aligned}
$$
满足对$\forall m\in M$和$\forall g_1, g_2\in G$有
1. $\rho(e, m)= m$, 其中$e$是$G$的单位元
2. $\rho(g_1g_2, m) = \rho(g_1, \rho(g_2, x))$

则称$G$在$M$上有群作用. 这个映射$\rho$称为一个群作用 

在不需要明确地指出映射$\rho$的情况下, 我们常常把$\rho(g,m)$简写为$g(m)$. 按照这个写法, 定义中的条件可以写为
1. $e(x)=x$
2. $g_1(g_2(x)) = g_1g_2(x)$


### 1.2. 群作用的例子
#### 1.2.1. 初等行变换
设$G = \mathrm{GL}_n(\mathbb{F})$, $M = M_n(\mathbb{F})$. 对任意的$C\in G, A\in M$, 定义$\rho_1(C, A) = CA$. 则$\rho_1$是$G$在$M$上的一个群作用. 这个群作用是用可逆矩阵$C$去左乘矩阵$A$. 相当于对$A$做了一系列的初等行变换. 

#### 1.2.2. 初等列变换
设$G = \mathrm{GL}_n(\mathbb{F})$, $M = M_n(\mathbb{F})$. 对任意的$C\in G, A\in M$, 定义$\rho_2(C, A) = AC^{-1}$. 则$\rho_2$是$G$在$M$上的一个群作用. 这个群作用是用可逆矩阵$C^{-1}$去右乘矩阵$A$. 相当于对$A$做了一系列的初等列变换. 

#### 1.2.3. 相似变换
设$G = \mathrm{GL}_n(\mathbb{F})$, $M = M_n(\mathbb{F})$. 对任意的$C\in G, A\in M$, 定义$\rho_3(C, A) = CAC^{-1}$. 则$\rho_3$是$G$在$M$上的一个群作用. 这个群作用是对矩阵做相似变换. 

#### 1.2.4. 合同变换
设$G = \mathrm{GL}_n(\mathbb{F})$, $M = S_n(\mathbb{F})$是数域$\mathbb{F}$上的所有$n$阶对称矩阵组成的集合. 对任意的$C\in G, A\in M$, 定义$\rho(C, A) = CAC^{\prime}$. 则$\rho$是$G$在$M$上的一个群作用. 这个群作用是对矩阵做合同变换

#### 1.2.5. 左乘、右乘与共轭
设$H\le G$, 定义群$H$在$G$上的作用为
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
T(g): M\to M,\quad T(g)(m) = g(m),\quad m\in M
$$
则容易验证
$$
T(g)T(g^{-1}) = T(g^{-1})T(g) = \mathrm{id}_M
$$
因此我们有$T(g)\in S_M$. 再定义映射$T: G\to S_M$为$g\mapsto T(g), \forall g\in G$, 容易验证$T$为$G$到$S_M$的同态.

再证充分性: 设 $T: G \rightarrow S_M$ 为群同态, 定义映射 $\rho: G \times M \rightarrow M$ 为 
$$
\rho(g, m)=g(m)=T(g)(m)
$$ 
则 $\rho$ 就是群 $G$ 在 $M$ 上的一个作用.
#####
___ 


## 2. 等价关系
### 2.1. 等价关系
设$M$是一个集合, $M\times M$的任一子集称为$M$上的一个二元关系. 设$R\subset M\times M$是$M$上的一个二元关系. 对于$a, b\in M$, 若$(a, b)\in R$, 则也记为$aRb$, 或称$a$与$b$具有关系$R$. 若$M$上的一个二元关系满足
1. **反身性**: 即对任意的$a\in M$, 有$aRa$
2. **对称性**: 即对任意的$a, b\in M$, 若$aRb$, 则有$bRa$
3. **传递性**: 即对任意的$a, b, c\in M$, 若$aRb$且$bRc$, 则有$aRc$

则称$R$是$M$上的一个等价关系. 

### 2.2. 等价类
设$R$是$M$上的一个等价关系, $a\in M$, 称集合$\bar{a} = \{b\in M\mid aRb\}$为$a$关于$R$的等价类

### 2.3. 等价类的性质
设$R$是$M$上的一个等价关系, 则有
1. 若$b\in \bar{a}$, 那么$\bar{a} = \bar{b}$
2. $\bar{a}$与$\bar{b}$或相等或不相交
3. 在$M$的每个等价类中取一个元组成$M$的一个子集$I$, 称为$M$的等价类的代表元集, 则$M = \bigcup\limits_{a\in I}^{} \bar{a}$且其中各个$\bar{a}$互不相交. 

### 2.4. 等价类的例子
#### 2.4.1. 群同构
群同构[[Lecture 2. 同构和同态#1.1. 同构的定义|(同构的定义)]]在群与群之间建立起了一个等价关系, 在同构映射下, 对应的元素在格子的运算下具有相同的代数性质. 因此不必加以区分同构的群
#### 2.4.2. 群作用的轨道
设群$G$作用在集合$M$上, 定义$xRy\iff y\in O_x$, 则$R$是$M$上的一个等价关系且$x$的等价类$\bar{x} = O_x$. [[#2.1. 轨道|(轨道的定义)]]

特别地, 左陪集和右陪集都是群作用的轨道, 因此可以作为等价类. 
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
\bar{x} = \{y\in M\mid xRy\} = \{y\in M\mid y\in O_x\} = O_x
$$
#####
___

## 3. 轨道与陪集
### 3.1. 轨道
设群$G$作用在集合$M$上, 对$x\in M$, 称$M$的子集
$$
O_x = \{g(x)\mid g\in G\}
$$
为$x$在$G$作用下的轨道, 或简称过$x$的轨道.

### 3.2. 陪集
设$G$为群, $H \le G$, 则$H$在$G$上可以定义左乘和右乘作用. 

考虑$H$在$G$上的左乘作用, 对于$x\in G$, 这个群作用下过$x$的轨道为
$$
O_x = \{hx\mid h\in H\} = Hx
$$
这称为$H$在$G$中的一个右陪集. 

而$H$在$G$上右乘作用下过$x$的轨道为
$$
\left\{x h^{-1} \mid h \in H\right\}=\{x h \mid h \in H\} = x H,
$$
称为 $H$ 在 $G$ 中的一个左陪集.


### 3.3. 群的陪集分解
设 $I$ 是 $G$ 关于子群 $H$ 的左陪集代表元集, 而 $J$ 是 $G$ 关于子群 $H$ 的右陪集代表元集, 则有
$$
G=\bigcup_{x \in I} x H=\bigcup_{y \in J} H y .
$$

将子群$H$在$G$中左(右)陪集的个数称为子群$H$在$G$中的指数, 记为$[G: H]$

### 3.4. 拉格朗日定理
1. 设 $G$ 为群, $H \leq G$, 则 $|G|=[G: H]|H|$. 
2. 设群$K\le H \le G$, 则$[G:K] = [G:H]\cdot [H:K]$
3. 设$G$为有限群, $H, K$是$G$的子群, 则
   $$
   |H|\cdot |K| = |HK|\cdot |H \cap K|
   $$
   其中$HK = \{hk\mid h\in H, k\in K\}$
4. 设 $G$ 为有限群, $H, K$ 为 $G$ 的子群, 则 
   $$
   [G: H \cap K] \leq[G: H][G: K]
   $$
   等号成立当且仅当 $H K=G$. 特别地, 若 $[G: H]$ 与 $[G: K]$ 互素,则等号一定成立.
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

