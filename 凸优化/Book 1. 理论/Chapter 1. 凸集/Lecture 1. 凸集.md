## 1. 凸集
### 1.1. 凸集的定义
集合 $C$ 被称为是凸的, 如果对任意的$\boldsymbol{x}_1, \boldsymbol{x}_2\in C$, 线段$\boldsymbol{x}_1 \boldsymbol{x}_2$都在 $C$中. 即
$$
\theta \boldsymbol{x}_1 + (1-\theta)\boldsymbol{x}_2\in C, \quad 0\le \theta\le 1
$$

### 1.2. 凸集的例子
1. Empty Set: $\varnothing$
2. Norm Ball: $\{\boldsymbol{x}\mid \|\boldsymbol{x}\|\le r\}$
3. Hyperplane: $\{\boldsymbol{x}\mid \boldsymbol{a}^{\top}\boldsymbol{x} = b\}$
4. Halfspace: $\{\boldsymbol{x} \mid \boldsymbol{a}^{\top}\boldsymbol{x}\le b\}$
5. Affine Space: $\{\boldsymbol{x}\mid \mathcal{A}(\boldsymbol{x}) = \boldsymbol{b}\}$
6. Polyhedron: $\{\boldsymbol{x}\mid A\boldsymbol{x}\le \boldsymbol{b}\}$

### 1.3. 广义凸组合(Generalized Convex Combination)
设$C\subseteq \mathbb{R}^n$是一个凸集,  $\boldsymbol{x}_1, \boldsymbol{x}_2, \cdots\in C$. 假设$\theta_1, \theta_2,\cdots$ 满足
$$
\theta_i\ge 0, \quad i=1,2,\cdots,\quad \sum\limits_{i=1}^{\infty}\theta_i = 1
$$
如果$\sum\limits_{i=1}^{\infty}\theta_i\boldsymbol{x}_i$收敛, 则有$\sum\limits_{i=1}^{\infty}\theta_i\boldsymbol{x}_i \in C$. 

更一般地, 假设 $p: \mathbb{R}^n\to \mathbb{R}$ 满足 $p(\boldsymbol{x})\ge 0, \forall \boldsymbol{x}\in C$ 和 $\displaystyle{\int} p(\boldsymbol{x}) \, \mathrm{d}\boldsymbol{x}=1$, 则有
$$
\mathbb{E}\boldsymbol{x} = \int \boldsymbol{x}p(\boldsymbol{x}) \, \mathrm{d}\boldsymbol{x} \in C \quad \text{If the integral exists. }
$$

### 1.4. 凸包(Convex Hull)
集合 $C$ 的凸包是集合$C$中所有点的凸组合,  记为$\mathrm{conv}C$ 
$$
\mathrm{conv}C = \{\theta_1\boldsymbol{x}_1+\cdots+\theta_k\boldsymbol{x}_k\mid \boldsymbol{x}_i\in C, \theta_i\ge 0, i=1,2,\cdots,k, \theta_1+\theta_2+\cdots+\theta_k=1\}
$$
$\mathrm{conv}C$ 是包含$C$的最小凸集.



## 2. 锥(Cone)

### 2.1 锥和凸锥

集合$C$ 被称为锥, 如果对于任意的 $\boldsymbol{x}\in C$ 和 $\theta\ge 0$, 都有 $\theta \boldsymbol{x}\in C$. 集合 $C$ 被称为凸锥如果它既是凸的也是一个锥, 也就是说, 对任意的$\boldsymbol{x}_1, \boldsymbol{x}_2\in C$ 和 $\theta_1, \theta_2\ge 0$, 都有 
$$
\theta_1 \boldsymbol{x}_1 + \theta_2\boldsymbol{x}_2\in C
$$


### 2.2. Conic Hull
集合 $C$的conic hull是 $C$中所有点的锥组合, 记为 $\mathrm{cone}C$
$$
\{\theta_1\boldsymbol{x}_1 + \cdots+ \theta_k\boldsymbol{x}_k\mid \boldsymbol{x}_i\in C, \theta_i\ge0, i=1,2,\cdots,k\}
$$
$\mathrm{cone}C$是包含$C$的最小凸锥. 


### 2.3. Norm cone 的重要例子
#### 2.3.1. 超平面和半空间
超平面是具有如下形式的集合
$$
\{\boldsymbol{x} \mid \boldsymbol{a}^{\top}\boldsymbol{x} = b\}, \quad \boldsymbol{a}\in \mathbb{R}^n, \boldsymbol{a}\ne \boldsymbol{0}, b\in \mathbb{R}
$$
对于任意的$\boldsymbol{x}_0$满足$\boldsymbol{a}^{\top}\boldsymbol{x}_0 = b$, 超平面可以被写成
$$
\{\boldsymbol{x} \mid \boldsymbol{a}^{\top}\boldsymbol{x} = b\} = \boldsymbol{x}_0 + \boldsymbol{a}^{\perp}
$$

一个超平面将$\mathbb{R}^n$划分为两个半平面. 半平面具有如下的表达形式
$$
\{\boldsymbol{x}\mid \boldsymbol{a}^{\top} \boldsymbol{x}\le b\}
$$


