## 1. 凸集
### 1.1. 凸集的定义
集合 $C$ 被称为是凸的, 如果对任意的$\boldsymbol{x}_1, \boldsymbol{x}_2\in C$, 都有
$$
\theta \boldsymbol{x}_1 + (1-\theta)\boldsymbol{x}_2\in C, \quad 0\le \theta\le 1
$$

### 1.2. 广义凸组合(Generalized Convex Combination)
设$C\subseteq \mathbb{R}^n$是一个凸集,  $\boldsymbol{x}_1, \boldsymbol{x}_2, \cdots\in C$. 假设$\theta_1, \theta_2,\cdots$ 满足
$$
\theta_i\ge 0, \quad i=1,2,\cdots,\quad \sum\limits_{i=1}^{\infty}\theta_i = 1
$$
如果$\sum\limits_{i=1}^{\infty}\theta_i\boldsymbol{x}_i$收敛, 则有$\sum\limits_{i=1}^{\infty}\theta_i\boldsymbol{x}_i \in C$. 

更一般地, 假设 $p: \mathbb{R}^n\to \mathbb{R}$ 满足 $p(\boldsymbol{x})\ge 0, \forall \boldsymbol{x}\in C$ 和 $\displaystyle{\int} p(\boldsymbol{x}) \, \mathrm{d}\boldsymbol{x}=1$, 则有
$$
\mathbb{E}\boldsymbol{x} = \int \boldsymbol{x}p(\boldsymbol{x}) \, \mathrm{d}\boldsymbol{x} \in C \quad \text{If the integral exists. }
$$

### 1.3. 凸包(Convex Hull)
集合 $C$ 的凸包是集合$C$中所有点的凸组合,  记为$\mathrm{conv}C$ 
$$
\mathrm{conv}C = \{\theta_1\boldsymbol{x}_1+\cdots+\theta_k\boldsymbol{x}_k\mid \boldsymbol{x}_i\in C, \theta_i\ge 0, i=1,2,\cdots,k, \theta_1+\theta_2+\cdots+\theta_k=1\}
$$
$\mathrm{conv}C$ 是包含$C$的最小凸集.

## 2. 锥(Cone)
### 2.1 锥和凸锥
集合$C$ 被称为锥, 如果对于任意的 $\boldsymbol{x}\in C$ 和 $\theta\ge 0$, 都有 $\theta \boldsymbol{x}\in C$. 

集合 $C$ 被称为凸锥, 如果它既是凸的也是一个锥, 也就是说, 对任意的$\boldsymbol{x}_1, \boldsymbol{x}_2\in C$ 和 $\theta_1, \theta_2\ge 0$, 都有 
$$
\theta_1 \boldsymbol{x}_1 + \theta_2\boldsymbol{x}_2\in C
$$


### 2.2. Conic Hull
集合 $C$的conic hull是 $C$中所有点的锥组合, 记为 $\mathrm{cone}C$
$$
\mathrm{cone}C = \{\theta_1\boldsymbol{x}_1 + \cdots+ \theta_k\boldsymbol{x}_k\mid \boldsymbol{x}_i\in C, \theta_i\ge0, i=1,2,\cdots,k\}
$$
$\mathrm{cone}C$是包含$C$的最小凸锥. 


### 2.3. 例子
#### 2.3.1. 超平面和半空间
超平面是具有如下形式的集合
$$
\{\boldsymbol{x} \mid \boldsymbol{a}^{\top}\boldsymbol{x} = b\}, \quad \boldsymbol{a}\in \mathbb{R}^n, \boldsymbol{a}\ne \boldsymbol{0}, b\in \mathbb{R}
$$
对于任意的$\boldsymbol{x}_0$满足$\boldsymbol{a}^{\top}\boldsymbol{x}_0 = b$, 超平面可以被写成
$$
\{\boldsymbol{x} \mid \boldsymbol{a}^{\top}\boldsymbol{x} = b\} = \boldsymbol{x}_0 + \boldsymbol{a}^{\perp}
$$

一个超平面将$\mathbb{R}^n$划分为两个半空间. 半空间具有如下的表达形式
$$
\{\boldsymbol{x}\mid \boldsymbol{a}^{\top} \boldsymbol{x}\le b\}, \quad \boldsymbol{a}\in \mathbb{R}^n, \boldsymbol{a}\ne \boldsymbol{0}, b\in \mathbb{R}
$$


