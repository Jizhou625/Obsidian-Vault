## 1. 基本术语
### 1.1. 优化问题
优化问题的一般形式为
$$
\begin{array}{ll}
\operatorname{minimize} & f_0(\boldsymbol{x}) \\
\text { subject to } & f_i(\boldsymbol{x}) \leq 0, \quad i=1, \cdots, m \\
& h_i(\boldsymbol{x})=0, \quad i=1, \cdots, p
\end{array} \tag{1}
$$
我们称$\boldsymbol{\boldsymbol{x}}\in \mathbb{R}^n$是优化变量, 称函数$f_0: \mathbb{R}^n\to \mathbb{R}$为目标函数或费用函数. 不等式$f_i(\boldsymbol{\boldsymbol{x}})\le 0$称为不等式约束, 方程组$h_i(\boldsymbol{\boldsymbol{x}})=0$称为等式约束. 如果没有约束, 我们称问题(1)为无约束优化问题.

### 1.2. 可行集
对于目标和所有约束函数有定义的点的集合
$$
\mathcal{D} = \bigcap\limits_{i=0}^{m} \mathrm{dom} f_i\cap \bigcap\limits_{i=1}^{p} \mathrm{dom} h_i
$$
称为优化问题(1)的定义域. 当点$\boldsymbol{\boldsymbol{x}}\in \mathcal{D}$满足约束$f_i(\boldsymbol{\boldsymbol{x}})\le 0$, $i=1,2,\cdots,m$和$h_i(\boldsymbol{\boldsymbol{x}})=0$, $i=1,2,\cdots, p$时, 称$\boldsymbol{\boldsymbol{x}}$是可行点. 可行点的集合称为可行集

### 1.3. 最优集
问题 (1) 的最优值 $p^{\star}$ 定义为
$$
p^{\star}=\inf \left\{f_0(\boldsymbol{x}) \mid f_i(\boldsymbol{x}) \leqslant 0, i=1, \cdots, m, h_i(\boldsymbol{x})=0, i=1, \cdots, p\right\} .
$$
我们允许 $p^{\star}$ 取值为 $\pm \infty$ 。如果问题不可行, 我们有 $p^{\star}=\infty$ (按惯例, 空集的下确界为 $\infty$)。如果存在可行解 $x_k$ 满足: 当 $k \rightarrow \infty$ 时, $f_0\left(x_k\right) \rightarrow-\infty$, 那么, $p^{\star}=-\infty$ 并且我们称问题 (1)无下界. 

如果 $\boldsymbol{x}^{\star}$ 是可行的并且 $f_0\left(\boldsymbol{x}^{\star}\right)=p^{\star}$, 我们称 $\boldsymbol{x}^{\star}$ 为最优点. 所有最优解的集合称为最优集, 记为
$$
X_{\mathrm{opt}}=\left\{\boldsymbol{x} \mid f_i(\boldsymbol{x}) \leqslant 0, i=1, \cdots, m, h_i(\boldsymbol{x})=0, i=1, \cdots, p, f_0(\boldsymbol{x})=p^{\star}\right\}
$$

### 1.4. $\varepsilon$-次优集
满足 $f_0(\boldsymbol{x}) \leqslant p^{\star}+\varepsilon$ (其中 $\varepsilon>0$ ) 的可行解 $\boldsymbol{x}$ 称为 $\varepsilon$-次优。所有 $\varepsilon$-次优解的集合称为问题 (1) 的 $\varepsilon$-次优集.