#### 2.3.2. Euclidean Balls and Ellipsoids
$\mathbb{R}^n$上的Euclidean ball是具有如下形式的集合
$$
\mathcal{B}(\boldsymbol{x}_0, r) = \{\boldsymbol{x}\mid \|\boldsymbol{x} - \boldsymbol{x}_0\|_2\le r\} 
$$
令一种常见的Euclidean ball的表示方法是
$$
\mathcal{B}(\boldsymbol{x}_0, r) = \{\boldsymbol{x}_0 + r\boldsymbol{u}\mid \|\boldsymbol{u}\|_2\le 1\}
$$
拓展距离的定义, 可以得到ellipsoid, 具有如下形式
$$
\mathcal{E} = \{\boldsymbol{x}\mid (\boldsymbol{x} - \boldsymbol{x}_0)^{\top}P^{-1}(\boldsymbol{x} - \boldsymbol{x}_0)\}, \quad P\succ 0
$$
另一种常见的ellipsoid的表示方法为
$$
\mathcal{E} = \{\boldsymbol{x}_0 + Au\mid \|\boldsymbol{u}\|_2\le 1\}, \quad A = P^{\frac{1}{2}}
$$

#### 2.3.3. Norm ball and norm cone
对于一般的范数$\|\cdot\|$, 定义与其相关的norm ball为
$$
\{\boldsymbol{x}\mid \|\boldsymbol{x} - \boldsymbol{x}_0\|\le r\}
$$
定义与范数$\|\cdot\|$相关的norm cone为
$$
C = \{(\boldsymbol{x}, t)\mid \|\boldsymbol{x}\|\le t\} \subset \mathbb{R}^{n+1}
$$
当使用二阶范数$\|\cdot\|_2$时, 我们得到如下图所示的二阶锥(second-order cone).

![image-20230619150824470](Chapter%201.%20凸集/Lecture%201.%20凸集.assets/image-20230619150824470.png)


#### 2.3.4. Polyhedra
一个Polyhedra是由有限个线性等式和线性不等式的解定义的集合
$$
\begin{aligned} 
\mathcal{P} &= \{\boldsymbol{a}_i^{\top}\boldsymbol{x}\le b_i,\ \boldsymbol{c}_j^{\top}\boldsymbol{x} = d_j,\quad  i=1,2,\cdots, m, j=1,2,\cdots, p\} \\ 
&= \{\boldsymbol{x}\mid A\boldsymbol{x}\preceq \boldsymbol{b}, C\boldsymbol{x} = \boldsymbol{d}\}
\end{aligned}
$$
因此, Polyhedra是有限个半空间和超平面的交集. 

#### 2.3.5. 半正定锥(positive semidefinite cone)
我们用$\mathbb{S}^n$表示所有对称的$n\times n$矩阵组成的集合
$$
\mathbb{S}^n = \{X\in \mathbb{R}^{n\times n}\mid X = X^{\top}\}
$$
用$\mathbb{S}^n_+$表示所有半正定矩阵组成的集合, 称其为半正定锥(positive semidefinite cone)
$$
\mathbb{S}^n_+ = \{X\in \mathbb{S}^n\mid X\succeq 0\}
$$
用$\mathbb{S}^n_{++}$表示所有正定矩阵组成的集合
$$
\mathbb{S}^n_{++} = \{X\in \mathbb{S}^n\mid X\succ 0\}
$$


## 3. 仿射集(Affine Sets)

### 3.1. 仿射子空间(Affine Subspaces)
一个集合$C$被称为仿射子空间, 当且仅当对任意$\boldsymbol{x}_1$, $\boldsymbol{x}_2\in C$, 都有过$\boldsymbol{x}_1$, $\boldsymbol{x}_2$的直线包含在$C$中, 也就是说
$$
\theta_1\boldsymbol{x}_1+(1-\theta)\boldsymbol{x}_2 = \boldsymbol{y} \in C
$$
如果 $C$ 是一个仿射子空间并且 $\boldsymbol{x}_0\in C$, 则
$$
V = C - \boldsymbol{x}_0= \{\boldsymbol{x}-\boldsymbol{x}_0\mid \boldsymbol{x}\in C\}
$$
是一个线性子空间.  我们定义仿射子空间的维数为$\mathrm{dim}C = \mathrm{dim}V$

### 3.2. 仿射组合(Affine Combination)
设$C\subset \mathbb{R}^n$是一个点集, $\boldsymbol{x}_1, \cdots, \boldsymbol{x}_k\in C$, $\theta_1, \cdots, \theta_k\in \mathbb{R}$, 且$\theta_1+\cdots+\theta_k=1$, 则
$$
\theta_1\boldsymbol{x}_1 + \cdots + \theta_k\boldsymbol{x}_k
$$
被称为$C$中点$\boldsymbol{x}_1, \cdots, \boldsymbol{x}_k$的仿射组合.

### 3.3. 仿射包(Affine Hull)
集合 $C$ 中所有点的仿射组合被称为集合 $C$ 的仿射包, 记为 $\mathrm{aff} C$
$$
\mathrm{aff}C = \{\theta_1\boldsymbol{x}_1+\cdots+\theta_k\boldsymbol{x}_k\mid \boldsymbol{x}_1,\cdots, \boldsymbol{x}_k\in C, \theta_1+ \cdots+\theta_k=1\}
$$
$\mathrm{aff} C$是包含$C$的最小的仿射子空间. 我们定义集合$C$的仿射维数为其仿射包$\mathrm{aff} C$的维数. 


### 3.4. 相对内点(Relative Interior)
如果$\mathrm{aff}C \neq \mathbb{R}^n$, 定义集合$C$的相对内点如下
$$
\operatorname{ri} C=\{\boldsymbol{x} \in C \mid \mathcal{B}(\boldsymbol{x}, r) \cap \operatorname{aff} C \subseteq C \text { for some } r>0\}
$$
我们可以定义集合 $C$ 的相对边界(relative bound)为 $\overline{C}\backslash \mathrm{ri}C$, 其中$\overline{C}$是$C$的闭包(closure). 





