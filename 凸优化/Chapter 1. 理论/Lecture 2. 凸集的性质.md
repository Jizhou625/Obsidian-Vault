## 1. 保凸运算
### 1.1. Intersection
如果对任意的$\alpha \in \mathcal{A}$ 都有 $S_\alpha$ 是凸的，则其交集$\bigcap\limits_{\alpha \in \mathcal{A}} S_\alpha$ 也是凸的
___
##### Examples
1. 考虑集合
   $$
   S=\left\{\boldsymbol{x} \in \mathbb{R}^m\mid |p(t)|\leq 1 \text { for }|t| \leq \pi / 3\right\}
   $$
   这里 $p(t)=\sum\limits_{k=1}^m x_k \cos k t$. 集合 $S$ 可以被解释成无限个凸集的交
   $$
   S=\bigcap\limits_{|t| \leq \pi / 3} S_t, \quad S_t=\left\{\boldsymbol{x} \mid-1 \leq(\cos t, \ldots, \cos m t)^{\top} \boldsymbol{x} \leq 1\right\}
   $$
   因此$S$是凸的
2. Positive semidefinite cone $\mathbb{S}^n_+$可以被写成
   $$
   \bigcap_{\boldsymbol{z} \neq \boldsymbol{0}}\left\{X \in \mathbb{S}^n \mid \boldsymbol{z}^{\top} X \boldsymbol{z} \geq 0\right\} .
   $$
   对任意的$\boldsymbol{z}\neq \boldsymbol{0}$, $\boldsymbol{z}^{\top} X \boldsymbol{z}$是$X$的线性方程, 因此
   $$
   \left\{X \in \mathbb{S}^n \mid \boldsymbol{z}^{\top} X \boldsymbol{z} \geq 0\right\}
   $$
   是$\mathbb{S}^n$上的半平面. 因此$\mathbb{S}^n_+$是凸的   

#####
___

### 1.2. Cartesian Product
如果$S_1$和$S_2$都是凸的, 则它们的笛卡尔积
$$
S_1\times S_2 = \{(\boldsymbol{x}_1, \boldsymbol{x}_2)\mid \boldsymbol{x}_1\in S_1, \boldsymbol{x}_2\in S_2\}
$$
也是凸的

### 1.3. Affine Function

假设 $S \subseteq \mathbb{R}^n$ 是一个凸集并且 $f: \mathbb{R}^n\to \mathbb{R}^m$ 是一个仿射函数
$$
f(\boldsymbol{x}) = A\boldsymbol{x}+\boldsymbol{b}
$$
则$S$在$f$下的像
$$
f(S)=\{f(\boldsymbol{x})\mid  \boldsymbol{x}\in S\}
$$
是凸集 

类似的, 如果$f: \mathbb{R}^k \to \mathbb{R}^n$ 是一个仿射函数, 则$S$在$f$下的反象 
$$
f^{-1}(S) = \{\boldsymbol{x}\mid f(\boldsymbol{x})\in S\}
$$
也是凸集
#### 1.3.1. Sum of two sets
如果$S_1$和$S_2$都是凸的, 则它们的和$S_1+S_2 = \{\boldsymbol{x}+\boldsymbol{y}\mid \boldsymbol{x}\in S_1, \boldsymbol{y}\in S_2\}$ 也是凸的. 这是因为笛卡尔积$S_1\times S_2$是凸的, 并且其在仿射函数$f(\boldsymbol{x}_1, \boldsymbol{x}_2) = \boldsymbol{x}_1 + \boldsymbol{x}_2$下的像是$S_1+S_2$

#### 1.3.2. Projection
一个凸集在它某些分量上的投影是凸的, 也就是说, 如果$S\subset \mathbb{R}^m\times \mathbb{R}^n$是凸的, 则
$$
T=\left\{\boldsymbol{x}_1 \in \mathbb{R}^m \mid\left(\boldsymbol{x}_1, \boldsymbol{x}_2\right) \in S \text { for some } \boldsymbol{x}_2 \in \mathbb{R}^n\right\}
$$
也是凸的