#### 2.3.2. Euclidean Balls and Ellipsoids
$\mathbb{R}^n$上的Euclidean ball是具有如下形式的集合
$$
\mathcal{B}(\boldsymbol{x}_0, r) = \{\boldsymbol{x}\mid \|\boldsymbol{x} - \boldsymbol{x}_0\|_2\le r\} 
$$
另一种常见的Euclidean ball的表示方法是
$$
\mathcal{B}(\boldsymbol{x}_0, r) = \{\boldsymbol{x}_0 + r\boldsymbol{u}\mid \|\boldsymbol{u}\|_2\le 1\}
$$
拓展距离的定义, 可以得到ellipsoid, 椭球具有如下形式
$$
\mathcal{E} = \{\boldsymbol{x}\mid (\boldsymbol{x} - \boldsymbol{x}_0)^{\top}P^{-1}(\boldsymbol{x} - \boldsymbol{x}_0)\}, \quad P\succ 0
$$
另一种常见的ellipsoid的表示方法为
$$
\mathcal{E} = \{\boldsymbol{x}_0 + Au\mid \|\boldsymbol{u}\|_2\le 1\}, \quad A = P^{\frac{1}{2}}
$$

#### 2.3.3. Norm Ball and Norm Cone
对于一般的范数$\|\cdot\|$, 定义与其相关的norm ball为
$$
\{\boldsymbol{x}\mid \|\boldsymbol{x} - \boldsymbol{x}_0\|\le r\}
$$
定义与范数$\|\cdot\|$相关的norm cone为
$$
C = \{(\boldsymbol{x}, t)\mid \|\boldsymbol{x}\|\le t\} \subset \mathbb{R}^{n+1}
$$
当使用二阶范数$\|\cdot\|_2$时, 我们得到如下图所示的二阶锥(second-order cone).

![image-20230619150824470](Lecture%201.%20凸集.assets/image-20230619150824470.png)


#### 2.3.4. 多面体(Polyhedra)
一个Polyhedra是由有限个线性等式和线性不等式的解定义的集合
$$
\begin{aligned} 
\mathcal{P} &= \{\boldsymbol{a}_i^{\top}\boldsymbol{x}\le b_i,\ \boldsymbol{c}_j^{\top}\boldsymbol{x} = d_j,\  i=1,2,\cdots, m,\ j=1,2,\cdots, p\} \\ 
&= \{\boldsymbol{x}\mid A\boldsymbol{x}\preceq \boldsymbol{b}, C\boldsymbol{x} = \boldsymbol{d}\}
\end{aligned}
$$
从几何上来说, Polyhedra是有限个半空间和超平面的交集. 

多面体有另外一种凸包描述, 考虑
$$
\mathcal{P}^{\prime} = \{\theta_1\boldsymbol{v}_1 + \theta_2\boldsymbol{v}_2 + \cdots + \theta_m\boldsymbol{v}_m +\cdots + \theta_k \boldsymbol{v}_k \mid \theta_1+\theta_2+\cdots +\theta_m =1, \theta_i\ge 0, i=1,2,\cdots, k\}, \quad m\le k
$$
$\mathcal{P}^{\prime}$可以被解释为$\boldsymbol{v}_1, \cdots, \boldsymbol{v}_m$的凸包加上点$\boldsymbol{v}_{m+1}, \cdots, \boldsymbol{v}_k$的锥包. 这样定义的$\mathcal{P}^{\prime}$是一个多面体, 并且每个多面体都可以表示为此类形式. 
___
##### Note
如何表示多面体是微妙的. 考虑$\ell_{\infty}$-norm下的$\mathbb{R}^n$中的单位球
$$
C = \{\boldsymbol{x}\mid |x_i|\le 1, i=1, 2, \cdots, n\}
$$
如果用半空间和超平面的交集来表示, 那么
$$
C = \{\boldsymbol{x}\mid \pm \boldsymbol{e}_i^{\top}\boldsymbol{x}\le 1, i=1,2, \cdots, n\}
$$
但如果用凸包和锥包来表示, 那么至少需要$2^n$个点
$$
C = \mathrm{conv}\{\boldsymbol{v}_1, \cdots, \boldsymbol{v}_{2^n}\}
$$
其中$\boldsymbol{v}_1, \cdots, \boldsymbol{v}_{2^n}$是所有元素均为$1$或$-1$的向量. 因此, 这两种表现形式的成本是差异巨大的. 
#####
___