### 1.5. 局部最优
我们称可行解 $\boldsymbol{x}$ 为局部最优, 如果存在 $R>0$ 使得
$$
f_0(\boldsymbol{x})=\inf \left\{f_0(\boldsymbol{z}) \mid f_i(\boldsymbol{z}) \leqslant 0, i=1, \cdots, m,h_i(\boldsymbol{z})=0, i=1, \cdots, p,\|\boldsymbol{z}-\boldsymbol{x}\|_2 \leqslant R\right\},
$$
或换言之, $\boldsymbol{x}$ 是关于 $\boldsymbol{z}$ 的优化问题
$$
\begin{array}{ll}
\operatorname{minimize} & f_0(\boldsymbol{z}) \\
\text { subject to } & f_i(\boldsymbol{z}) \leqslant 0, \quad i=1, \cdots, m \\
& h_i(\boldsymbol{z})=0, \quad i=1, \cdots, p \\
& \|\boldsymbol{z}-\boldsymbol{x}\|_2 \leqslant R
\end{array}
$$
的解

## 2. 等价问题
### 2.1. 变量替换
设 $\phi: \mathbb{R}^n \rightarrow \mathbb{R}^n$ 是一一映射, 其象包含了问题的定义域 $\mathcal{D}$, 即 $\phi(\operatorname{dom} \phi) \supseteq \mathcal{D}$. 定义函数 $\tilde{f}_i$ 和 $\tilde{h}_i$ 为
$$
\tilde{f}_i(\boldsymbol{z})=f_i(\phi(\boldsymbol{z})), \quad i=0, \cdots, m, \quad \tilde{h}_i(\boldsymbol{z})=h_i(\phi(\boldsymbol{z})), \quad i=1, \cdots, p 
$$
下面考虑关于 $\boldsymbol{z}$ 的问题
$$
\begin{array}{ll}
\operatorname{minimize} & \tilde{f}_0(\boldsymbol{z}) \\
\text { subject to } & \tilde{f}_i(\boldsymbol{z}) \leqslant 0, \quad i=1, \cdots, m \\
& \tilde{h}_i(\boldsymbol{z})=0, \quad i=1, \cdots, p,
\end{array} \tag{2}
$$
我们称标准形式问题 (1) 和问题 (2) 通过变量变换或变量代换 $\boldsymbol{x}=\phi(\boldsymbol{z})$ 所联系. 

### 2.2. 目标函数和约束函数
设 $\psi_0: \mathbb{R} \rightarrow \mathbb{R}$ 单增; $\psi_1, \cdots, \psi_m: \mathbb{R} \rightarrow \mathbb{R}$ 满足: 当且仅当 $u \leqslant 0$ 时 $\psi_i(u) \leqslant 0$; $\psi_{m+1}, \cdots, \psi_{m+p}: \mathbb{R} \rightarrow \mathbb{R}$ 满足: 当且仅当 $u=0$ 时 $\psi_i(u)=0$ 。我们定义函数 $\tilde{f}_i$ 和 $\tilde{h}_i$ 为复合函数
$$
\tilde{f}_i(\boldsymbol{x})=\psi_i\left(f_i(\boldsymbol{x})\right), \quad i=0, \cdots, m, \quad \tilde{h}_i(\boldsymbol{x})=\psi_{m+i}\left(h_i(\boldsymbol{x})\right), \quad i=1, \cdots, p 
$$
显然, 问题
$$
\begin{array}{ll}
\operatorname{minimize} & \tilde{f}_0(\boldsymbol{x}) \\
\text { subject to } & \tilde{f}_i(\boldsymbol{x}) \leqslant 0, \quad i=1, \cdots, m \\
& \tilde{h}_i(\boldsymbol{x})=0, \quad i=1, \cdots, p
\end{array}
$$
与标准形式(1)等价. 事实上, 其可行集相同, 最优解也相同. 

### 2.3. 松弛变量
通过观察可以得到一个简单的变换, 即 $f_i(\boldsymbol{x}) \leqslant 0$ 等价于存在一个 $s_i \geqslant 0$ 满足 $f_i(\boldsymbol{x})+s_i=0$ 。 利用这个变换, 我们可以得到问题
$$
\begin{array}{ll}
\operatorname{minimize} & f_0(\boldsymbol{x}) \\
\text { subject to } & s_i \geqslant 0, \quad i=1, \cdots, m \\
& f_i(\boldsymbol{x})+s_i=0, \quad i=1, \cdots, m \\
& h_i(\boldsymbol{x})=0, \quad i=1, \cdots, p
\end{array}
$$
新的变量$s_i$称为对应原不等式约束$f_i(\boldsymbol{x})\le 0$的松弛变量. 