#### 1.3.3. Partial sum
如果$S_1$和$S_2$都是凸的且$S_1, S_2\in \mathbb{R}^n\times \mathbb{R}^m$, 则它们的partial sum
$$
S=\left\{\left(x, y_1+y_2\right) \mid\left(x, y_1\right) \in S_1,\left(x, y_2\right) \in S_2\right\}
$$
也是凸的
___
##### Examples
1. 多面体 $\{\boldsymbol{x}\mid A\boldsymbol{x}\preceq \boldsymbol{b}, C\boldsymbol{x}=\boldsymbol{d}\}$ 可以被解释成在仿射函数$f(\boldsymbol{x}) = (\boldsymbol{b} - A\boldsymbol{x}, \boldsymbol{d}-C\boldsymbol{x})$下的笛卡尔积$\mathbb{R}_+^m\times \{\boldsymbol{0}\}$的反象. 
   $$
   \{\boldsymbol{x}\mid A\boldsymbol{x}\preceq \boldsymbol{b}, C\boldsymbol{x}=\boldsymbol{d}\} = \{\boldsymbol{x}\mid f(\boldsymbol{x})\in \mathbb{R}_+^m\times \{\boldsymbol{0}\}\}
   $$
   因此, 多面体 $\{\boldsymbol{x}\mid A\boldsymbol{x}\preceq \boldsymbol{b}, C\boldsymbol{x}=\boldsymbol{d}\}$ 是凸的. 
2. 设 $B, A_i\in \mathbb{S}^m$,  $A(\boldsymbol{x}) = x_1A_1+\cdots+x_nA_n \preceq B$ 被称为关于$\boldsymbol{x}$的线性矩阵不等式(LMI). LMI的解集$\{\boldsymbol{x} \mid A(\boldsymbol{x} ) \preceq B\}$是一个凸集. 事实上, 它是在仿射函数$f(\boldsymbol{x})=B-A(\boldsymbol{x}): \mathbb{R}^n \rightarrow \mathbb{S}^m$下$\mathbb{S}^n_{+}$的反象. 
3. Hyperbolic cone
   $$
   \{\boldsymbol{x}\mid \boldsymbol{x}^{\top} P\boldsymbol{x}\le (\boldsymbol{c}^{\top} \boldsymbol{x})^2, \quad \boldsymbol{c}^{\top} \boldsymbol{x}\ge 0 \}, \quad P\in \mathbb{S}_+^n, \boldsymbol{c}\in \mathbb{R}^n
   $$
   是凸集. 事实上, 它是second-order cone 
   $$
   \{(\boldsymbol{z}, t)\mid \boldsymbol{z}^{\top} \boldsymbol{z}\le t^2, t\ge 0\}$$ 
   在仿射函数 $f(\boldsymbol{x}) = (P^{\frac{1}{2}}\boldsymbol{x}, \boldsymbol{c}^{\top}\boldsymbol{x})$下的反象. 

### 1.4. Perspective Functions
透视函数 $P: \mathbb{R}^n\times \mathbb{R}_{++}\to \mathbb{R}^n$ 定义为 $P(\boldsymbol{z}, t) = \dfrac{\boldsymbol{z}}{t}$. 如果$C\subset \mathrm{dom}P$是一个凸集, 那么其在透视函数$P$作用下的像
$$
P(C) = \{P(\boldsymbol{x})\mid \boldsymbol{x}\in C\}
$$
也是一个凸集. 

透视函数$P$作用下凸集的反象仍然是凸的, 也就是说, 如果$C\subset \mathbb{R}^n$ 是凸的, 则
$$
P^{-1}(C) = \left\{(\boldsymbol{x},t)\in \mathbb{R}^{n+1}\mid \dfrac{\boldsymbol{x}}{t}\in C, t>0\right\}
$$
也是凸的

### 1.5. Linear-fractional Function

