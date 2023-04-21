## 1. 数据的向量表示
### 1.1. 多元观测值的矩阵表示
若获得了 $n$ 个观测值, 每个观察值有$p$个特征, 我们可以把全体数据集放在一个 $n \times p$ 的阵列中
$$
X=\left(\begin{array}{cccc}
x_{11} & x_{12} & \cdots & x_{1 p} \\
x_{21} & x_{22} & \cdots & x_{2 p} \\
\vdots & \vdots & & \vdots \\
x_{n 1} & x_{n 2} & \cdots & x_{n p}
\end{array}\right)=\left(\begin{array}{c}
\boldsymbol{x}_1^{\prime} \\
\boldsymbol{x}_2^{\prime} \\
\vdots \\
\boldsymbol{x}_n^{\prime}
\end{array}\right)
$$
其中 $\boldsymbol{x}_j^{\prime}$ 表示第 $j$ 个观测值. 我们同样可以把数据看做 $n$ 维空间中的 $p$ 个特征向量来构造, 我们令
$$
X=\left(\begin{array}{cccc}
x_{11} & x_{12} & \cdots & x_{1 p} \\
x_{21} & x_{22} & \cdots & x_{2 p} \\
\vdots & \vdots & & \vdots \\
x_{n 1} & x_{n 2} & \cdots & x_{n p}
\end{array}\right)=\left(\boldsymbol{f}_1, \boldsymbol{f}_2, \cdots, \boldsymbol{f}_p\right)
$$
则 $\boldsymbol{f}_i$ 是第 $i$ 个特征的 $n$ 个测量结果

### 1.2. 样本均值的向量表示
样本均值可以被矩阵表示为
$$
\overline{\boldsymbol{x}}=\left(\begin{array}{c}
\bar{x}_1 \\
\bar{x}_2 \\
\vdots \\
\bar{x}_p
\end{array}\right)=\frac{1}{n}\left(\begin{array}{cccc}
x_{11} & x_{21} & \cdots & x_{n 1} \\
x_{12} & x_{22} & \cdots & x_{n 2} \\
\vdots & \vdots & & \vdots \\
x_{1 p} & x_{2 p} & \cdots & x_{n p}
\end{array}\right)\left(\begin{array}{c}
1 \\
1 \\
\vdots \\
1
\end{array}\right)
$$
通常可以被写为
$$
\bar{\boldsymbol{x}}=\frac{1}{n} X^{\top} \boldsymbol{1}
$$
当需要将均值向量扩充为均值矩阵时, 我们有
$$
\boldsymbol{1} \overline{\boldsymbol{x}}^{\prime}=\frac{1}{n} \boldsymbol{1} \boldsymbol{1}^{\prime} X=\left(\begin{array}{cccc}
\bar{x}_1 & \bar{x}_2 & \cdots & \bar{x}_p \\
\bar{x}_1 & \bar{x}_2 & \cdots & \bar{x}_p \\
\vdots & \vdots & & \vdots \\
\bar{x}_1 & \bar{x}_2 & \cdots & \bar{x}_p
\end{array}\right)
$$

### 1.3. 样本方差表示
从 $X$ 减去 $\boldsymbol{1} \bar{\boldsymbol{x}}^{\prime}$, 产生 $n \times p$ 偏差 (剩余) 矩阵
$$
X-\frac{1}{n} \boldsymbol{1} \boldsymbol{1}^{\prime} X=\left(\begin{array}{cccc}
x_{11}-\bar{x}_1 & x_{12}-\bar{x}_2 & \cdots & x_{1 p}-\bar{x}_p \\
x_{21}-\bar{x}_1 & x_{22}-\bar{x}_2 & \cdots & x_{2 p}-\bar{x}_p \\
\vdots & \vdots & & \vdots \\
x_{n 1}-\bar{x}_1 & x_{n 2}-\bar{x}_2 & \cdots & x_{n p}-\bar{x}_p
\end{array}\right)
$$
于是不难有 
$$
(n-1) S=\left(X-\frac{1}{n} \boldsymbol{11}^{\prime} X\right)^{\prime}\left(X-\frac{1}{n} \boldsymbol{11}^{\prime} X\right)=X^{\prime}\left(I-\frac{1}{n} \boldsymbol{11}^{\prime}\right) X
$$
也即有 
$$
S=\frac{1}{n-1} X^{\prime}\left(I-\frac{1}{n} \boldsymbol{11}^{\prime}\right) X
$$

## 2. 样本统计量
### 2.1. Kurtosis(尾部风险)
一般地, 我们可以用 kurtosis(峰度) 来度量资产的尾部风险. 标准正态分布的 kurtosis 为 3 . 如果 kurtosis 大于 3 , 我们一般认为这是肥尾分布, 其尾部风险通常较大. 而如果 kurtosis 小于 3 , 则可以认为是薄尾分布, 尾部风险比较小. $t$ 分布的峰度为 $3+\dfrac{6}{\nu-4}$,  是肥尾分布

### 2.2. 矩检验
在正态性假定下, 我们可以对三阶矩和四阶矩做如下的检验
1. 对称性检验(偏度检验): 利用 $S^*=\dfrac{\hat{S}(x)}{\sqrt{6 / T}} \sim N(0,1)$ 进行检验
2. 肥尾检验 (峰度检验): 利用 $K^*=\dfrac{\hat{K}(x)-3}{\sqrt{24 / T}} \sim N(0,1)$ 进行检验

### 2.3. 广义样本方差
有时, 希望对用 $S$ 表示的无偏样本方差-协方差矩阵能给定一个数值, 我们选择这一数值为$S$的行列式 $|S|$, 该行列式称为广义样本方差. 事实上, 广义样本方差具有良好的几何性质.
1. $n$ 维空间上的几何意义: 我们记由 $p$ 个偏差向量 $\boldsymbol{d}_1, \boldsymbol{d}_2, \cdots, \boldsymbol{d}_p$ 所产生的 $n$ 维几何体的体积为 $V$, 则 $|S|=\dfrac{1}{(n-1)^p} V^2$
2.  $p$ 维空间上的几何意义: 我们可以在 $p$ 维空间上考虑统计距离的测度. 距离 $\bar{\boldsymbol{x}}$ 为常数距离 $c$ 的点的坐标满足
    $$
    (\boldsymbol{x}-\overline{\boldsymbol{x}})^{\prime} S^{-1}(\boldsymbol{x}-\overline{\boldsymbol{x}})=c^2
    $$
    不难证明这个超椭球的体积为
    $$
    V\left\{\boldsymbol{x}:(\boldsymbol{x}-\overline{\boldsymbol{x}})^{\prime} S^{-1}(\boldsymbol{x}-\overline{\boldsymbol{x}}) \leq c^2\right\}=k_p \sqrt{|S| c^p}
    $$