### 2.4. 消除等式约束
如果我们可以用一些参数$\boldsymbol{z}\in \mathbb{R}^k$来显式参数化等式约束
$$
h_i(\boldsymbol{x}) = 0, \quad i=1, \cdots, p
$$
的解, 那么我们可以从原问题中消除等式约束. 例如, 假设$\phi: \mathbb{R}^k\to \mathbb{R}^n$是使得$\boldsymbol{x}$满足$h_i(\boldsymbol{x}) = 0, \quad i=1, \cdots, p$等价于存在某些$\boldsymbol{z}\in\mathbb{R}^k$使得$\boldsymbol{x} = \phi(\boldsymbol{z})$的函数. 那么, 优化问题
$$
\begin{array}{ll}
\operatorname{minimize} & \tilde{f}_0(\boldsymbol{z})=f_0(\phi(\boldsymbol{z})) \\
\text { subject to } & \tilde{f}_i(\boldsymbol{z})=f_i(\phi(\boldsymbol{z})) \leqslant 0, \quad i=1, \cdots, m
\end{array}
$$
与原问题(1)等价. 

当等式约束是线性的时候, 假设$A\boldsymbol{x} = \boldsymbol{b}$有解. 令$\boldsymbol{x}_0$表示等式约束的任意可行解, 令$F\in \mathbb{R}^{n\times k}$为满足$\mathrm{col}(F) = \mathcal{N}(A)$的矩阵, 那么线性方程$A\boldsymbol{x} = \boldsymbol{b}$的通解可以表示为$F\boldsymbol{z}+ \boldsymbol{x}_0$, 其中$\boldsymbol{z}\in \mathbb{R}^k$. 将$\boldsymbol{x} = F\boldsymbol{z}+\boldsymbol{x}_0$带入原问题可以得到关于$\boldsymbol{z}$的问题
$$
\begin{array}{ll}
\operatorname{minimize} & f_0\left(F \boldsymbol{z}+\boldsymbol{x}_0\right) \\
\text { subject to } & f_i\left(F \boldsymbol{z}+\boldsymbol{x}_0\right) \leqslant 0, \quad i=1, \cdots, m
\end{array}
$$

### 2.5. Epigraph形式
标准问题(1)的epigraph形式为
$$
\begin{array}{ll}
\operatorname{minimize} & t \\
\text { subject to } & f_0(\boldsymbol{x})-t \leqslant 0 \\
& f_i(\boldsymbol{x}) \leqslant 0, \quad i=1, \cdots, m \\
& h_i(\boldsymbol{x})=0, \quad i=1, \cdots, p,
\end{array}
$$
其优化变量为$\boldsymbol{x}\in \mathbb{R}^n$和$t\in \mathbb{R}$, 容易看出这个问题和原问题是等价的.


## 3. 凸优化
### 3.1. 标准形式的凸优化问题
凸优化问题是形如
$$
\begin{array}{ll}
\operatorname{minimize} & f_0(\boldsymbol{x}) \\
\text { subject to } & f_i(\boldsymbol{x}) \leqslant 0, \quad i=1, \cdots, m \\
& \boldsymbol{a}_i^{\top} \boldsymbol{x}=b_i, \quad i=1, \cdots, p
\end{array} \tag{3}
$$
的问题, 其中$f_0, f_1, \cdots, f_m$为凸函数. 对比问题(3)和一般的标准形式问题(1), 凸优化问题有三个附加的要求
1. 目标函数必须是凸的
2. 不等式约束函数必须是凸的
3. 等式约束函数$h_i(\boldsymbol{x}) = \boldsymbol{a}_i^{\top}\boldsymbol{x} - \boldsymbol{b}_i$必须是仿射的. 

