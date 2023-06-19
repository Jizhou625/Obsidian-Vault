## 1. 保凸运算
### 1.1. Intersection
如果对任意的$\alpha \in \mathcal{A}$ 都有 $S_\alpha$ 是凸的，则交集$\bigcap\limits_{\alpha \in \mathcal{A}} S_\alpha$ 也是凸的
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
2. 一个闭凸集$S$ 是所有包含它的半空间的交集, 也就是说
   $$
   S=\bigcap\{\mathcal{H} \mid \mathcal{H} \text { is halfspace, } S \subseteq \mathcal{H}\}
   $$

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
也是凸的 

类似的, 如果$f: \mathbb{R}^k \to \mathbb{R}^n$ 是一个仿射函数, 则$S$在$f$下的反象 
$$
f^{-1}(S) = \{\boldsymbol{x}\mid f(\boldsymbol{x})\in S\}
$$
也是凸的
#### 1.3.1. Sum of two sets
如果$S_1$和$S_2$都是凸的, 则它们的和$S_1+S_2 = \{\boldsymbol{x}+\boldsymbol{y}\mid \boldsymbol{x}\in S_1, \boldsymbol{y}\in S_2\}$ 也是凸的. 这是因为$S_1\times S_2$是凸的, 并且其在$f(\boldsymbol{x}_1, \boldsymbol{x}_2) = \boldsymbol{x}_1 + \boldsymbol{x}_2$下的像是$S_1+S_2$

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
透视函数$P$下凸集的反象仍然是凸的, 也就是说, 如果$C\subset \mathbb{R}^n$ 是凸的, 则
$$
P^{-1}(C) = \left\{(\boldsymbol{x},t)\in \mathbb{R}^{n+1}\mid \dfrac{\boldsymbol{x}}{t}\in C, t>0\right\}
$$
也是凸的

### 1.5. Linear-fractional Function

线性分式函数是透视函数和仿射函数的组合. 假设 $g: \mathbb{R}^n\to \mathbb{R}^{m+1}$是仿射函数, 也就是说 
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
被称为linear-fractional函数. 如果$C$是凸集, 那么其在linear-fractional函数$f$作用下的像$f(C)$也是凸的. 类似地, 如果$C\subset \mathbb{R}^m$是凸的, 则其反象$f^{-1}(C)$也是凸的. 

## 2. Proper Cone
### 2.1. Proper Cone的定义
锥$K\subset \mathbb{R}^n$被称为proper cone, 如果它满足下列的条件
1. $K$是凸的
2. $K$是闭的
3. $K$是solid的, 也就是说, $K$有非空的interior
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
### 5.1. 分离超平面定理(Separating Hyperplanes Theorem)
假设 $C$ 和 $D$ 是两个不相交的凸集, 也就是说, $C \cap D=\varnothing$. 则存在一个 $\boldsymbol{a} \neq \boldsymbol{0}$ 和 $b$ 使得 $\boldsymbol{a}^{\top}\boldsymbol{x} \leq b$ 对任意的 $\boldsymbol{x} \in C$成立, $\boldsymbol{a}^{\top} \boldsymbol{x} \geq b$ 对任意的 $\boldsymbol{x} \in D$成立. 换句话说,  仿射函数$\boldsymbol{a}^{\top} \boldsymbol{x}-b$ 在 $C$ 上非正, 在 $D$ 上非负. 超平面 $\left\{\boldsymbol{x} \mid \boldsymbol{a}^{\top} \boldsymbol{x}=b\right\}$ 被称为凸集 $C$ 和 $D$ 的分离超平面. 
___

**Example:**
Suppose $C$ is convex and $D$ is affine, i.e., $D=\left\{F\boldsymbol{ u}+\boldsymbol{g} \mid \boldsymbol{u} \in \mathbb{R}^m\right\}$, where ${F} \in \mathbb{R}^{n \times m}$. Suppose $C$ and $D$ are disjoint, so by the separating hyperplane theorem there are $\boldsymbol{a} \neq 0$ and $b$ such that $\boldsymbol{a}^{\top} \boldsymbol{x} \leq b$ for all $\boldsymbol{x} \in C$ and $\boldsymbol{a}^{\top} \boldsymbol{x} \geq$ $b$ for all $\mathrm{x} \in D$.

