## 1. Jacobi导数和梯度
### 1.1. 向量视角下的Jacobi矩阵
假设 $\boldsymbol{f}: \mathbb{R}^n \rightarrow \mathbb{R}^m$ 并且 $\boldsymbol{x} \in(\operatorname{dom} \boldsymbol{f})^{\circ}$. 假设存在矩阵$J$满足 
$$
\lim _{\boldsymbol{z} \in \operatorname{dom}\boldsymbol{f} \backslash \{\boldsymbol{x}\}, \boldsymbol{z} \rightarrow \boldsymbol{x}} \frac{\|\boldsymbol{f}(\boldsymbol{z})-\boldsymbol{f}(\boldsymbol{x})-J(\boldsymbol{z}-\boldsymbol{x})\|_2}{\|\boldsymbol{z}-\boldsymbol{x}\|_2}=0
$$
则称$\boldsymbol{f}$在$\boldsymbol{x}$处是可导的并记
$$
\mathrm{D} \boldsymbol{f}(\boldsymbol{x})=J
$$
设 $\boldsymbol{z}=\boldsymbol{x}+\boldsymbol{t e}_i$, 令$t \rightarrow 0$, 则
$$
\begin{aligned}
 \lim _{\boldsymbol{z} \in \operatorname{dom}\boldsymbol{f} \backslash \{\boldsymbol{x}\}, \boldsymbol{z} \rightarrow \boldsymbol{x}} \frac{\|\boldsymbol{f}(\boldsymbol{z})-\boldsymbol{f}(\boldsymbol{x})-J(\boldsymbol{z}-\boldsymbol{x})\|_2}{\|\boldsymbol{z}-\boldsymbol{x}\|_2}&=\lim _{t \rightarrow 0} \frac{\left\|\boldsymbol{f}\left(\boldsymbol{x}+\boldsymbol{t e}_i\right)-\boldsymbol{f}(\boldsymbol{x})-t \boldsymbol{e}_i\right\|_2}{|t|} \\
& =\lim _{t \rightarrow 0}\left\|\frac{\boldsymbol{f}\left(\boldsymbol{x}+t \boldsymbol{e}_i\right)-\boldsymbol{f}(\boldsymbol{x})}{t}-J \boldsymbol{e}_i\right\|_2 \\
& =\left\|\frac{\partial \boldsymbol{f}(\boldsymbol{x})}{\partial x_i}-J \boldsymbol{e}_i\right\|_2 \\
&
\end{aligned}
$$
于是
$$
\mathrm{D} \boldsymbol{f}(\boldsymbol{x})=\frac{\partial \boldsymbol{f}(\boldsymbol{x})}{\partial \boldsymbol{x}^{\top}}
$$
这里 $J$ 是一个 $m \times n$ 的Jacobi矩阵. 

### 1.2. 矩阵视角下的Jacobi矩阵
设$F: \mathbb{R}^{m\times n}\to \mathbb{R}^{p\times q}$是一个实值函数, 其Jacobi导数定义为
$$
\mathrm{D}_XF(X) = \dfrac{\partial \mathrm{vec}(F(X)) }{\partial \mathrm{vec}(X)^{\top} } \in \mathbb{R}^{pq\times mn} 
$$
事实上, 向量视角下的定义是矩阵视角下的特例, 这是因为对于任意的向量$\boldsymbol{x}$, $\mathrm{vec}\left(\boldsymbol{x}\right) = \boldsymbol{x}$. 因此, 之后如果不特别说明, 我们将使用矩阵视角下的Jacobi矩阵的定义.

### 1.3. 梯度矩阵
对于实值矩阵函数$F(X)\in \mathbb{R}^{p\times q}$. 梯度矩阵定义为
$$
\nabla_XF(X) = \dfrac{\mathrm{vec}^{\top} (F(X)) }{\partial \mathrm{ve c}(X)} 
$$
显然有
$$
\nabla_XF(X)=(\mathrm{D}_XF(X))^{\top} 
$$
换言之, 梯度矩阵是其Jacobian矩阵的转置


## 2. 基本法则
### 2.1. 独立性基本假设
假定实值函数的向量变元$\boldsymbol{x}$(矩阵变元$X$)本身无任何特殊结构, 即向量或矩阵变元的元素之间是各自独立的. 上述独立性基本假设可以用数学公式表示为
$$
\dfrac{\partial x_i }{\partial x_j} = \delta_{ij},\quad \dfrac{\partial x_{kl} }{\partial x_{ij}} =\delta_{ki}\delta_{lj}  
$$
这里的$\delta_{ij}$是克罗内克符号. 