凸优化问题的可行集是凸的, 因为它是问题定义域$\mathcal{D} = \bigcap\limits_{i=0}^m \mathrm{dom} f_i$, $m$个凸的下水平集$\{\boldsymbol{x}\mid f_i(\boldsymbol{x})\le 0\}$以及$p$个超平面$\{\boldsymbol{x}\mid \boldsymbol{a}^{\top}_i\boldsymbol{x} = \boldsymbol{b}_i\}$的交集. 因此, 在一个凸优化问题中, 我们是在一个凸集上极小化一个凸的目标函数. 

### 3.2. 局部最优解和全局最优解
凸优化问题的一个基础性质是其任意局部最优解也是(全局)最优解. 
___
##### Proof
假设$\boldsymbol{x}$是凸优化问题的局部最优解, 即$\boldsymbol{x}$是可行的并且对于某个$R>0$, 有
$$
f_0(\boldsymbol{x}) = \inf\{f_0(\boldsymbol{z})\mid \boldsymbol{z} \text{ is feasible},\ \|\boldsymbol{z} - \boldsymbol{x}\|_2\le R\}
$$
现在假设$\boldsymbol{x}$不是全局最优解, 即存在一个可行的$\boldsymbol{y}$使得$f_0(\boldsymbol{y}) < f_0(\boldsymbol{x})$. 考虑
$$
\boldsymbol{z} = (1- \theta)\boldsymbol{x} + \theta \boldsymbol{y}, \quad \theta = \dfrac{R}{2\|\boldsymbol{y} - \boldsymbol{x}\|_2}
$$
给出的点$\boldsymbol{z}$, 我们有$\|\boldsymbol{z} - \boldsymbol{x}\|_2 = \dfrac{R}{2}<R$. 根据可行集的凸性, $\boldsymbol{z}$是可行的. 根据$f_0$的凸性, 我们有
$$
f_0(\boldsymbol{z}) \le (1- \theta) f_0(\boldsymbol{x}) + \theta f_0(\boldsymbol{y}) < f_0(\boldsymbol{x})
$$
这与$\boldsymbol{x}$是局部最优解矛盾. 因此, $\boldsymbol{x}$是全局最优解.
#####
___

### 3.3. 可微函数$f_0$的最优性准则
设凸优化问题的目标函数$f_0$是可微的, 对于所有的$\boldsymbol{x}, \boldsymbol{y}\in \mathrm{dom}f_0$有
$$
f_0(\boldsymbol{y}) \ge f_0(\boldsymbol{x}) + \nabla f_0(\boldsymbol{x})^{\top}(\boldsymbol{y} - \boldsymbol{x})
$$
令$X$表示其可行集, 即
$$
X = \{\boldsymbol{x}\mid f_i(\boldsymbol{x})\le 0, i=1,2,\cdots, m; h_i(\boldsymbol{x}) = 0, i=1,2,\cdots, p\}
$$
那么, $\boldsymbol{x}$是最优解, 当且仅当$\boldsymbol{x}\in X$且
$$
\nabla f_0(\boldsymbol{x})^{\top}(\boldsymbol{y} - \boldsymbol{x}) \ge 0, \quad \forall \boldsymbol{y}\in X \tag{4}
$$
___
##### Proof
首先假设$\boldsymbol{x}\in X$满足
$$
\nabla f_0(\boldsymbol{x})^{\top}(\boldsymbol{y} - \boldsymbol{x}) \ge 0, \quad \forall \boldsymbol{y}\in X
$$
那么显然有$f_0(\boldsymbol{y})\ge f_0(\boldsymbol{x})$. 这表明$\boldsymbol{x}$是问题(1)的一个最优解. 