Now $\boldsymbol{a}^{\top} \boldsymbol{x} \geq b$ for all $\boldsymbol{x} \in D$ means $\boldsymbol{a}^{\top} F\boldsymbol{u} \geq b-\boldsymbol{a}^{\top} \boldsymbol{g}$ for all $\boldsymbol{u} \in \mathbb{R}^m$. But a linear function is bounded below on $\mathbb{R}^m$ only when it is zero, so we conclude $\boldsymbol{a}^{\top} F=\boldsymbol{0}$ (and hence, $b \leq \boldsymbol{a}^{\top}  \boldsymbol{g}$ )

Thus we conclude that there exists $\boldsymbol{a} \neq 0$ such that $F^{\top} \boldsymbol{a}=\boldsymbol{0}$ and $\boldsymbol{a}^{\top} \boldsymbol{x} \leq \boldsymbol{a}^{\top} \boldsymbol{g}$ for all $\boldsymbol{x} \in C$.

![image-20230319192022011](Chapter%201.%20凸集/Lecture%201.%20凸集.assets/image-20230319192022011.png)

### 5.2. Strict Separation:
If the separating hyperplane satisfies the stronger condition that $\boldsymbol{a}^{\top} \boldsymbol{x}<b$ for all $\boldsymbol{x} \in C$ and $\boldsymbol{a}^{\top} \boldsymbol{x}>b$ for all $\boldsymbol{x} \in D$, then the sets $C$ and $D$ are called strictly separated. Disjoint convex sets need not to be strictly separated by a hyperplane, even when the sets are closed. 

There are some examples of strict separation. 
1. a point and a closed convex set. 
2. a closed convex set is the intersection of all halfspaces that contain it. 

### 5.3. Converse Separating Hyperplanes Theorem
Any two convex sets $C$ and $D$, at least one of which is open, are disjoint if and only if there exists a separating hyperplane.

### 5.4. Theorem of the Alternative (Fakas' Lemma)
For $A\in\mathbb{R}^{m\times n}$ and $\boldsymbol{b}\in \mathbb{R}^m$, the following are strong alternatives:
1. $\exists \boldsymbol{x}\in \mathbb{R}^n_+$ such that $A\boldsymbol{x}=\boldsymbol{b}$
2. $\exists \boldsymbol{y} \in \mathbb{R}^m$ such that $A^{\top}\boldsymbol{y}\succeq 0$ and $\boldsymbol{b}^{\top}\boldsymbol{y}<0$
___
##### Proof: 
First, we prove that $1\Longrightarrow \neg 2$: For $\boldsymbol{x}\in \mathbb{R}^n_+$ with $A\boldsymbol{x}=\boldsymbol{b}$ and $\boldsymbol{y}\in \mathbb{R}^m$ with $A^{\top}\boldsymbol{y}\succeq 0$ we have $\boldsymbol{b}^{\top}\boldsymbol{y} =\boldsymbol{x}^{\top} A^{\top}\boldsymbol{y}\ge 0$. 

Then, we prove that $\neg 1\Longrightarrow 2$: Consider the closed convex cone $C = \mathrm{cone}(A)$. Here, $\mathrm{cone}(A)$ is the cone of the column space of $A$. $\neg 1$ means that $\boldsymbol{b}$ is not in  $\mathrm{cone}(A)$. By the separating hyperplane theorem we can get that there exist $\boldsymbol{y}\in \mathbb{R}^m$ and $\mu$ such that $\langle \boldsymbol{y}, \boldsymbol{z}\rangle \ge \mu > \langle \boldsymbol{y}, \boldsymbol{b}\rangle$ for all $\boldsymbol{z} \in C$. Then we can get that $\langle A^{\top}\boldsymbol{y}, \boldsymbol{x} \rangle \ge \mu, \forall \boldsymbol{x}\ge 0$, which implies $A^{\top}\boldsymbol{y}\ge 0$ and $\mu \le 0$.  

### 5.5. Supporting Hyperplanes Theorem
Suppose $C \subseteq \mathbb{R}^n$, and $\boldsymbol{x}_0$ is a point in its boundary $\partial C$. If $\boldsymbol{a} \neq \boldsymbol{0}$ satisfies $\boldsymbol{a}^{\top}  \boldsymbol{x} \leq \boldsymbol{a}^{\top}  \boldsymbol{x}_0$ for all $\boldsymbol{x} \in C$, then the hyperplane $\left\{\boldsymbol{x} \mid \boldsymbol{a}^{\top}  \boldsymbol{x}=\boldsymbol{a}^{\top}  \boldsymbol{x}_0\right\}$ is called a supporting hyperplane to $C$ at the point $\boldsymbol{x}_0$.

For any nonempty convex set $C$, and any $\boldsymbol{x}_0\in \partial C$, there exists a supporting hyperplane to $C$ at $\boldsymbol{x}_0$.