## 1. Lagrange对偶函数
### 1.1. Lagrange乘子
考虑标准形式的优化问题
$$
\begin{array}{ll}
\operatorname{minimize} & f_0(\boldsymbol{x}) \\
\text { subject to } & f_i(\boldsymbol{x}) \leqslant 0, \quad i=1, \cdots, m \\
& h_i(\boldsymbol{x})=0, \quad i=1, \cdots, p,
\end{array} \tag{1}
$$
定义问题(1)的Lagrange函数$L: \mathbb{R}^n\times \mathbb{R}^m\times \mathbb{R}^p\to \mathbb{R}$为
$$
L(\boldsymbol{x}, \boldsymbol{\lambda}, \boldsymbol{\nu}) = f_0(\boldsymbol{x}) + \sum_{i=1}^m \lambda_i f_i(\boldsymbol{x}) + \sum_{i=1}^p \nu_i h_i(\boldsymbol{x}) 
$$
向量$\boldsymbol{\lambda}$和$\boldsymbol{\nu}$称为对偶变量或是问题(1)的Lagrange乘子向量. 

### 1.2. Lagrange对偶函数
定义Lagrange对偶函数$g: \mathbb{R}^{m}\times \mathbb{R}^p\to \mathbb{R}$为Lagrange函数关于$\boldsymbol{x}$取得的最小值: 即对$\boldsymbol{\lambda}\in \mathbb{R}^m$和$\boldsymbol{\nu}\in \mathbb{R}^p$, 有
$$
g(\boldsymbol{\lambda}, \boldsymbol{\nu}) = \inf_{\boldsymbol{x}\in \mathcal{D}} L(\boldsymbol{x}, \boldsymbol{\lambda}, \boldsymbol{\nu}) = \inf_{\boldsymbol{x}\in \mathcal{D}} \left( f_0(\boldsymbol{x}) + \sum_{i=1}^m \lambda_i f_i(\boldsymbol{x}) + \sum_{i=1}^p \nu_i h_i(\boldsymbol{x}) \right)
$$
因为对偶函数是一族关于$(\boldsymbol{\lambda}, \boldsymbol{\nu})$的仿射函数的逐点下确界, 所以即使
