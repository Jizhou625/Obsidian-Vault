## 1. 回归模型概述
### 1.1. 总体回归函数和OLS回归线
**总体回归函数**: 总体回归函数(Population Regression Function, PRF) $\mathbb{E}(y\mid \boldsymbol{x}) = \boldsymbol{x}^{\top}\boldsymbol{\beta}$ 是$\boldsymbol{x}$的一个线性函数. 线性意味着$\boldsymbol{x}$的某个分量$x_i$产生一个单位的变化, 将使得$y$的期望改变$\beta_i$. 总体回归函数总是固定而未知的. 

**OLS回归线**: OLS回归线可以被写成 $\hat{y} = \boldsymbol{x}^{\top}\hat{\boldsymbol{\beta}}$的形式, OLS回归线又被称为样本回归函数(Sample Regression Function, SRF), 因为它是总体回归函数 $\mathbb{E}(y\mid \boldsymbol{x}) = \boldsymbol{x}^{\top}\boldsymbol{\beta}$ 的一个样本估计. 

### 1.2. 线性模型与非线性模型
有必要说明线性模型和非线性模型的区别, 考虑以下的两个模型
$$
\begin{aligned} 
    Y_i&=\beta_1+\beta_2 X_i+ \beta_3 X_i^3+u_i \\
Y_i&=\beta_1 e^{\beta_2 X_i}+u_i 
\end{aligned}
$$
其中第一个方程式一个线性回归模型(关于参数$\beta_1, \beta_2, \beta_3$线性), 而第二个方程式是一个非线性模型(指数回归模型). 一般来说, 非线性回归模型的OLS估计没有显式解

### 1.3. 回归模型的OLS估计
OLS的最优化目标是使得残差平方和最小, 也就是说
$$
\min\limits_{\hat{\boldsymbol{\beta}}_{\mathrm{OLS}}} (\boldsymbol{y}-X \hat{\boldsymbol{\beta}}_{\mathrm{OLS}})^{\prime}(\boldsymbol{y}-X\hat{\boldsymbol{\beta}}_{\mathrm{OLS}})
$$
求解可以得到, 参数$\boldsymbol{\beta}$的OLS估计量为
$$
\hat{\boldsymbol{\beta}}_{\mathrm{OLS}} = (X^{\top}X)^{-1}X^{\top}\boldsymbol{y}
$$
设$M\equiv I - X(X^{\top}X)^{-1}X^{\top}$, $M$是一个对称幂等矩阵. 则OLS估计的残差可以写成
$$
\hat{\boldsymbol{u}} = M\boldsymbol{y}
$$
## 2. OLS估计的无偏性和一致性
### 2.1. OLS模型的无偏性假定
1. **线性于参数**: 在总体模型中, 因变量$y$和自变量$\boldsymbol{x}$, 误差项$u$的关系如下
   $$
   y=\boldsymbol{x}^{\top}\boldsymbol{\beta}+u
   $$
2. **随机抽样**: 我们具有一个服从总体模型$y=\boldsymbol{x}^{\top}\boldsymbol{\beta}+u$的随机样本, 其样本容量为$n$. 
   
   ***Note***: 有必要对随机抽样做进一步的说明, 抽样的非随机性主要有两种可能的来源
   - **自变量非随机**: 基于自变量的样本选择(非随机性)一般不会造成估计失效
   - **因变量非随机**: 基于因变量的样本选择(非随机性)一般会造成估计失效

3. **不存在完全共线性**: 在样本中, 自变量之间也不存在严格的线性关系(如果有截距项$\beta_0$, 则看作其对应于一个恒为$1$的自变量)
4. **零条件均值假定**: 给定解释变量的任意值, 误差的期望值都为$0$, 换言之
   $$
   \mathbb{E}\left(u \mid \boldsymbol{x}\right)=0
   $$ 

满足上述4个条件的模型所得到的$\boldsymbol{\beta}$的估计量$\hat{\boldsymbol{\beta}}_{\mathrm{OLS}}$是无偏的. 
___
##### Proof: 
根据线性于参数的条件, 我们可以得到
$$
\hat{\boldsymbol{\beta}}_{\mathrm{OLS}} = (X^{\top}X)^{-1}X^{\top}(X\boldsymbol{\beta} +\boldsymbol{u}) = \boldsymbol{\beta} + (X^{\top}X)^{-1}X^{\top}\boldsymbol{u}
$$
这里, 不完全共线性的条件保证了$(X^{\top}X)^{-1}$是存在的. 再根据零条件均值假定, 我们有
$$
\mathbb{E}\hat{\boldsymbol{\beta}}_{\mathrm{OLS}} = \boldsymbol{\beta}
$$
___
**Note**: 在证明里我们似乎没有用到随机抽样的条件, 这是因为这个条件隐含在了零条件均值假定里. 例如, 考虑总体模型$y = x+u$, 如果我们用$y>0$的条件来筛选样本, 则要求$u>-x$. 当$x=-1$时, 自然地有$u>1$, 这就违背了零条件均值假定.

