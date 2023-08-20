## 1. Proper Cone and Generalized Inequality
### 1.1. 真锥(Proper Cone)的定义
锥$K\subset \mathbb{R}^n$被称为proper cone, 如果它满足下列的条件
1. $K$是凸的
2. $K$是闭的
3. $K$是实(solid)的, 也就是说, $K$有非空的内点集
4. $K$是单向(pointed)的, 也就是说, $K\cap -K = \{\boldsymbol{0}\}$

### 1.2. Generalized Inequality
我们可以定义在proper cone $K$上的generalized inequality $\preceq_K$, 其偏序关系为
$$
\boldsymbol{x} \preceq_K \boldsymbol{y} \iff \boldsymbol{y}-\boldsymbol{x} \in K
$$
类似地, 我们可以定义严格偏序关系为
$$
\boldsymbol{x} \prec_K \boldsymbol{y} \iff \boldsymbol{y}-\boldsymbol{x} \in K^{\circ}
$$

### 1.3. Generalized Inequality $\preceq_K$的性质
1. **在加法下保持**: 如果$\boldsymbol{x}\preceq_K \boldsymbol{y}$并且$\boldsymbol{u}\preceq_K \boldsymbol{v}$, 那么$\boldsymbol{x}+\boldsymbol{u}\preceq_K \boldsymbol{y}+\boldsymbol{v}$
2. **传递性**: 如果$\boldsymbol{x}\preceq_K \boldsymbol{y}$并且$\boldsymbol{y}\preceq_K \boldsymbol{z}$, 那么$\boldsymbol{x}\preceq_K \boldsymbol{z}$
3. **在非负标量乘法下保持**: 如果$\boldsymbol{x}\preceq_K \boldsymbol{y}$并且$\alpha\ge 0$, 那么$\alpha\boldsymbol{x}\preceq_K \alpha\boldsymbol{y}$
4. **反身性**: $\boldsymbol{x}\preceq_K \boldsymbol{x}$
5. **反对称性**: 如果$\boldsymbol{x}\preceq_K \boldsymbol{y}$并且$\boldsymbol{y}\preceq_K \boldsymbol{x}$, 那么$\boldsymbol{x}=\boldsymbol{y}$
6. **在极限下保持**: 如果$\boldsymbol{x}_i\preceq_K \boldsymbol{y}_i$对于所有的$k$成立, 并且$\boldsymbol{x}_i\to \boldsymbol{x}$, $\boldsymbol{y}_i\to \boldsymbol{y}$, 那么$\boldsymbol{x}\preceq_K \boldsymbol{y}$

### 1.4. 最大值和极小值(Minimum and Minimal Elements)
设$\boldsymbol{x}\in S$, 如果对任意的$\boldsymbol{y}\in S$, 有$\boldsymbol{x}\preceq_K \boldsymbol{y}$, 则称$\boldsymbol{x}$是$S$中的最小值. $\boldsymbol{x}$是$S$中的最小值当且仅当
$$
S\subseteq \boldsymbol{x} + K
$$

如果对任意的$\boldsymbol{y}\in S$, $\boldsymbol{y}\preceq_K \boldsymbol{x}$当且仅当$\boldsymbol{y} = \boldsymbol{x}$, 则称$\boldsymbol{x}$是$S$中的极小值. $\boldsymbol{x}\in S$是$S$中的极小值当且仅当
$$
(\boldsymbol{x} - K)\cap S = \{\boldsymbol{x}\} 
$$


## 2. Dual Cones 
### 2.1. Dual Cones的定义
设$K$是一个锥, 集合
$$
K^* = \{\boldsymbol{y}\mid \boldsymbol{y}^{\top}\boldsymbol{x}\ge 0, \forall \boldsymbol{x}\in K\}
$$
被称为$K$的对偶锥.

![image-0](Lecture%203.%20%E7%9C%9F%E9%94%A5%E5%92%8C%E5%AF%B9%E5%81%B6%E9%94%A5.assets/%E5%AF%B9%E5%81%B6%E9%94%A5.png)  


### 2.2. Dual Cones的例子
#### 2.2.1. 子空间
子空间$V\subseteq \mathbb{R}^n$的对偶锥是其正交补$V^{\perp} = \{\boldsymbol{y}\mid \boldsymbol{y}^{\top}\boldsymbol{v} = 0,\forall \boldsymbol{v}\in V\}$

#### 2.2.2. 半正定锥
半正定锥$\mathbb{S}_+^n$的对偶锥是半正定锥$\mathbb{S}_+^n$本身, 即对任意的$X, Y\in \mathbb{S}^n$
$$
\operatorname{tr}(XY) \ge 0, \forall X\in \mathbb{S}_+^n \iff Y\in \mathbb{S}_+^n
$$