#### 2.3.5. 单纯形(Simplexes)
单纯形是一类重要的多面体, 设$k+1$个点$\boldsymbol{v}_0, \cdots, \boldsymbol{v}_k\in \mathbb{R}^n$仿射独立, 即$\boldsymbol{v}_1 - \boldsymbol{v}_0, \cdots , \boldsymbol{v}_k - \boldsymbol{v}_0$线性独立. 那么, 这些点决定了一个单纯形
$$
C = \mathrm{conv}\{\boldsymbol{v}_0, \cdots , \boldsymbol{v}_k\} = \{\theta_0\boldsymbol{v}_0 + \cdots + \theta_k\boldsymbol{v}_k\mid \boldsymbol{\theta}\succeq \boldsymbol{0}, \sum_{i=0}^k\theta_i = 1\}
$$
这个单纯形的仿射维度为$k$, 因此也称为$\mathbb{R}^n$空间上的$k$维单纯形. 
___
##### Proof 单纯形是多面体
考虑$B = (\boldsymbol{v}_1 - \boldsymbol{v}_0, \cdots, \boldsymbol{v}_k - \boldsymbol{v}_0)\in \mathbb{R}^{n\times k}$. 我们知道$\boldsymbol{x}\in C$的充要条件为
$$
\boldsymbol{x} = \boldsymbol{v}_0 + B\boldsymbol{y}, \quad \boldsymbol{y}\succeq \boldsymbol{0},\ \boldsymbol{1}^{\top}\boldsymbol{y} \le 1
$$
因为$B$的秩为$k$, 因此存在非奇异矩阵$A = (A_1, A_2)\in \mathbb{R}^{n\times n}$使得
$$
AB = \begin{pmatrix} A_1\\ A_2\end{pmatrix}\begin{pmatrix}B_1\\   B_2\end{pmatrix} = \begin{pmatrix}I_k \\ 0\end{pmatrix}
$$
于是我们得到了$\boldsymbol{x}\in C$的充分必要条件为
$$
A_2\boldsymbol{x} = A_2\boldsymbol{v}_0, \quad A_1\boldsymbol{x}\succeq A_1\boldsymbol{v}_0, \quad \boldsymbol{1}^{\top}A_1\boldsymbol{x} \le 1 + \boldsymbol{1}^{\top}A_1\boldsymbol{v}_0
$$
这描述了一个多面体. 
#####
___



#### 2.3.6. 半正定锥(positive semidefinite cone)
用$\mathbb{S}^n_+$表示所有半正定矩阵组成的集合, 称其为半正定锥
$$
\mathbb{S}^n_+ = \{X\in \mathbb{S}^n\mid X\succeq 0\}
$$

![image-1](Lecture%201.%20%E5%87%B8%E9%9B%86.assets/R%5E2%E4%B8%AD%E7%9A%84%E6%AD%A3%E5%AE%9A%E9%94%A5%E8%BE%B9%E7%95%8C.png)  


## 3. 仿射集(Affine Sets)

### 3.1. 仿射子空间(Affine Subspaces)
一个集合$C$被称为仿射子空间, 当且仅当对任意$\boldsymbol{x}_1$, $\boldsymbol{x}_2\in C$, 有
$$
\theta_1\boldsymbol{x}_1+(1-\theta)\boldsymbol{x}_2  \in C,\quad \forall \theta\in\mathbb{R}
$$
如果 $C$ 是一个仿射子空间并且 $\boldsymbol{x}_0\in C$, 那么
$$
V = C - \boldsymbol{x}_0= \{\boldsymbol{x}-\boldsymbol{x}_0\mid \boldsymbol{x}\in C\}
$$
是一个线性子空间.  定义仿射子空间的维数为$\mathrm{dim}C = \mathrm{dim}V$. 

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
$\mathrm{aff} C$是包含$C$的最小的仿射子空间. 

定义集合$C$的仿射维数为其仿射包$\mathrm{aff} C$的维数.
___
##### Note: 仿射维数与正常
考虑$\{\boldsymbol{x}\in \mathbb{R}^2\mid x_1^2 +x_2^2 = 1\}$, 它的仿射包(affine hull)是$\mathbb{R}^2$, 因此它的仿射维数(affine dimension)为2. 但通常$\mathbb{R}^2$中的单位球的维数为1.
#####
___ 


### 3.4. 相对内点(Relative Interior)和相对边界(Relative Boundary)
对于任意的集合$C$满足$\mathrm{aff}C \neq \mathbb{R}^n$, 定义集合$C$的相对内点为
$$
\operatorname{ri} C=\{\boldsymbol{x} \in C \mid \mathcal{B}(\boldsymbol{x}, r) \cap \operatorname{aff} C \subseteq C \text { for some } r>0\}
$$
定义集合 $C$ 的相对边界为 $\overline{C}\backslash \mathrm{ri}C$, 其中$\overline{C}$是$C$的闭包(closure). 