反之, 假设$\boldsymbol{x}$是最优解但条件(4)不成立, 即对于某些$\boldsymbol{y}\in X$, 有
$$
\nabla f_0(\boldsymbol{x})^{\top}(\boldsymbol{y} - \boldsymbol{x}) < 0
$$
考虑$\boldsymbol{z}(t) = t\boldsymbol{y}+(1-t)\boldsymbol{x}$, 其中$t\in [0, 1]$为参数. 因为$\boldsymbol{z}(t)$在$\boldsymbol{x}$和$\boldsymbol{y}$之间的线段上, 而可行集是凸集, 因此$z(t)$可行. 注意到
$$
\dfrac{\mathrm{d}}{\mathrm{d} t}f_0(\boldsymbol{z}(t))\ \Bigg|_{t=0} = \nabla f_0(\boldsymbol{x})^{\top}(\boldsymbol{y} - \boldsymbol{x}) < 0
$$
因此, 对于小正数, 我们有
$$
f_0(\boldsymbol{z}(t)) < f_0(\boldsymbol{x})
$$
#####
___
#### 3.3.1. 无约束问题的最优性准则
对于无约束优化问题, 条件(4)可以简化为一个众所周知的$\boldsymbol{x}$是最优解的充分必要条件
$$
\nabla f_0(\boldsymbol{x}) = 0
$$

#### 3.3.2. 只含等式约束的问题
考虑只含等式约束而没有不等式约束的问题, 即
$$
\begin{array}{ll}
\operatorname{minimize} & f_0(\boldsymbol{x}) \\
\text { subject to } & A \boldsymbol{x}=\boldsymbol{b},
\end{array}
$$
可行解$\boldsymbol{x}$的最优性条件为, 对于任意满足$A\boldsymbol{y} = \boldsymbol{b}$的$\boldsymbol{y}$, 记$\boldsymbol{y} = \boldsymbol{x} + \boldsymbol{v}$, 其中$\boldsymbol{v}\in \mathcal{N}(A)$. 因此, 对于任意的$\boldsymbol{v}\in \mathcal{N}(A)$, 我们有$\nabla f_0(\boldsymbol{x})^{\top}\boldsymbol{v} = 0$. 换言之
$$
\nabla f_0(\boldsymbol{x}) \perp \mathcal{N}(A)
$$
因为$\mathcal{N}(A) = \mathrm{col}(A^{\top})$. 因此最优性条件可以表示为$\nabla f_0(\boldsymbol{x})\in \mathrm{col}(A^{\top})$, 即存在$\boldsymbol{\nu}\in \mathbb{R}^p$使得
$$
\nabla f_0(\boldsymbol{x}) + A^{\top}\boldsymbol{\nu} = 0
$$
这是经典的Lagrange乘子法的最优性条件.

#### 3.3.3. 非负象限的极小化
考虑非负象限的极小化问题
$$
\begin{array}{ll}
\operatorname{minimize} & f_0(\boldsymbol{x}) \\
\text { subject to } & \boldsymbol{x} \succeq 0
\end{array}
$$
于是最优化条件为
$$
\boldsymbol{x} \succeq 0, \quad \nabla f_0(\boldsymbol{x})^{\top}(\boldsymbol{y} - \boldsymbol{x}) \ge 0, \forall \boldsymbol{y}\succeq 0
$$
显然这个条件可以被简化为
$$
\boldsymbol{x} \succeq 0, \quad  - \nabla f_0(\boldsymbol{x})^{\top}\boldsymbol{x} \ge 0, \quad \nabla f_0(\boldsymbol{x}) \succeq 0
$$
这样就得到了互补性的最优化条件
$$
\boldsymbol{x} \succeq 0, \quad \nabla f_0(\boldsymbol{x}) \succeq 0, \quad x_i\left(\nabla f_0(\boldsymbol{x})\right)_i = 0, \quad i=1,2,\cdots, n
$$

### 3.4. 拟凸优化