#### 2.2.3. 范数锥
令$\|\cdot\|$为定义在$\mathbb{R}^n$上的范数, 与之相关的锥$K = \{(\boldsymbol{x}, t)\in \mathbb{R}^{n+1}\mid \|\boldsymbol{x}\|\le t\}$的对偶锥由其对偶范数定义
$$
K^* = \{(\boldsymbol{y}, s)\in \mathbb{R}^{n+1}\mid \|\boldsymbol{y}\|_*\le s\}
$$ 

### 2.3. Dual Cones的性质
Dual Cones 满足如下的性质
1. $K^*$是凸锥并且$K^*$是闭的
2. $K_1\subset K_2\implies K_2^* \subset K_1^*$
3. 如果$K$有非空的内点集, 则$K^*$是pointed的, 也就是说 $K^* \cap - K^* = \{0\}$
4. 如果$K$的闭包是pointed的, 则$K^*$有非空的内点集
5. $K^{**}$是$K$的凸包的闭包, 也就是说, 如果$K$是凸的并且是闭的, 则$K^{**} = K$
6. 如果$K$是proper cone, 则其dual cone也是 proper cone. 

___
##### Proof
设$K$是一个锥, $K$的对偶锥为
$$
K^* = \{\boldsymbol{y}\mid \boldsymbol{y}^{\top}\boldsymbol{x}\ge 0, \forall \boldsymbol{x}\in K\}
$$
1. 显然, 对任意的$\boldsymbol{y}_1, \boldsymbol{y}_2 \in K^*$和$\lambda_1, \lambda_2>0$, 我们有$(\lambda_1 \boldsymbol{y}_1 + \lambda_2 \boldsymbol{y}_2)^{\top}\boldsymbol{x}\ge 0$, 因此$K^*$是一个凸锥, 又对任意的收敛到$\boldsymbol{y}$的序列$\boldsymbol{y}_k\in K^*$, 有
   $$
   \boldsymbol{y}^{\top}_k\boldsymbol{x}\ge 0, \forall \boldsymbol{x}\in K \implies \boldsymbol{y}^{\top}\boldsymbol{x}\ge 0, \forall \boldsymbol{x}\in K
   $$
   因此$K^*$是闭的.
2. 因为
   $$
   K_1^* = \{\boldsymbol{y}\mid \boldsymbol{y}^{\top}\boldsymbol{x}\ge 0, \forall \boldsymbol{x}\in K_1\}, \quad K_2^* = \{\boldsymbol{y}\mid \boldsymbol{y}^{\top}\boldsymbol{x}\ge 0, \forall \boldsymbol{x}\in K_2\}
   $$
   对任意的$\boldsymbol{y_2}\in K_2^*$, 既然$K_1\subseteq K_2$, 那么
   $$
   \boldsymbol{y}^{\top}\boldsymbol{x}\ge 0, \quad \forall \boldsymbol{x}\in K_2\implies \boldsymbol{y}^{\top}\boldsymbol{x}\ge 0, \quad \forall \boldsymbol{x}\in K_1
   $$   
   这就得到了$K_2^*\subseteq K_1^*$
3. 如果$K$有非空的内点集, 那么存在一个$\boldsymbol{x}_0\in K$和某个$\varepsilon>0$使得$\mathcal{B}(\boldsymbol{x}_0, \varepsilon)\in K$. 假设$\boldsymbol{y}$和$-\boldsymbol{y}$都在$K^*$中, 那么
   $$
   \boldsymbol{y}^{\top}\boldsymbol{x}\ge 0, \quad -\boldsymbol{y}^{\top}\boldsymbol{x}\ge 0,\quad \forall \boldsymbol{x}\in \mathcal{B}(\boldsymbol{x}_0, \varepsilon)
   $$
   因为$\mathcal{B}(\boldsymbol{x}_0, \varepsilon)$的维数为$n$, 因此$\boldsymbol{y} = 0$, 于是我们得到了$K^*\cap -K^* = \{\boldsymbol{0}\}$