线性分式函数是透视函数和仿射函数的组合. 假设 $g: \mathbb{R}^n\to \mathbb{R}^{m+1}$是仿射函数
$$
g(\boldsymbol{x})=\left(\begin{array}{c}
 {A} \\
\boldsymbol{c}^{\top}
\end{array}\right) \boldsymbol{x}+\left(\begin{array}{l}
\boldsymbol{b} \\
d
\end{array}\right),\quad A\in \mathbb{R}^{m\times n}, \boldsymbol{b}\in \mathbb{R}^m, \boldsymbol{c}\in \mathbb{R}^n, d\in \mathbb{R}
$$
函数 $f= P\circ g: \mathbb{R}^n\to \mathbb{R}^m$ 
$$
f(\boldsymbol{x}) = \dfrac{A\boldsymbol{x}+\boldsymbol{b}}{\boldsymbol{c}^{\top}\boldsymbol{x}+d},\quad \mathrm{dom} f = \{\boldsymbol{x}\mid \boldsymbol{c}^{\top}\boldsymbol{x}+d>0\}
$$
被称为linear-fractional函数. 

如果$C$是凸集, 那么其在linear-fractional函数$f$作用下的像$f(C)$也是凸的. 类似地, 如果$C\subset \mathbb{R}^m$是凸的, 那么其反象$f^{-1}(C)$也是凸的. 

## 2. 真锥(Proper Cone)
### 2.1. Proper Cone的定义
锥$K\subset \mathbb{R}^n$被称为proper cone, 如果它满足下列的条件
1. $K$是凸的
2. $K$是闭的
3. $K$是实(solid)的, 也就是说, $K$有非空的内点集
4. $K$是pointed的, 也就是说, $K\cap -K = \{\boldsymbol{0}\}$

### 2.2. Generalized Inequality
我们可以定义在proper cone $K$上的generalized inequality $\preceq_K$, 其偏序关系为
$$
\boldsymbol{x} \preceq_K \boldsymbol{y} \iff \boldsymbol{y}-\boldsymbol{x} \in K
$$
类似地, 我们可以定义严格偏序关系为
$$
\boldsymbol{x} \prec_K \boldsymbol{y} \iff \boldsymbol{y}-\boldsymbol{x} \in K^{\circ}
$$

### 2.3. Generalized Inequality的性质
1. $\preceq_K$在加法下保持: 也就是说, 如果$\boldsymbol{x}\preceq_K \boldsymbol{y}$并且$\boldsymbol{u}\preceq_K \boldsymbol{v}$, 那么$\boldsymbol{x}+\boldsymbol{u}\preceq_K \boldsymbol{y}+\boldsymbol{v}$
2. $\preceq_K$具有传递性: 如果$\boldsymbol{x}\preceq_K \boldsymbol{y}$并且$\boldsymbol{y}\preceq_K \boldsymbol{z}$, 那么$\boldsymbol{x}\preceq_K \boldsymbol{z}$
3. $\preceq_K$在非负标量乘法下保持: 如果$\boldsymbol{x}\preceq_K \boldsymbol{y}$并且$\alpha\ge 0$, 那么$\alpha\boldsymbol{x}\preceq_K \alpha\boldsymbol{y}$
4. $\preceq_K$具有反身性: $\boldsymbol{x}\preceq_K \boldsymbol{x}$
5. $\preceq_K$具有反对称性: 如果$\boldsymbol{x}\preceq_K \boldsymbol{y}$并且$\boldsymbol{y}\preceq_K \boldsymbol{x}$, 那么$\boldsymbol{x}=\boldsymbol{y}$
6. $\preceq_K$在极限下保持: 如果$\boldsymbol{x}_i\preceq_K \boldsymbol{y}_i$对于所有的$k$成立, 并且$\boldsymbol{x}_i\to \boldsymbol{x}$, $\boldsymbol{y}_i\to \boldsymbol{y}$, 那么$\boldsymbol{x}\preceq_K \boldsymbol{y}$


