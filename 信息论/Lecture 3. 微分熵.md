## 1. 微分熵
### 1.1. 微分熵的定义
一个以$f(x)$为密度函数的连续随机变量$X$的微分熵(differential entropy) $h(X)$定义为
$$
h(X)=-\int_{S}f(x)\log f(x)\mathrm{d}x
$$
其中$S$为这个随机变量的支撑集. 与离散情形一样, 微分熵仅依赖于随机变量的概率密度, 因此, 有时候我们将微分熵写为$h(f)$.

微分熵在很多情况下并不存在, 即使存在也不一定为正, 和离散熵不同, 微分熵并不具有明确的代数意义. 

### 1.2. 微分熵和离散熵的关系
考虑一个密度函数为$f(x)$的随机变量$X$, 假定将$X$的定义域等分成长度为$\Delta$的若干个小区间, 考虑量化后的随机变量$X^{\Delta}$, 其定义为
$$
X^{\Delta}=x_i,\quad i\Delta \le X< (i+1)\Delta
$$
如果随机变量$X$的密度函数$f(x)$是黎曼可积的, 那么
$$\lim_{\Delta\to 0}H(X^{\Delta})+\log \Delta = h(f)$$
于是, 连续随机变量$X$经过$n$比特量化处理(此时分割的小区间长度为$\dfrac{1}{2^n}$)后的熵大约为$h(X)+n$.


### 1.3. 联合微分熵与条件微分熵
联合密度函数为$f(x_1, x_2, \cdots, x_n)$的一组随机变量$X_1, X_2, \cdots, X_n$的联合微分熵定义为
$$
h(X_1, X_2, \cdots, X_n) = -\int f(\boldsymbol{x})\log f(\boldsymbol{x})\mathrm{d}\boldsymbol{x}
$$

如果$(\boldsymbol{x}, \boldsymbol{y})$的联合密度函数为$f(\boldsymbol{x}, \boldsymbol{y})$, 定义条件微分熵为
$$
h(\boldsymbol{x}\mid \boldsymbol{y}) = -\int f(\boldsymbol{x}, \boldsymbol{y})\log f(\boldsymbol{x}\mid \boldsymbol{y})\mathrm{d}\boldsymbol{x}\mathrm{d}\boldsymbol{y}
$$


### 1.4. 链式法则与微分熵的独立界
我们有
$$
h(X_1,X_2, \cdots,X_n)=\sum_{i=1}^nh(X_i\mid X_{i-1},\cdots , X_1)\le \sum_{i=1}^nh(X_i)
$$
当且仅当$X_1,X_2, \cdots,X_n$相互独立时等号成立. 

### 1.5. 多元正态分布的微分熵
设$X_1, X_2, \cdots, X_n$服从均值为$\boldsymbol{\mu}$, 协方差为$\Sigma$的多元正态分布, 记为$\boldsymbol{x}\sim \mathcal{N}_n(\boldsymbol{\mu}, \Sigma)$. 则
$$
h\left(\mathcal{N}_n(\boldsymbol{\mu}, \Sigma)\right) = \dfrac{1}{2}\log_2(2\pi e)^n |\Sigma| 
$$
___
##### Proof
设$X_1, X_2, \cdots, X_n$的联合概率密度函数为
$$
f(\boldsymbol{x}) = \dfrac{1}{(\sqrt{2\pi})\sqrt{|\Sigma|}} \exp\left\{-\dfrac{1}{2}(\boldsymbol{x}-\boldsymbol{\mu})^{\top}\Sigma^{-1}(\boldsymbol{x}-\boldsymbol{\mu})\right\}
$$
于是我们有
$$
\begin{aligned}
h(f) & = - \int f(\boldsymbol{x})\left[-\dfrac{1}{2}(\boldsymbol{x}-\boldsymbol{\mu})^{\top}\Sigma^{-1}(\boldsymbol{x}-\boldsymbol{\mu}) - \ln(\sqrt{2\pi})^n \sqrt{|\Sigma|}\right] \mathrm{d}\boldsymbol{x}\\
& = \dfrac{1}{2}\log_2(2\pi e)^n |\Sigma|
\end{aligned}
$$
#####
___



## 2. 相对熵和互信息
### 2.1. 相对熵
两个密度函数$f$和$g$之间的相对熵(KL divergence) $D(f\mid \mid g)$定义为
$$
D(f\mid \mid g) = \int f(x)\log \dfrac{f(x)}{g(x)}\mathrm{d}x
$$
注意到只有当$f$的支撑集包含在$g$的支撑集中时, $D(f\mid \mid g)$是有限的. 


### 2.2. 互信息
联合密度函数为$f(x, y)$的两个随机变量间的互信息$I(X; Y)$定义为
$$
I(X; Y) = \int f(x, y)\log \dfrac{f(x, y)}{f(x)f(y)}\mathrm{d}x \mathrm{d}y
$$
根据定义, 显然有
$$
I(X; Y) = h(X) - h(X\mid Y) = h(Y) - h(Y\mid X) = h(X) + h(Y) - h(X, Y)
$$
以及
$$
I(X; Y) = D(f(x, y)\mid \mid f(x)f(y))
$$

### 2.3. 值域分割的互信息定义
设$\mathcal{X}$是随机变量$X$的值域, $\mathcal{P}$为$\mathcal{X}$的一个分割. $X$关于$\mathcal{P}$的量化(记为$[X]_{\mathcal{P}}$)是定义如下的离散随机变量
$$
\mathbb{P}([X]_{\mathcal{P}}=i)=\mathbb{P}(X\in P_i)=\int _{P_i}\mathrm{d}F(x)
$$
任意随机变量$X,Y$间的互信息如下
$$
I(X;Y)=\sup_{\mathcal{P}, \mathcal{Q}}I([X]_{\mathcal{P}}, [Y]_{\mathcal{Q}})
$$
其上确界遍历所有可能的有限分割$\mathcal{P}$和$\mathcal{Q}$. 这样互信息的定义可以覆盖所有的分布函数, 不论是离散, 连续还是奇异的


## 3. 微分熵的性质
### 1.6. 给定协方差矩阵的最大熵
设随机向量$\boldsymbol{x}\in \mathbb{R}^n$的均值为$\boldsymbol{0}$, 协方差矩阵为$\Sigma$, 则
$$
h(\boldsymbol{x}) \le \dfrac{1}{2}\log_2(2\pi e)^n |\Sigma|
$$
当且仅当$\boldsymbol{x}\sim \mathcal{N}_n(\boldsymbol{\mu}, \Sigma)$等号成立. 