4. 用反证法, 因为$K^*$是一个凸锥, 因此$K^*$的内点集是空的当且仅当$K^*$的维数至多为$n-1$. 不妨设$K^*$的维数为$k$, 并且设$\mathrm{span}\left(K^*\right) = \{\boldsymbol{u}_1, \boldsymbol{u}_2, \cdots, \boldsymbol{u}_k\}$, 于是我们有
   $$
   \boldsymbol{y} =\lambda_1 \boldsymbol{u}_1 + \lambda_2 \boldsymbol{u}_2 + \cdots + \lambda_k \boldsymbol{u}_k
   $$
   根据$K^*$的定义, 我们知道对任意的$\boldsymbol{x}\in K$, 都有$\boldsymbol{y}^{\top}\boldsymbol{x}\ge 0$, 因此
   $$
   \lambda_1 \boldsymbol{u}_1^{\top}\boldsymbol{x} + \lambda_2 \boldsymbol{u}_2^{\top}\boldsymbol{x} + \cdots + \lambda_k \boldsymbol{u}_k^{\top}\boldsymbol{x} \ge 0, \quad \forall \boldsymbol{x}\in K
   $$
   考虑$\boldsymbol{u}_{k+1}$是和$\mathrm{span}\left(\{\boldsymbol{u}_1, \boldsymbol{u}_2, \cdots, \boldsymbol{u}_k\}\right)$不相关的向量, 如果
   $$
   \lambda_1 \boldsymbol{u}_1^{\top}\boldsymbol{x} + \lambda_2 \boldsymbol{u}_2^{\top}\boldsymbol{x} + \cdots + \lambda_k \boldsymbol{u}_k^{\top}\boldsymbol{x} > 0,\quad \forall \boldsymbol{x}\in K
   $$
   那么取一个很小的$\lambda_{k+1}$, 我们可以保证
   $$
   \lambda_1 \boldsymbol{u}_1^{\top}\boldsymbol{x} + \lambda_2 \boldsymbol{u}_2^{\top}\boldsymbol{x} + \cdots + \lambda_k \boldsymbol{u}_k^{\top}\boldsymbol{x} + \lambda_{k+1}\boldsymbol{u}_{k+1}^{\top}\boldsymbol{x} \ge  0 , \quad \forall \boldsymbol{x}\in K
   $$
   这与$K^*$的维数是$k$矛盾! 
5. 根据$K^*$的定义, 我们知道对任意的$\boldsymbol{x}\in K$, 都有$\boldsymbol{x}^{\top}\boldsymbol{y}\ge 0, \forall \boldsymbol{y}\in K^*$, 因此$K\subseteq K^{**}$. 根据性质1, $K^{**}$是凸的并且是闭的, 因此$K^{**}\subseteq \overline{\mathrm{conv}(K)}$. 
6. 根据Proper Cone的定义, 根据性质3, 可以得到$K^*$是pointed的, 根据性质4, 可以得到$K^*$有非空的内点集, 根据性质1, 可以得到$K^*$是凸的并且是闭的, 因此$K^*$是proper cone.
#####
___
### 2.4. Dual Generalized Inequality
设$K$是一个proper cone, 那么$K^*$也是一个proper cone, 因此可以定义在$K^*$上的generalized inequality $\preceq_{K^*}$, Generalized Inequality $\preceq_{K^*}$被称为$\preceq_{K}$的对偶. 

### 2.5. Dual Generalized Inequality $\preceq_{K^*}$的性质
1. $\boldsymbol{x}\preceq_{K}\boldsymbol{y}$ 当且仅当 $\boldsymbol{\lambda}^{\top}\boldsymbol{x}\le \boldsymbol{\lambda}^{\top}\boldsymbol{y}$对任意的$\boldsymbol{\lambda}\succeq_{K^*} \boldsymbol{0}$成立
2. $\boldsymbol{x}\prec_{K}\boldsymbol{y}$ 当且仅当 $\boldsymbol{\lambda}^{\top}\boldsymbol{x}< \boldsymbol{\lambda}^{\top}\boldsymbol{y}$对任意的$\boldsymbol{\lambda}\succeq_{K^*} \boldsymbol{0}$且$\boldsymbol{\lambda}\neq \boldsymbol{0}$成立
3. $\boldsymbol{x}\in S$是$S$中关于$\preceq_k$的minimum element当且仅当对所有的$\boldsymbol{\lambda}\succ_{K^*}\boldsymbol{0}$, $\boldsymbol{x}=\operatorname*{argmin}\limits_{\boldsymbol{z}\in S} \boldsymbol{\lambda}^{\top}\boldsymbol{z}$. 也就是说, 对任意的$\boldsymbol{\lambda}\succ_{K^*}\boldsymbol{0}$, 超平面
   $$
   \{\boldsymbol{z}\mid \boldsymbol{\lambda}^{\top}(\boldsymbol{z} - \boldsymbol{x}) = 0\}
   $$
   是$S$关于$\boldsymbol{x}$的strict supporting hyperplane.
4. 设$\boldsymbol{x}\in S$, 如果$\boldsymbol{\lambda}\succ_{K^*}\boldsymbol{0}$, 并且$\boldsymbol{x}\in \operatorname*{argmin}\limits_{\boldsymbol{z}\in S} \boldsymbol{\lambda}^{\top}\boldsymbol{z}$, 那么$\boldsymbol{x}$是$S$中关于$\preceq_k$的minimal element. 反过来, 如果$S$是凸的, 并且对任意的极小值$\boldsymbol{x}$存在一个非零的$\boldsymbol{\lambda}\succeq_{K^*}\boldsymbol{0}$, 使得$\boldsymbol{x}$最小化$\boldsymbol{\lambda}^{\top}\boldsymbol{z}$. 
   
___
##### Proof
#####
___