## 3. 分离和支持超平面(Separating and Supporting Hyperplanes)
### 3.1. 分离超平面定理(Separating Hyperplanes Theorem)

假设 $C$ 和 $D$ 是两个不相交的凸集, 也就是说, $C \cap D=\varnothing$. 则存在一个 $\boldsymbol{a} \neq \boldsymbol{0}$ 和 $b$ 使得 $\boldsymbol{a}^{\top}\boldsymbol{x} \leq b$ 对任意的 $\boldsymbol{x} \in C$成立, $\boldsymbol{a}^{\top} \boldsymbol{x} \geq b$ 对任意的 $\boldsymbol{x} \in D$成立. 换句话说,  仿射函数$\boldsymbol{a}^{\top} \boldsymbol{x}-b$ 在 $C$ 上非正, 在 $D$ 上非负. 超平面 $\left\{\boldsymbol{x} \mid \boldsymbol{a}^{\top} \boldsymbol{x}=b\right\}$ 被称为凸集 $C$ 和 $D$ 的分离超平面. 

![image-20230620010802530](Lecture%202.%20凸集的性质.assets/image-20230620010802530.png)


### 3.2. 严格分离(Strict Separation)
如果我们构造的分离超平面满足 $\boldsymbol{a}^{\top} \boldsymbol{x}<b$ 对任意的 $\boldsymbol{x} \in C$ 成立, $\boldsymbol{a}^{\top} \boldsymbol{x}>b$ 对任意的 $\boldsymbol{x} \in D$成立, 则凸集 $C$ 和 $D$ 被称为严格分离. 

不交的凸集不一定是被一个超平面严格分离, 即使这两个凸集都是闭的. 例如, 
$$
C = \{(x, y)\mid xy\ge 1, x, y>0\},\quad D = \{(x, y)\mid x\le 0\}
$$
是一个反例.
___
##### 点集和闭凸集的严格分离
设$C$是一个闭凸集, 而$\boldsymbol{x}_0\notin C$, 那么存在将$\boldsymbol{x}_0$和$C$严格分离的超平面. 

为了说明这一点, 需要注意, 对于足够小的$\varepsilon>0$, 存在两个不相交的集合$C$和$\mathcal{B}(\boldsymbol{x}_0, \varepsilon)$. 根据超平面分离定理, 存在$\boldsymbol{a}\neq \boldsymbol{0}$和$b$, 使得对于任意的$\boldsymbol{x}\in C$有$\boldsymbol{a}^{\top}\boldsymbol{x}\le b$. 对于任意的$\boldsymbol{x}\in \mathcal{B}(\boldsymbol{x}_0, \varepsilon)$有$\boldsymbol{a}^{\top}\boldsymbol{x}\ge b$. 利用$\mathcal{B}(\boldsymbol{x}_0, \varepsilon) = \{\boldsymbol{x}_0 + \boldsymbol{u}\mid \|\boldsymbol{u}\|_2\le \varepsilon\}$, 我们可以将上述的条件写成
$$
\boldsymbol{a}^{\top} (\boldsymbol{x}_0 + \boldsymbol{u}) \ge b, \quad \forall \|\boldsymbol{u}\|_2 \le \varepsilon
$$
显然$\boldsymbol{u} = - \varepsilon \dfrac{\boldsymbol{a}}{\|\boldsymbol{a}\|_2}$极小化上式的左端. 带入可得
$$
\boldsymbol{a}^{\top}\boldsymbol{x}_0 - \varepsilon \|\boldsymbol{a}\|_2 \ge b
$$
所以仿射函数
$$
f(\boldsymbol{x}) = \boldsymbol{a}^{\top}\boldsymbol{x} - b - \dfrac{ \varepsilon \|\boldsymbol{a}\|_2}{2}
$$
在$C$上是负的, 而在$\boldsymbol{x}_0$点是正的. 
#####
___


