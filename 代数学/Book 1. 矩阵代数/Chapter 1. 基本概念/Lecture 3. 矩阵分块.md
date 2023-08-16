## 1. 一些术语
### 1.1. 子矩阵
设$A\in \mathbb{M}_{m, n}(\mathbb{F})$, 对指标集${\alpha}\subseteq \{1,2,\cdots, n\}$和${\beta}\subseteq \{1,2, \cdots, n\}$, 我们用$A[{\alpha}, {\beta}]$来记$A$的位于由${\alpha}$所指定的那些行以及由${\beta}$所指定的那些列的位置上那些元素所构成的子矩阵. 

如果${\alpha} = {\beta}$, 则子矩阵$A[{\alpha}] = A[{\alpha}, {\alpha}]$就是$A$的一个主子矩阵(principal submatrix). 

对$A\in \mathbb{M}_{n}(\mathbb{F})$以及$k\in \{1,2, \cdots, n\}$, $A[\{1,2,\cdots, k\}]$是顺序主子矩阵(leading principal submatrix), $A[\{n-k+1, n-k+2, \cdots, n\}]$是尾主子矩阵(trailing principal submatrix).

### 1.2. 子式
$A$中的一个$r\times r$子矩阵的行列式称为$A$的一个$r$阶子式(minor); 如果一个$r\times r$的子矩阵是一个主子矩阵, 那么它的行列式就是一个$r$阶主子式(principal minor). 如果该子矩阵是一个顺序主子矩阵, 那么它的行列式就是一个顺序主子式(leading principal minor); 如果该子矩阵是一个尾主子矩阵, 那么它的行列式就是一个尾主子式(trailing principal minor). 我们约定空的主子式是$1$, 即$\det|\varnothing| = 1$. 

## 2. 分块矩阵的运算
### 2.1. 分块矩阵的乘法
如果$A\in \mathbb{M}_{m, n}(\mathbb{F})$的分划以及$B\in \mathbb{M}_{m, n}(\mathbb{F})$的分划使得$\{1,2, \cdots , n\}$的两个分划完全相同, 则这两个矩阵分划就称为是共形的(conformal). 在此情形下, 有
$$
(AB)[\alpha_i, \gamma_j] = \sum\limits_{k=1}^{s} A[\alpha_i, \beta_k]B[\beta_k, \gamma_j] 
$$
其中, 分划未必是顺序的.

### 2.2. Sherman-Morrison-Woodbury公式
假设非奇异的矩阵$A\in \mathbb{M}_{n}(\mathbb{F})$有一个已知的逆$A^{-1}$, 考虑$B = A+XRY$, 其中$X$是$n\times r$矩阵, $Y$是$r\times n$矩阵, $R$是$r\times r$非奇异矩阵. 如果$B$和$R^{-1}+ YA^{-1}X$是非奇异的, 那么
$$
B^{-1}=A^{-1}-A^{-1} X\left(R^{-1}+Y A^{-1} X\right)^{-1} Y A^{-1}
$$
当$r<<n$时, 这个公式可以用来更有效地计算$B^{-1}$.

特别地, 当$B = A +\boldsymbol{x}\boldsymbol{y}^{\top}$且$\boldsymbol{y}^{\top}A^{-1}\boldsymbol{x}\neq -1$时
$$
B^{-1} = A^{-1} - \dfrac{1}{1+ \boldsymbol{y}A^{-1}\boldsymbol{x}}A^{-1}\boldsymbol{x}\boldsymbol{y}^{\top}A^{-1}
$$
当$A = I$, 即$B = I + \boldsymbol{xy}^{\top}$时, 只要$\boldsymbol{y}^{\top}\boldsymbol{x}\neq -1$, 就有
$$
B^{-1} = I - \dfrac{1}{1+ \boldsymbol{y}^{\top}\boldsymbol{x}}\boldsymbol{xy}^{\top}
$$
___
##### Proof
我们只要验证
$$
\begin{aligned} 
B^{-1} B &= A^{-1}(A+XRY)-A^{-1} X\left(R^{-1}+Y A^{-1} X\right)^{-1} Y A^{-1}(A+XRY) \\ 
& = I  + A^{-1}XRY - A^{-1}X\left(R^{-1}+YA^{-1}X\right)^{-1}Y - A^{-1}X\left(R^{-1}+YA^{-1}X\right)^{-1}YA^{-1}XRY \\
& = I + A^{-1}XRY - A^{-1}X\left(R^{-1}+YA^{-1}X\right)^{-1}\left(R^{-1}+YA^{-1}X\right)RY \\
& = I
\end{aligned}
$$
这就证明了结论成立
#####
___
### 2.3. Schur补
假设$\alpha$是使得$A[\alpha]$非奇异的一个指标集. 我们称特殊的矩阵
$$
A / A[\alpha] = A[\alpha^c] - A[\alpha^c, \alpha]A[\alpha]^{-1}A[\alpha, \alpha^c]
$$
为$A[\alpha]$在$A$中的一个Schur补.


## 3. 分块矩阵的秩
### 3.1. 零化度互补(Complementary Nullity)
假设$A\in \mathbb{M}_n(\mathbb{F})$非奇异, 设$\alpha$和$\beta$是$\{1,2, \cdots, n\}$的非空指标集, $|\alpha|=r, |\beta|=s$. 则零化度互补(Complementary Nullity)法则为
$$
\mathrm{nullity}(A[\alpha, \beta]) = \mathrm{nullity}(A^{-1}[\beta^c, \alpha^c])
$$
它等价于秩恒等式
$$
\mathrm{rank}(A[\alpha, \beta]) = \mathrm{rank}(A^{-1}[\beta^c, \alpha^c]) + r + s - n
$$