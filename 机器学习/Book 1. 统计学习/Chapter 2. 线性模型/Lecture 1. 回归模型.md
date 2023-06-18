## 1. 线性回归模型
### 1.1. 多元线性回归
对于一般的数据集 $D$, 样本由 $d$ 个属性描述, 我们试图学得
$$
f\left(\boldsymbol{x}_i\right)=\boldsymbol{w}^{\top} \boldsymbol{x}_i+b, \text { s.t. } f\left(\boldsymbol{x}_i\right) \simeq y_i
$$
这称为 “多元线性回归” (multivariate linear regression).

### 1.2. 多元线性回归的最小二乘估计
可以使用最小二乘法来对 $\boldsymbol{w}$ 和 $b$ 进行估计. 用 $\widehat{\boldsymbol{w}}=\left(\begin{array}{l}\boldsymbol{w} \\ b\end{array}\right)$ 来表示参数, 将数据集 $D$ 表示为一个 $m \times(d+1)$ 大小的矩阵 $X$, 其中每行对应于一个实例. 
$$
X =\left(\begin{array}{ccccc}
x_{11} & x_{12} & \cdots & x_{1 d} & 1 \\
x_{21} & x_{22} & \cdots & x_{2 d} & 1 \\
\vdots & \vdots & & \vdots & \vdots \\
x_{m 1} & x_{m 2} & \cdots & x_{m d} & 1
\end{array}\right)=\left(\begin{array}{cc}
\boldsymbol{x}_1^{\top} & 1 \\
\boldsymbol{x}_2^{\top} & 1 \\
\vdots & \vdots \\
\boldsymbol{x}_m^{\top} & 1
\end{array}\right)
$$
将标签写成向量形式 $\boldsymbol{y}=\left(y_1, y_2, \cdots, y_m\right)^{\top}$, 则有
$$
\widehat{\boldsymbol{w}}^*=\arg \min _{\widehat{\boldsymbol{w}}}(\boldsymbol{y}-X \widehat{\boldsymbol{w}})^{\top}(\boldsymbol{y}-X \widehat{\boldsymbol{w}})
$$
令 $E_{\widehat{\boldsymbol{w}}}=(\boldsymbol{y}-X \widehat{\boldsymbol{w}})^{\top}(\boldsymbol{y}-X \widehat{\boldsymbol{w}})$, 对 $\widehat{\boldsymbol{w}}$ 求导可得
$$
\frac{\partial E_{\widehat{\boldsymbol{w}}}}{\partial \widehat{\boldsymbol{w}}}=2 X^{\top}(X \widehat{\boldsymbol{w}}-\boldsymbol{y})
$$
假定 $X^{\top} X$ 为满秩矩阵 (full-rank matrix) 或正定矩阵 (positive definite matrix). 令导数式为$0$可以得到
$$
\widehat{\boldsymbol{w}}^*=\left(X^{\top} X\right)^{-1} X^{\top} \boldsymbol{y}
$$
此时最终学得的线性回归模型为
$$
f\left(\boldsymbol{x}_i\right)=\boldsymbol{x}_i^{\top}\left(X^{\top} X\right)^{-1} X^{\top} \boldsymbol{y}
$$
现实任务中 $X^{\top} X$ 往往不是满秩矩阵. 例如在许多任务中我们会遇到大量的变量, 其数目甚至超过样例数, 导致 $X$ 的列数多于行数, 此时 $X^{\top} X$ 显然不满秩, 这意味着广义最小二乘解 $\widehat{\boldsymbol{w}}$ 不唯一.

### 1.3. 正则化项(regularization)
不失一般性, 我们可以将线性回归的正则化写成
$$
L(\boldsymbol{w})=\frac{1}{2} \sum_{n=1}^N\left(y_n-\boldsymbol{w}^{\top} \boldsymbol{x}^{(n)}\right)^2+\lambda f(w)
$$
线性回归有下面两种常用的正则化方式, 我们可以用 $k$ 折交叉验证来选择模型的超参数.
1. Ridge 回归, 也称 $L_2$ 正则化
    $$
    L(\boldsymbol{w})=\frac{1}{2} \sum_{n=1}^N\left(y_n-\boldsymbol{w}^{\top} \boldsymbol{x}^{(n)}\right)^2+\lambda\|\boldsymbol{w}\|_2
    $$
2. Lasso 回归, 也称 $L_1$ 正则化
    $$
    L(\boldsymbol{w})=\frac{1}{2} \sum_{n=1}^N\left(y_n-\boldsymbol{w}^{\top}  \boldsymbol{x}^{(n)}\right)^2+\lambda\|\boldsymbol{w}\|_1
    $$
    $L_1$ 正则化具有稀疏化的效果

### 1.4. 常见损失函数
除了均方误差以外, 我们还有很多其他的评估函数. 我们往往根据模型的性质选择不同的损失函数, 一些最常用的评估函数列举如下
1. $0 / 1$ 评估函数: $\ell^{0 / 1}(y, \hat{y})=\mathbb{I}_{y \hat{y} \leq 0}$
2. Hinge 评估函数: $\ell^{(\mathrm{hin})}(y, \hat{y})=\max \{0,1-y \hat{y}\}$
3. Logistic 评估函数: $\ell^{(\log )}(y, \hat{y})=\log (1+\exp [-y \hat{y}])$
4. Exponential 评估函数: $\ell^{(\exp )}(y, \hat{y})=\exp [-y \hat{y}]$
5. Squared 评估函数: $\ell^{(\mathrm{sqr})}(y, \hat{y})=(y-\hat{y})^2$

### 1.5. 广义线性模型(generalized linear model)
考虑单调可微函数$g(\cdot)$, 令
$$
y = g^{-1}(\boldsymbol{w}^{\top} \boldsymbol{x} + b)
$$
这样的模型称为“广义线性模型”, 其中函数$g(\cdot)$称为联系函数(link function)