### 3.3. 逆分离超平面定理(Converse Separating Hyperplanes Theorem)
任意的两个凸集 $C$ 和 $D$, 如果其中至少一个是开集, 则它们不相交当且仅当存在一个分离超平面. 

**注意**: 至少一个是开集的条件是必要的. 否则, 一个简单的反例是$C = D = \{0\}\subset \mathbb{R}$, 它们被超平面$x = 0$分离. 
___
##### 严格线性不等式择一定理
我们导出严格线性不等式
$$
A\boldsymbol{x} \prec \boldsymbol{b}
$$
有解的充分必要条件. 改不等式不可行的充分必要条件是凸集
$$
C = \{\boldsymbol{b} - A\boldsymbol{x}\mid \boldsymbol{x}\in \mathbb{R}^n\}, \quad D = \{\boldsymbol{y}\in \mathbb{R}^m\mid \boldsymbol{y}\succ \boldsymbol{0}\}
$$
不相交. 显然集合$D$是一个开集, 而$C$是一个凸集. 根据逆分离超平面定理, $C$和$D$不相交的充分必要条件是存在分离超平面, 即存在非零的$\boldsymbol{\lambda}\in \mathbb{R}^m$和$\mu\in \mathbb{R}$使得$C$中$\boldsymbol{\lambda}^{\top}\boldsymbol{y}\le \mu$, 并且$D$中$\boldsymbol{\lambda}^{\top}\boldsymbol{y}\ge \mu$. 将这两个不等式简化, 可以得到
$$
A^{\top} \boldsymbol{\lambda} = 0, \quad \boldsymbol{\lambda}^{\top}\boldsymbol{b} - \mu \le 0, \quad \mu\le 0, \boldsymbol{\lambda}\succ \boldsymbol{0}
$$
因此, 严格不等式组无解的充要条件是存在$\boldsymbol{\lambda}\in \mathbb{R}^m$使得
$$
\boldsymbol{\lambda} \neq 0, \quad \boldsymbol{\lambda} \succeq \boldsymbol{0}, \quad A^{\top}\boldsymbol{\lambda} = 0, \quad \boldsymbol{\lambda}^{\top}\boldsymbol{b} \le 0
$$
#####
___


## 4. 支撑超平面(Supporting Hyperplanes)
### 4.1. 支撑超平面的定义
假设 $C \subseteq \mathbb{R}^n$ 并且 $\boldsymbol{x}_0$ 是 $C$ 的边界点集 $\partial C$ 上的一点. 如果 $\boldsymbol{a} \neq \boldsymbol{0}$ 满足 $\boldsymbol{a}^{\top}  \boldsymbol{x} \leq \boldsymbol{a}^{\top}  \boldsymbol{x}_0$ 对任意的 $\boldsymbol{x} \in C$成立, 则超平面 $\left\{\boldsymbol{x} \mid \boldsymbol{a}^{\top}  \boldsymbol{x}=\boldsymbol{a}^{\top}  \boldsymbol{x}_0\right\}$ 被称为 $C$ 在 $\boldsymbol{x}_0$处的支撑超平面. 

也可以说, 点$\boldsymbol{x}_0$ 和集合 $C$ 被超平面 $\left\{\boldsymbol{x} \mid \boldsymbol{a}^{\top}  \boldsymbol{x}=\boldsymbol{a}^{\top}  \boldsymbol{x}_0\right\}$ 分离.

![image-20230620132425988](Lecture%202.%20凸集的性质.assets/image-20230620132425988.png)

### 4.2. 支撑超平面定理(Supporting Hyperplanes Theorem)
对任意非空的凸集 $C$ 和任意的 $\boldsymbol{x}_0\in \partial C$, 存在 $C$ 在 $\boldsymbol{x}_0$ 处的支撑超平面. 


### 4.3. 逆支撑超平面定理(Converse Supporting Hyperplanes Theorem)
假设集合$C$是闭集, 并且有非空的内点集, 则$C$在每一个边界点处都有支撑超平面当且仅当它是凸的. 