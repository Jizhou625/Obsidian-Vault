## 1. 一阶实矩阵微分
### 1.1. 矩阵微分
矩阵微分用符号$\mathrm{d}X$表示, 定义为
$$
\mathrm{d}X = \begin{pmatrix}
\mathrm{d}X_{11} & \mathrm{d}X_{12}&\cdots & \mathrm{d}X_{1n} \\
\mathrm{d}X_{21} & \mathrm{d}X_{22}&\cdots & \mathrm{d}X_{2n} \\
\vdots & \vdots & & \vdots  \\
 \mathrm{d}X_{m1} & \mathrm{d}X_{m2}&\cdots & \mathrm{d}X_{mn} 
\end{pmatrix}
$$
### 1.2. 标量函数的全微分
对于向量微分, 全微分的定义为
$$
\mathrm{d} f=\sum_{i=1}^n \frac{\partial f}{\partial x_i} \mathrm{d} x_i=\left(\frac{\partial f}{\partial \boldsymbol{x}}\right)^{\top} \mathrm{d} \boldsymbol{x}
$$
对于矩阵微分, 全微分的定义为
$$
\mathrm{d} f=\sum_{i=1}^m \sum_{j=1}^n \frac{\partial f}{\partial X_{i j}} \mathrm{d} X_{i j}=\operatorname{tr}\left(\left(\frac{\partial f}{\partial X}\right)^{\top}  \mathrm{d} X\right)
$$
我们可以统一表示为
$$
\mathrm{d} f = \mathrm{tr}\left(\left(\frac{\partial f}{\partial X}\right)^{\top}  \mathrm{d} X\right) = \mathrm{D}_{\mathrm{vec}(X)}f(X) \mathrm{d}(\mathrm{vec}(X))
$$
这里$X$可以退化为向量. 因此Jacobi derivative和梯度函数可以通过下式辨识
$$
\mathrm{d}f(X) =\mathrm{tr}\left\{A\mathrm{d}X\right\}\iff \mathrm{D}_Xf(X) = A \iff \nabla_Xf(X)=A^{\top}  
$$
### 1.3. 实值矩阵函数的全微分
根据1.2的结论, 我们有
$$
\mathrm{d}f_{kl}(X) =\mathrm{tr}\left(\left(\frac{\partial f_{kl}}{\partial X}\right)^{\top}  \mathrm{d} X\right) = \mathrm{D}_{\mathrm{vec}(X)}f_{kl}(X) \mathrm{d}(\mathrm{vec}(X)) 
$$
于是, 全微分矩阵的向量化函数具有下列的表达式
$$
\mathrm{d}(\mathrm{vec}(F(X))) = \dfrac{\partial \mathrm{vec}(F(X)) }{\partial (\mathrm{vec}(X))^{\top} } \mathrm{d}(\mathrm{vec}(X))
$$
对于一个包含$X$和$X^{\top}$的矩阵函数$F(X)\in \mathbb{R}^{p\times q}$
$$
\mathrm{d}(\mathrm{vec}(F(X))) = A\mathrm{vec}(\mathrm{d}X)+ B\mathrm{d}(\mathrm{vec}(X^{\top}))
$$
利用$\mathrm{d}(\mathrm{vec}X^{\top}) = K_{mn}\mathrm{vec}(\mathrm{d}X)$, 上式可以改写为
$$
\mathrm{d}(\mathrm{vec}F(X)) = (A+BK_{mn})\mathrm{d}(\mathrm{vec}X)
$$
我们有
$$
\begin{align}
\mathrm{d}(\mathrm{vec}F(X)) = (A+BK_{mn})\mathrm{d}(\mathrm{vec}X) &\iff \mathrm{D}_XF(X)= A+BK_{mn}  \\
&\iff \nabla_XF(X) = A^{\top} +K_{nm}B^{\top}
\end{align}
$$
根据[[矩阵代数/Chapter 2. 矩阵求导/Lecture 0. Basic Knowledge#3.2. 向量化算子的性质]], 我们有
$$
\begin{align}
\mathrm{d}F(X)= A(\mathrm{d}X)B&\iff \mathrm{d}(\mathrm{vec}(F(X))) = (B^{\top}\otimes   A)\mathrm{d}(\mathrm{vec}X)  \\
\mathrm{d}F(X)= C(\mathrm{d}X^{\top} )D&\iff \mathrm{d}(\mathrm{vec}(F(X))) = (D^{\top}\otimes C)K_{mn}\mathrm{d}(\mathrm{vec}X)  
\end{align}
$$
因此矩阵函数$F(X): \mathbb{R}^{m\times n}\to \mathbb{R}^{p\times q}$的$pq\times mn$维Jacobian矩阵可以通过下式辨识
$$
\begin{align}
\mathrm{d}F(X)=A(\mathrm{d}X)B+C(\mathrm{d}X^{\top} )D&\iff \mathrm{D}_XF(X)=(B^{\top} \otimes A)+(D^{\top} \otimes C)K_{mn} \\
&\iff \nabla_XF(X)=(B \otimes A^{\top} )+K_{nm}(D \otimes C^{\top})
\end{align}
$$
需要注意的是, 并不是所有的矩阵函数的矩阵微分都可以表示为上述形式


## 2. 微分法
### 2.1. 性质
1. **线性性**: $\mathrm{d}(X+Y) = \mathrm{d}X +\mathrm{d}Y,\quad \mathrm{d}(X-Y) = \mathrm{d}X - \mathrm{d}Y$
2. **乘法法则**: $\mathrm{d}(XY) =(\mathrm{d}X) Y+X(\mathrm{d}Y)$
3. **转置**: $\mathrm{d}(X^{\top})=(\mathrm{d}X)^{\top}$
4. **迹**: $\mathrm{d}\mathrm{tr}(X) =\mathrm{tr}(\mathrm{d}X)$
5. **哈达玛积**: $\mathrm{d}(X\odot Y)=X\odot\mathrm{d}Y +\mathrm{d}X\odot Y$
7. **克罗内亚积**: $\mathrm{d}(U\otimes V) = \mathrm{d}U\otimes V + U\otimes \mathrm{d}V$
8. **向量化**: $\mathrm{d}(\mathrm{vec}(X)) = \mathrm{ve c}(\mathrm{d}X)$
9. **逐元素求导**: $\mathrm{d}\sigma(X) = \sigma^{\prime}(X)\odot \mathrm{d}X$
10. **逆矩阵**: $\mathrm{d}X^{-1} = -X^{-1}(\mathrm{d}X)X^{-1}$
11. **行列式**: $\mathrm{d}|X| = |X|\mathrm{tr}(X^{-1}\mathrm{d}X)$
---
***Proof***: 这里我们只对逆矩阵和行列式进行证明
对于逆矩阵
$$
\begin{align}
\dfrac{\partial X^{-1} }{\partial X_{ij}} &= \lim_{ \Delta X \to 0 }\dfrac{ (X+\Delta X)^{-1} -X^{-1} }{\Delta X_{ij} }  \\ \\
&=\lim _{\Delta X \rightarrow 0} \frac{(X+\Delta X)^{-1} X X^{-1}-(X+\Delta X)^{-1}(X+\Delta X) X^{-1}}{\Delta X_{ij}} \\  \\
& = -X^{-1} \lim _{\Delta x \rightarrow 0} \frac{\Delta X}{\Delta X_{ij}} X^{-1}  \\
&= -X^{-1} \dfrac{\partial X }{\partial X_{ij}}X^{-1} 
\end{align} 
$$
对于行列式
$$
\begin{align}
\dfrac{\partial |X| }{\partial X_{ij}} & = \lim_{ \Delta X \to 0 } \dfrac{|X+\Delta X|-|X|}{\Delta X_{ij}}  \\
& =  \lim_{ \Delta X \to 0 } \dfrac{|X||I+X^{-\frac{1}{2}}\Delta X X^{-\frac{1}{2}}| -|X|}{\Delta X_{ij}}  \\
& = \lim_{ \Delta X \to 0 } \dfrac{|X|\mathrm{tr}\{X^{-\frac{1}{2}}\Delta X X^{-\frac{1}{2}}\}}{\Delta X_{ij}}\\ 
& = |X|\mathrm{tr}\left\{X^{-1}\dfrac{\partial X }{\partial X_{ij}}  \right\}
\end{align}
$$

### 2.2. 微分法Example
**Example**: $f(X) =\boldsymbol{a}^{\top} X \boldsymbol{b},\quad \dfrac{\partial f(X) }{\partial X}$
1. 首先对$f(X)$求微分
  $$
  \mathrm{ d}f(X) = \mathrm{d}(\boldsymbol{a}^{\top} X \boldsymbol{b}) = \boldsymbol{a}^{\top} (\mathrm{d} X)\boldsymbol{b}=\mathrm{tr}\{\boldsymbol{ba}^{\top} \mathrm{d}X\}
  $$

2. 根据矩阵导数的定义, 我们得到
   $$
   \left(\frac{\partial f}{\partial X}\right)^{\top}=\boldsymbol{ba}^{\top} \implies \dfrac{\partial f }{\partial X}=\boldsymbol{ab}^{\top}
   $$
### 2.4. 

## 3. 二阶实矩阵微分

### 3.1. Hessian矩阵
**向量形式**: 二次连续可导的实值函数$f(\boldsymbol{x})$相对于$m\times 1$实向量$\boldsymbol{x}$的二阶偏导数称为Hessian矩阵, 记为$H[f(\boldsymbol{x})]$, 定义为
$$
H(f(\boldsymbol{x})) = \dfrac{\partial ^2 f(\boldsymbol{x}) }{\partial \boldsymbol{x}\partial \boldsymbol{x}^{\top} } =\dfrac{\partial  }{\partial \boldsymbol{x}}\left[\dfrac{\partial f(\boldsymbol{x}) }{\partial \boldsymbol{x}^{\top} } \right] \in \mathbb{R}^{m\times m}
$$
或记作
$$
H(f(\boldsymbol{x})) = \nabla_{\boldsymbol{x}}(\mathrm{D}_{\boldsymbol{x}}f(\boldsymbol{x}))=\begin{pmatrix}
\dfrac{\partial ^2f }{\partial x_1 \partial x_1} & \dfrac{\partial ^2f }{\partial x_1 \partial x_2} & \cdots & \dfrac{\partial ^2f }{\partial x_1 \partial x_m} \\
\dfrac{\partial ^2f }{\partial x_2 \partial x_1} & \dfrac{\partial ^2f }{\partial x_2 \partial x_2} & \cdots & \dfrac{\partial ^2f }{\partial x_2 \partial x_m} \\ 
\vdots& \vdots& & \vdots  \\
\dfrac{\partial ^2f }{\partial x_m \partial x_1} & \dfrac{\partial ^2f }{\partial x_m \partial x_2} & \cdots & \dfrac{\partial ^2f }{\partial x_m \partial x_m} \\ 
\end{pmatrix}
$$
**矩阵形式**: 实标量函数$f(X)$的Hessian矩阵定义为 
$$
H[f(X)]= \dfrac{\partial ^2 f(X) }{\partial \mathrm{vec}(X)\partial (\mathrm{vec}(X))^{\top} } 
$$
### 3.2. 标量函数$f(\boldsymbol{x})$的二阶微分
注意到微分$\mathrm{d}\boldsymbol{x}$不是向量$\boldsymbol{x}$的函数, 故有
$$
\mathrm{d}^2\boldsymbol{x}=\mathrm{d}(\mathrm{d}\boldsymbol{x})=0
$$
我们可以求得二阶微分$\mathrm{d}^2f(\boldsymbol{x})=\mathrm{d}(\mathrm{d}f(\boldsymbol{x}))$为
$$
\mathrm{d}^2f(\boldsymbol{x})= (\mathrm{d}\boldsymbol{x})^{\top} \dfrac{\partial \mathrm{d}f(\boldsymbol{x}) }{\partial \boldsymbol{x}} =  (\mathrm{d}\boldsymbol{x})^{\top} \dfrac{\partial f^2(\boldsymbol{x}) }{\partial \boldsymbol{x}\partial \boldsymbol{x}^{\top} }\mathrm{d}\boldsymbol{x}=  (\mathrm{d}\boldsymbol{x})^{\top} H[f(\boldsymbol{x})]\mathrm{d}\boldsymbol{x}
$$
我们需要确保Hessian矩阵是实对称矩阵, 因此
$$
\mathrm{d}^2f(\boldsymbol{x}) =(\mathrm{d}\boldsymbol{x})^{\top} B\mathrm{d}\boldsymbol{x}\iff H[f(\boldsymbol{x})] = \dfrac{1}{2} (B^{\top} +B) 
$$
### 3.3 矩阵函数$f(X)$的二阶微分
与1.2的推导类似, 我们可以得到
$$
\mathrm{d}^2f(X)= (\mathrm{d}(\mathrm{vec}X))^{\top} H[f(X)]\mathrm{d}(\mathrm{vec}X)
$$
于是
$$
\mathrm{d}^2f(X)= (\mathrm{d}(\mathrm{vec}X))^{\top} B\mathrm{d}(\mathrm{vec}X)\iff H[f(X)]= \frac{1}{2}(B^{\top} +B)
$$
更进一步, 因为$\mathrm{d}f(X) =\mathrm{tr}\left\{A\mathrm{d}X\right\}$的微分, 不失一般性, 假设矩阵函数$A(X)$的微分矩阵为
$$
\mathrm{d}A = B(\mathrm{d}X)C, \quad B, C\in \mathbb{R}^{n\times m}
$$
或者
$$
\mathrm{d}A = U(\mathrm{d}X)^{\top} V,\quad U\in \mathbb{R}^{n\times n}, V\in \mathbb{R}^{m\times m}
$$
因此二阶微分可以写成$\mathrm{d}^2f(X)=\mathrm{tr}\left\{\mathrm{d}A\mathrm{d}X\right\}$, 根据上面假设中的形式
$$
\mathrm{d}^2f(X)=\mathrm{tr}\left\{B(\mathrm{d}X)C\mathrm{d}X\right\}=(\mathrm{d}\mathrm{vec}X)^{\top} K_{nm}(C^{\top} \otimes B)\mathrm{d}(\mathrm{vec}X)
$$
或
$$
\mathrm{d}^2f(X) = \mathrm{tr}\left\{V(\mathrm{d}X)U(\mathrm{d}X)^{\top}\right\} = (\mathrm{d}\mathrm{vec}X)^{\top} (U^{\top} \otimes V)\mathrm{d}\mathrm{vec}X
$$
因此我们有下面的辨识方法
$$
\begin{align}
\mathrm{d}^2 f(X) = \mathrm{tr}\left\{V(\mathrm{d}X)U(\mathrm{d}X)^{\top} \right\} &\iff H[f(x)] = \frac{1}{2}(U^{\top} \otimes V + U \otimes V^{\top} ) \\
\mathrm{d}^2f(X) = \mathrm{tr}\left\{B(\mathrm{d}X)C\mathrm{d}X)\right\} &\iff H[f(X)] =\frac{1}{2}K_{nm}(C^{\top} \otimes B+B^{\top} \otimes C)
\end{align}
$$
### 3.4. 例子
**Example 1**: 实值函数$f(X)=\mathrm{tr}\left\{X^{-1}\right\}$, 其中$X$是一个$n\times n$矩阵
$$
\mathrm{d}f(X) = -\mathrm{tr}\left\{X^{-1}\mathrm{d}X X^{-1}\right\}
$$
求上述一阶微分的微分, 得到二阶微分矩阵
$$
\begin{align}
\mathrm{d}^2f(X) &= -\mathrm{tr}\left\{(\mathrm{d}X^{-1})(\mathrm{d}X)X^{-1}\right\}- \mathrm{tr}\left\{X^{-1}(\mathrm{d}X)(\mathrm{d}X^{-1})\right\} \\
& = 2\mathrm{tr}\left\{X^{-1}(\mathrm{d}X)X^{-1}(\mathrm{d}X)X^{-1}\right\} \\
& = 2\mathrm{tr}\left\{X^{-2}(\mathrm{d}X)X^{-1}\mathrm{d}X\right\}
\end{align}
$$
根据3.3中提到的辨识方法, 即可得到Hessian矩阵
$$
H[f(X)] = \dfrac{\partial ^2 \mathrm{tr}\left\{X^{-1}\right\} }{\partial \mathrm{vec} X \partial(\mathrm{vec}X)^{\top} } = K_{nn}[X^{-\top}\otimes X^{-2} + (X^{-2})^{\top} \otimes  X^{-1} ] 
$$
**Example 2**: 对于二次型函数$f(X)=\mathrm{tr}\left\{X^{\top} A X\right\}$, 其一阶微分为
$$
\mathrm{d}f(X) =\mathrm{tr}\left\{X^{\top} (A+A^{\top} )\mathrm{d}X\right\}
$$
再次求微分, 得到二阶微分
$$
\mathrm{d}^2f(X)=\mathrm{tr}\left\{(A+A^{\top} )(\mathrm{d}X)(\mathrm{d}X)^{\top} \right\}
$$
根据3.3中提到的辨识方法, 即可得到Hessian矩阵
$$
H[f(X)] = \dfrac{\partial ^2 \mathrm{tr}\left\{X^{\top} A X\right\} }{\partial \mathrm{vec} X \partial(\mathrm{vec}X)^{\top} } = I \otimes (A+A^{\top} ) 
$$
**Example 3**: 函数$\log|X|$的一阶微分为$\mathrm{d}\log|X| = \mathrm{tr}\left\{X^{-1}\mathrm{d}X\right\}$, 再次求微分, 可以得到二阶微分
$$
\mathrm{d}^2f(X) = \mathrm{tr}\left\{X^{-1}(\mathrm{d}X)X^{-1}\mathrm{d}X\right\}
$$
根据3.3中提到的辨识方法, 即可得到Hessian矩阵
$$
H[f(X)] = \dfrac{\partial ^2 \log |X| }{\partial \mathrm{vec} X \partial(\mathrm{vec}X)^{\top} } = -K_{nn}(X^{-\top} \otimes  X^{-1}) 
$$