## 1. Definition
### 1.1. Definition of Jacobi Derivatives
**Vector Version**: Suppose $\boldsymbol{f}: \mathbb{R}^n \rightarrow \mathbb{R}^m$, and $\boldsymbol{x} \in(\operatorname{dom} \boldsymbol{f})^{\circ}$. If there exists a matrix $J$ such that
$$
\lim _{\boldsymbol{z} \in \operatorname{dom} \boldsymbol{f}, \boldsymbol{z} \neq \boldsymbol{x}, \boldsymbol{z} \rightarrow \boldsymbol{x}} \frac{\|\boldsymbol{f}(\boldsymbol{z})-\boldsymbol{f}(\boldsymbol{x})-J(\boldsymbol{z}-\boldsymbol{x})\|_2}{\|\boldsymbol{z}-\boldsymbol{x}\|_2}=0
$$
for all choice of sequence $\{\boldsymbol{z}\} \subset \operatorname{dom} \boldsymbol{f}$, then $\boldsymbol{f}$ is said to be differentiable at and denote
$$
\mathrm{D} \boldsymbol{f}(\boldsymbol{x})=J
$$
Let $\boldsymbol{z}=\boldsymbol{x}+\boldsymbol{t e}_i$ and let $t \rightarrow 0$. Then
$$
\begin{aligned}
 \lim _{\boldsymbol{z} \in \operatorname{dom} \boldsymbol{f}, \boldsymbol{z} \neq \boldsymbol{x}, \boldsymbol{z} \rightarrow \boldsymbol{x}} \frac{\|\boldsymbol{f}(\boldsymbol{z})-\boldsymbol{f}(\boldsymbol{x})-J(\boldsymbol{z}-\boldsymbol{x})\|_2}{\|\boldsymbol{z}-\boldsymbol{x}\|_2}&=\lim _{t \rightarrow 0} \frac{\left\|\boldsymbol{f}\left(\boldsymbol{x}+\boldsymbol{t e}_i\right)-\boldsymbol{f}(\boldsymbol{x})-t \boldsymbol{e}_i\right\|_2}{|t|} \\
& =\lim _{t \rightarrow 0}\left\|\frac{\boldsymbol{f}\left(\boldsymbol{x}+t \boldsymbol{e}_i\right)-\boldsymbol{f}(\boldsymbol{x})}{t}-J \boldsymbol{e}_i\right\|_2 \\
& =\left\|\frac{\partial \boldsymbol{f}(\boldsymbol{x})}{\partial x_i}-J \boldsymbol{e}_i\right\|_2 \\
&
\end{aligned}
$$
Therefore
$$
\mathrm{D}_{\boldsymbol{x}} \boldsymbol{f}(\boldsymbol{x})=\frac{\partial \boldsymbol{f}(\boldsymbol{x})}{\partial \boldsymbol{x}^{\top}}
$$
Here $J$ is a $m \times \mathrm{n}$ Jacobian matrix
**Scalar-Matrix Version**: When $f: \mathbb{R}^{m\times n}\to \mathbb{R}$ is real-valued, then we define Jacobi derivatives of $f$ as
$$\mathrm{D}_Xf(X) = \dfrac{\partial f(X) }{\partial X^{\top} } = \begin{pmatrix}
\dfrac{\partial f(X) }{\partial X_{11}} &  \dfrac{\partial f(X) }{\partial X_{21}} &\cdots&\dfrac{\partial f(X) }{\partial X_{m1}}  \\
\dfrac{\partial f(X) }{\partial X_{12}} &  \dfrac{\partial f(X) }{\partial X_{22}} &\cdots&\dfrac{\partial f(X) }{\partial X_{m2}}  \\
\vdots&\vdots& &\vdots \\
\dfrac{\partial f(X) }{\partial X_{1n}} &  \dfrac{\partial f(X) }{\partial X_{2n}} &\cdots&\dfrac{\partial f(X) }{\partial X_{mn}}  
\end{pmatrix} \in \mathbb{R}^{n\times m} $$
**Matrix to Matrix Version**: When $F: \mathbb{R}^{m\times n}\to \mathbb{R}^{p\times q}$ is real-valued, then we define Jacobi derivatives of $F$ as 
$$
\mathrm{D}_XF(X) = \dfrac{\partial \mathrm{vec}(F(X)) }{\partial \mathrm{vec}(X)^{\top} } \in \mathbb{R}^{pq\times mn} 
$$

### 1.2. 梯度矩阵
**实值标量函数**: 采用列向量形式定义的偏导算子被称为列向量偏导算子, 习惯称为梯度算子. 对于实值标量函数$f(X)$, 其梯度矩阵定义为
$$
\nabla _Xf(X) = D_X^{\top} f(X)
$$
当矩阵$X$退化为向量$\boldsymbol{x}$时, 该等式也成立.
**实值向量函数**:  这里我们只对$\boldsymbol{f}(\boldsymbol{x})$类型的实值向量函数的梯度矩阵进行形式上的定义
$$
\nabla _{\boldsymbol{x}}\boldsymbol{f}(\boldsymbol{x}) = \mathrm{D}_{\boldsymbol{x}}^{\top} \boldsymbol{f}(\boldsymbol{x})
$$
**实值矩阵函数**: 对于实值矩阵函数$F(X)\in \mathbb{R}^{p\times q}$. 梯度矩阵定义为
$$
\nabla_XF(X) = \dfrac{\mathrm{vec}^{\top} (F(X)) }{\partial \mathrm{ve c}(X)} 
$$
显然有
$$
\nabla_XF(X)=(\mathrm{D}_XF(X))^{\top} 
$$
换言之, 梯度矩阵是其Jacobian矩阵的转置



## 2. 计算
### 2.1. 独立性基本假设
假定实值函数的向量变元$\boldsymbol{x}$或者矩阵变元$X$本身无任何特殊结构, 即向量或矩阵变元的元素之间是各自独立的. 上述独立性基本假设可以用数学公式表示为
$$
\dfrac{\partial x_i }{\partial x_j} = \delta_{ij},\quad \dfrac{\partial x_{kl} }{\partial x_{ij}} =\delta_{ki}\delta_{lj}  
$$
### 2.2. 基本法则
1. **线性法则**: 若$f(X)$, $g(X)$分别是矩阵$X$的实值函数, $c_1, c_2$为实常数, 则
   $$
    \dfrac{\partial c_1f(X)+c_2g(X) }{\partial X} = c_1\dfrac{\partial f(X) }{\partial X} + c_2\dfrac{\partial f(X) }{\partial X}  
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
   \left[\dfrac{\partial g(F) }{\partial X} \right]_{ij}=\dfrac{\partial g(F) }{\partial x_{ij}} =\sum_{k=1}^p\sum_{l=1}^q \dfrac{\partial g(F) }{\partial f_{kl}}\dfrac{\partial f_{kl} }{\partial x_{ij}}
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

3. **Basic Rules**: 
   $$
   \dfrac{\mathrm{d}\boldsymbol{x}^{\top} }{\mathrm{d}\boldsymbol{x}} = I,\quad \dfrac{\mathrm{d}\boldsymbol{x}}{\mathrm{d}\boldsymbol{x}^{\top} } = I
   $$

   $$
   \dfrac{\mathrm{d}\boldsymbol{x}^{\top} A}{\mathrm{d}\boldsymbol{x}} = A,\quad \dfrac{\mathrm{d}A\boldsymbol{x}}{\mathrm{d}\boldsymbol{x}^{\top} } = A
   $$

   