### 2.2. 基本法则
1. **线性法则**: 若$F(X)$, $G(X)$分别是矩阵$X$的实值函数, $c_1, c_2$为实常数, 则
   $$
    \dfrac{\partial c_1F(X)+c_2G(X)}{\partial X} = c_1\dfrac{\partial F(X) }{\partial X} + c_2\dfrac{\partial G(X) }{\partial X}  
   $$
1. **乘法法则**: 若$f(X), g(X)$都是矩阵$X$的实值函数, 则
   $$
   \dfrac{\partial f(X) g(X)}{\partial X} = g(X)\dfrac{\partial f(X) }{\partial X}+f(X)\dfrac{\partial g(X) }{\partial X}   
   $$
2. **链式法则**: 设$X$是$m\times n$矩阵, 且$y=f(X)$和$g(y)$分别是以矩阵$X$和标量$y$为变元的实值函数, 则
   $$
   \dfrac{\partial g(f(X)) }{\partial X} = \dfrac{\mathrm{d}g(y)}{\mathrm{d}y}\dfrac{\partial f(X) }{\partial X}
   $$
   推而广之, 若记$g(F(X))=g(F)$, 其中$F\in \mathbb{R}^{p\times q}$, $X\in \mathbb{R}^{m\times n}$. 则链式法则为
   $$
   \left[\dfrac{\partial g(F) }{\partial X} \right]_{ij}=\dfrac{\partial g(F) }{\partial x_{ij}} = \dfrac{\partial g(F)}{\partial \mathrm{vec}^{\top}\left(F\right)} \dfrac{\partial \mathrm{vec}\left(F\right)}{\partial x_{ij}}  
   $$

### 2.3. 向量求导运算法则
1. **Production Rule**: 若$\phi(\boldsymbol{x}) = (\boldsymbol{f}(\boldsymbol{x}))^{\top}\boldsymbol{g}(\boldsymbol{x})$, 则
  $$
  \mathrm{D}_{\boldsymbol{x}}\phi(\boldsymbol{x}) = (\boldsymbol{g}(\boldsymbol{x}))^{\top}\mathrm{D}_{\boldsymbol{x}}\boldsymbol{f}(\boldsymbol{x}) + (\boldsymbol{f}(\boldsymbol{x}) )^{\top} \mathrm{D}_{\boldsymbol{x}} \boldsymbol{g}(\boldsymbol{x})$$
  $$\nabla \phi(\boldsymbol{x}) = \nabla_{\boldsymbol{x}} \boldsymbol{f} (\boldsymbol{x}) \boldsymbol{g}(\boldsymbol{x}) + \nabla_{\boldsymbol{x}}\boldsymbol{g}(\boldsymbol{x}) \boldsymbol{f}(\boldsymbol{x})
  $$

2. **Chain Rule**: 
   $$
   \dfrac{\partial \boldsymbol{h}(\boldsymbol{x}) }{\partial \boldsymbol{x}^{\top}  } = \dfrac{\partial \boldsymbol{h}(\boldsymbol{x}) }{\partial \boldsymbol{f}^{\top} (\boldsymbol{x})}\cdot \dfrac{\partial \boldsymbol{f}(\boldsymbol{x}) }{\partial \boldsymbol{x}^{\top} }  \implies\mathrm{D}_{\boldsymbol{x}}\boldsymbol{h}(\boldsymbol{x}) = \mathrm{D}_{\boldsymbol{f}(\boldsymbol{x})} \boldsymbol{h}(\boldsymbol{x})\cdot \mathrm{D}_{\boldsymbol{x}}\boldsymbol{f}(\boldsymbol{x}) 
   $$
    $$
   \dfrac{\partial \boldsymbol{h}^{\top} (\boldsymbol{x}) }{\partial \boldsymbol{x}} = \dfrac{\partial \boldsymbol{f}^{\top} (\boldsymbol{x}) }{\partial \boldsymbol{x}} \cdot \dfrac{\partial \boldsymbol{h}^{\top} (\boldsymbol{x}) }{\partial \boldsymbol{f}(\boldsymbol{x})} \implies \nabla_{\boldsymbol{x}}\boldsymbol{h}(\boldsymbol{x}) = \nabla_{\boldsymbol{x}}\boldsymbol{f}(\boldsymbol{x}) \nabla_{\boldsymbol{f}(\boldsymbol{x})}\boldsymbol{h}(\boldsymbol{x})
   $$



   