换句话说, 随机抽样假定保证了样本概率分布 $y_{\mathrm{sample}}\mid \boldsymbol{x}_{\mathrm{sample}}$ 和总体概率分布$y_{\mathrm{total}}\mid \boldsymbol{x}_{\mathrm{total}}$相同. 
#####
___

### 2.2. OLS模型的一致性假定
1. **线性于参数**: 在总体模型中, 因变量$y$和自变量$\boldsymbol{x}$, 误差项$u$的关系如下
   $$
   y=\boldsymbol{x}^{\top}\boldsymbol{\beta}+u
   $$
2. **随机抽样**: 我们具有一个服从总体模型$y=\boldsymbol{x}^{\top}\boldsymbol{\beta}+u$的随机样本, 其样本容量为$n$. 
   
   ***Note***: 有必要对随机抽样做进一步的说明, 抽样的非随机性主要有两种可能的来源
   - **自变量非随机**: 基于自变量的样本选择(非随机性)一般不会造成估计失效
   - **因变量非随机**: 基于因变量的样本选择(非随机性)一般会造成估计失效

3. **不存在完全共线性**: 在样本中, 自变量之间也不存在严格的线性关系(如果有截距项$\beta_0$, 则看作其对应于一个恒为$1$的自变量)
4. **零均值和零相关假定**: $\mathbb{E}(u)=0, \operatorname{Cov}\left(\boldsymbol{x}, u\right)=0$

满足上述4个条件的模型所得到的$\boldsymbol{\beta}$的估计量$\hat{\boldsymbol{\beta}}_{\mathrm{OLS}}$是一致的. 
___
##### Proof: 
 根据线性于参数的条件, 我们可以得到
$$
\hat{\boldsymbol{\beta}}_{\mathrm{OLS}} = (X^{\top}X)^{-1}X^{\top}(X\boldsymbol{\beta} +\boldsymbol{u}) = \boldsymbol{\beta} + (X^{\top}X)^{-1}X^{\top}\boldsymbol{u}
$$
这里, 不完全共线性的条件保证了$(X^{\top}X)^{-1}$是存在的. 设
$$
A = \dfrac{1}{n} X^{\top}X, \quad B = \dfrac{1}{n} X^{\top}\boldsymbol{u}
$$
#####
___

## 2. 拟合优度
### 2.1. 几个平方和的定义
1. 总平方和(Total Sum of Squares, SST): 
   $$
   \mathrm{SST} \equiv \sum_{i=1}^n(y_i - \bar{y})^2
   $$
2. 解释平方和 (Explained Sum of Squares, $\mathrm{SSE}$): 
   $$
   \mathrm{SSE} \equiv \sum_{i=1}^n\left(\widehat{y}_i-\bar{y}\right)^2
   $$ 
3. 残差平方和 (residual sum of squares, SSR): 
   $$
   \mathrm{SSR} \equiv \sum_{i=1}\left(\widehat{y}_i-y\right)^2=\widehat{u}_i^2
   $$

### 2.2. 判定系数(Coefficient of Determination, $R^2$)
判定系数又被称为 R-squared, 被定义为
$$
R^2=\frac{\mathrm{SSE}}{\mathrm{SST}}=1-\frac{\mathrm{SSR}}{\mathrm{SST}}
$$
事实上, $R^2$ 可以写成
$$
R^2=\frac{\operatorname{SSE}}{\mathrm{SST}}=\frac{\hat{\boldsymbol{y}}^{\prime} \hat{\boldsymbol{y}}-\dfrac{1}{n}\left(\hat{\boldsymbol{y}}^{\prime} \mathbf{1}\right)^2}{\boldsymbol{y}^{\prime} \boldsymbol{y}-\dfrac{1}{n}\left(\boldsymbol{y}^{\prime} \mathbf{1}\right)^2}=\frac{\boldsymbol{y}^{\prime} X\left(X^{\top} X\right)^{-1} X^{\top} \boldsymbol{y}-\dfrac{1}{n}\left(\boldsymbol{y}^{\prime} \mathbf{1}\right)^2}{\boldsymbol{y}^{\prime} \boldsymbol{y}-\dfrac{1}{n}\left(\boldsymbol{y}^{\prime} \mathbf{1}\right)^2}=\frac{\operatorname{Cov}(\hat{y}, y)}{\mathrm{D}(y)}
$$
显然, $\mathrm{D}(\hat{y})=\operatorname{Cov}(\hat{y}, y)$, 因此我们有 $R^2=\operatorname{Corr}^2(\hat{y}, y), R^2$ 实际上就是拟合量和真实值相关系数的平方.