## 2. Logistic 回归
### 2.1. Logistic 函数
对数几率函数(logistic function)是一种常用的Sigmoid函数, 它的形式为
$$
y=\dfrac{1}{1+e^{-z}}
$$
它将$z$值转化为一个接近$0$或$1$的$y$值, 并且其输出值在$z=0$附近变化最陡
$$
\mathbb{P}(y=1)=\frac{1}{1+e^{-\left(\boldsymbol{w}^{\top} \boldsymbol{x}+b\right)}} \Longrightarrow \ln \frac{\mathbb{P}(y=1)}{\mathbb{P}(y=0)}=\boldsymbol{w}^{\top} \boldsymbol{x}+b
$$
我们把 $\ln \dfrac{\mathbb{P}(y=1)}{\mathbb{P}(y=0)}$ 称为对数几率 (log odds, 亦称 logit).

可以将 logistic 函数经过适当的推广得到 softmax 函数, softmax 函数可以用作神经网络的多分类问题
$$
P\left(y=c_i\right)=\frac{e^{-\boldsymbol{w}_i^{\top} \boldsymbol{x}}}{\sum\limits_{k=1}^K e^{-\boldsymbol{w}_k^{\top} \boldsymbol{x}}} \quad y \in\left\{c_1, c_2, \cdots, c_K\right\}
$$

### 2.2. Logistic 回归的极大似然估计
给定数据集 $\left\{\left(\boldsymbol{x}_i, y_i\right)\right\}_{i=1}^m$, Logistic 回归模型最大化 “对数似然” (log-likelihood)
$$
\ell(\boldsymbol{w}, b)=\sum_{i=1}^m \ln p\left(y_i \mid \boldsymbol{x}_i ; \boldsymbol{w}, b\right)
$$
即令每个样本属于其真实标记的概率越大越好. 令 $\boldsymbol{\beta}=\left(\begin{array}{c}\boldsymbol{w} \\ b\end{array}\right), \widehat{\boldsymbol{x}}=\left(\begin{array}{c}\boldsymbol{x} \\ 1\end{array}\right)$. 则 $\boldsymbol{w}^{\top} \boldsymbol{x}+b$ 可以简写为 $\boldsymbol{\beta}^{\top} \widehat{\boldsymbol{x}}$, 再令
$$
\begin{gathered}
p_1(\widehat{\boldsymbol{x}} ; \boldsymbol{\beta})=\mathbb{P}(y=1 \mid \widehat{\boldsymbol{x}} ;  \hat{\boldsymbol{\beta}}) \\
p_0(\widehat{\boldsymbol{x}} ; \boldsymbol{\beta})=\mathbb{P}(y=0 \mid \widehat{\boldsymbol{x}} ; \hat{\boldsymbol{\beta}})=1-p_1(\widehat{\boldsymbol{x}} ; \boldsymbol{\beta})
\end{gathered}
$$
则似然项可以写成
$$
p\left(y_i \mid \boldsymbol{x}_i ; \boldsymbol{w}, b\right)=y_i p_1(\widehat{\boldsymbol{x}} ; \boldsymbol{\beta})+\left(1-y_i\right) p_0(\widehat{\boldsymbol{x}} ; \boldsymbol{\beta})
$$
于是, 最大化 $\ell(\boldsymbol{w}, b)$ 等价于最小化
$$
\min _{\boldsymbol{\beta}} \ell(\boldsymbol{\beta})=\sum_{i=1}^m\left(-y_i \boldsymbol{\beta}^{\top} \hat{\boldsymbol{x}}_i+\ln \left(1+e^{\boldsymbol{\beta}^{\top} \hat{\boldsymbol{x}}_i}\right)\right)
$$

### 2.3. Logistic 回归的梯度下降
因为$\ell(\boldsymbol{\beta})$ 是关于 $\boldsymbol{\beta}$ 的高阶可导连续凸函数, 根据凸优化理论, 经典的数值计算算法如梯度下降法 (gradient descent method), 牛顿法 (Newton method) 都可以求得最优解
$$
\boldsymbol{\beta}^*=\arg \min _{\boldsymbol{\beta}} \ell(\boldsymbol{\beta})
$$
以牛顿法为例, 其第 $t+1$ 轮迭代解的更新公式
$$
\boldsymbol{\beta}^{t+1}=\boldsymbol{\beta}^t-\left(\frac{\partial^2 \ell(\boldsymbol{\beta})}{\partial \boldsymbol{\beta} \partial \boldsymbol{\beta}^{\prime}}\right)^{-1} \frac{\partial \ell(\boldsymbol{\beta})}{\partial \boldsymbol{\beta}}
$$
其中关于 $\boldsymbol{\beta}$ 的一阶二阶导数分别为
$$
\begin{gathered}
\frac{\partial \ell(\boldsymbol{\beta})}{\partial \boldsymbol{\beta}}=-\sum_{i=1}^m \hat{\boldsymbol{x}}_i\left(y_i-p_1(\hat{\boldsymbol{x}} ; \boldsymbol{\beta})\right) \\
\frac{\partial^2 \ell(\boldsymbol{\beta})}{\partial \boldsymbol{\beta} \partial \boldsymbol{\beta}^{\prime}}=\sum_{i=1}^m \hat{\boldsymbol{x}}_i \hat{\boldsymbol{x}}_i^{\top} p_1\left(\hat{\boldsymbol{x}}_i ; \boldsymbol{\beta}\right)\left(1-p_1\left(\hat{\boldsymbol{x}}_i ; \boldsymbol{\beta}\right)\right)
\end{gathered}
$$