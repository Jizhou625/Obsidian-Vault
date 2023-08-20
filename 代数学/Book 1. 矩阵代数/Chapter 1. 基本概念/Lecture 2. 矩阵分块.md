## 1. 基础知识
### 1.1. 子矩阵
设$A\in \mathbb{M}_{m, n}(\mathbb{F})$, 对指标集${\alpha}\subseteq \{1,2,\cdots, n\}$和${\beta}\subseteq \{1,2, \cdots, n\}$, 我们用$A[{\alpha}, {\beta}]$来记$A$的位于由${\alpha}$所指定的那些行以及由${\beta}$所指定的那些列的位置上那些元素所构成的子矩阵. 

如果${\alpha} = {\beta}$, 则子矩阵$A[{\alpha}] = A[{\alpha}, {\alpha}]$就是$A$的一个主子矩阵(principal submatrix). 

对$A\in \mathbb{M}_{n}(\mathbb{F})$以及$k\in \{1,2, \cdots, n\}$, $A[\{1,2,\cdots, k\}]$是顺序主子矩阵(leading principal submatrix), $A[\{n-k+1, n-k+2, \cdots, n\}]$是尾主子矩阵(trailing principal submatrix).

### 1.2. 子式
$A$中的一个$r\times r$子矩阵的行列式称为$A$的一个$r$阶子式(minor); 如果一个$r\times r$的子矩阵是一个主子矩阵, 那么它的行列式就是一个$r$阶主子式(principal minor). 如果该子矩阵是一个顺序主子矩阵, 那么它的行列式就是一个顺序主子式(leading principal minor); 如果该子矩阵是一个尾主子矩阵, 那么它的行列式就是一个尾主子式(trailing principal minor). 我们约定空的主子式是$1$, 即$\det|\varnothing| = 1$. 

### 1.3. 子矩阵和顺序主子矩阵
假设$\alpha$是使得$A[\alpha]$非奇异的一个指标集, $A^{\prime}$是$A$经过行列对换得到的矩阵, 使得$A[\alpha]$出现在$A^{\prime}$的左上角, 但是$\alpha$和$\alpha^c$中的相对顺序在$A^{\prime}$中保持不变. 设$|\alpha|=t$, 再设$\beta = \{1,2,\cdots, t\}$, 则我们有
$$
A[\alpha]^{-1} = A^{\prime}[\beta]^{-1}, \quad A^{-1}[\alpha] =A^{\prime - 1}[\beta]
$$
___
##### Proof
事实上, 我们有$A[\alpha] = A^{\prime}[\beta]$, 因此$A[\alpha]^{-1} = A^{\prime}[\beta]^{-1}$显然成立. 设从$A$到$A^{\prime}$需要进行$k$次初等行列变换, 对于任意$i,j\in\{1,2, \cdots, t\}$, 从$i$到$\alpha_i$, $j$到$\alpha_j$共需要进行$|\alpha_i - i| + |\alpha_j - j|$次初等行列变换. 因为
$$
\begin{aligned} 
   A^*[\alpha_i, \alpha_j] &= (-1)^{\alpha_i +\alpha_j} \det\left(A[\alpha_j^c, \alpha_i^c]\right)  \\ 
   A^{\prime *}[i, j] &= (-1)^{i+j} \det\left(A^{\prime}[j^c, i^c]\right)
\end{aligned}
$$
于是我们有
$$
\begin{aligned} 
   A^{-1}[\alpha_i, \alpha_j] &= \dfrac{1}{\det(A)} A^*[\alpha_i, \alpha_j]\\ 
   & = (-1)^{\alpha_i +\alpha_j} \dfrac{\det\left(A[\alpha_j^c, \alpha_i^c]\right)}{\det(A)}  \\ 
    & = (-1)^{\alpha_i +\alpha_j+k} \dfrac{\det\left(A[\alpha_j^c, \alpha_i^c]\right)}{\det(A^{\prime})}  \\
    & = (-1)^{\alpha_i +\alpha_j+k+|\alpha_i - i| +|\alpha_j - j|} \dfrac{\det\left(A[j^c, i^c]\right)}{\det(A^{\prime})}  \\
    & =  (-1)^{\alpha_i +\alpha_j+k+|\alpha_i - i| +|\alpha_j - j|+i+j}\dfrac{A^{\prime *}[i,j]}{\det(A^{\prime})} \\ 
    & =  (-1)^{\alpha_i +\alpha_j+k+|\alpha_i - i| +|\alpha_j - j|+i+j} A^{-1}[i, j]\\ 
    & = (-1)^kA^{-1}[i, j]
\end{aligned}
$$
又因为从$A^{\prime}$到$A$的初等变换关于行列是对称的, 因此$k$是偶数. 这就证明了
$$
A^{-1}[\alpha_i, \alpha_j]  = A^{-1}[i, j] \implies A^{-1}[\alpha] =A^{\prime - 1}[\beta]
$$
#####
___

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

假设下面所有的逆都是存在的, 则有 
$$
A^{-1}[\alpha^c] = (A / A[\alpha])^{-1}
$$
并且
$$
A^{-1}[\alpha^c, \alpha] = - (A / A[\alpha])^{-1} A[\alpha^c, \alpha]A[\alpha]^{-1} = -A[\alpha^c]^{-1}A[\alpha^c, \alpha] (A / A[\alpha^c])^{-1}
$$
___
##### Proof
我们首先证明结论对于分块矩阵
$$
A = \begin{pmatrix}
A_{11}  & A_{12} \\ 
A_{21} & A_{22}
\end{pmatrix}
$$
是成立的. 事实上
$$
A^{-1} = \begin{pmatrix}
(A / A_{22})^{-1} & -A^{-1}_{11}A_{12}(A / A_{11})^{-1} \\
-A_{22}^{-1}A_{21} (A / A_{22})^{-1} & (A / A_{11})^{-1}
\end{pmatrix}
$$
因此, 我们有$A^{-1}_{11} = (A / A_{22})^{-1}$并且$A^{-1}_{12} = -A^{-1}_{11}A_{12}(A / A_{11})^{-1}$. 这就证明了结论对于分块矩阵$\begin{pmatrix} A_{11}  & A_{12} \\ A_{21} & A_{22}\end{pmatrix}$是成立的. 对于任意的指标集$\alpha$, 我们可以重排$A$的行和列, 使得$A[\alpha]$是$A$的左上角的子矩阵. 根据[1.3. 子矩阵和顺序主子矩阵](#1.3.%20子矩阵和顺序主子矩阵)中的结论, 我们证明了结论对指标集$\alpha$也成立. 
#####
___


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
___
##### Proof
我们只需要考虑顺序子矩阵的情况, 设$A_{11}$是一个$r\times s$的矩阵, $A$的分块形式为
$$
A = \begin{pmatrix}A_{11} & A_{12} \\ A_{21} & A_{22}\end{pmatrix}
$$
再设
$$
A^{-1} = \begin{pmatrix}B_{11} & B_{12} \\ B_{21} & B_{22} \end{pmatrix}
$$
其中$B_{11}$是一个$s\times r$矩阵. 我们要证明的就是
$$
\mathrm{nullity}(A_{11}) = \mathrm{nullity}(B_{22})
$$
假设$A_{11}$的零化度为$k$, 如果$k\ge 1$, 设$X\in \mathbb{M}_{s, k}(\mathbb{F})$的列是$A_{11}$的零空间的一组基, 由于$A$非奇异, 因此
$$
A\begin{pmatrix}X \\ 0\end{pmatrix} = \begin{pmatrix}A_{11}X \\ A_{21}X\end{pmatrix} = \begin{pmatrix}0 \\ A_{21}X\end{pmatrix}
$$
是满秩的, 所以$A_{21}X$至少有$k$个线性无关的列. 但是
$$
\begin{pmatrix}
B_{12}(A_{21}X) \\ B_{22}(A_{21}X)
\end{pmatrix} = A^{-1} \begin{pmatrix}0 \\ A_{21}X\end{pmatrix} = A^{-1}A\begin{pmatrix}X \\ 0\end{pmatrix} = \begin{pmatrix}X \\ 0\end{pmatrix}
$$
从而$B_{22}(A_{21}X)=0$, 从而$\mathrm{nullity}(B_{22}) \ge  \mathrm{nullity}(A_{11})$, 同理可以得到$\mathrm{nullity}(A_{11}) \ge  \mathrm{nullity}(B_{22})$, 因此$\mathrm{nullity}(A_{11}) =  \mathrm{nullity}(B_{22})$.

#####
___

### 3.2. 主秩(Rank Principal)
假设$A\in \mathbb{M}_n(\mathbb{F})$并且$\mathrm{rank}\left(A\right) = r$, 如果$A$有一个非奇异的$r\times r$主子矩阵, 那么就称$A$是主秩的(rank principal). 

如果存在某个指标集$\alpha\subset \{1,2, \cdots, n\}$满足$|\alpha|=r$, 使得
$$
\mathrm{rank}\left(A[\alpha, \varnothing^c]\right) = \mathrm{rank}\left(A[\varnothing^c, \alpha]\right)= r
$$
那么$A$就是主秩的. 特别地, $A[\alpha]$还是非奇异的. 
___
##### Proof
考虑$A = \begin{pmatrix} A_{11} & A_{12} \\ A_{21} & A_{22}\end{pmatrix}$, 其中$A_{11}$是一个$r\times r$的方阵, 如果$\mathrm{rank}\left(A_{11}, A_{12}\right) = \mathrm{rank}\begin{pmatrix}A_{11} \\ A_{21}\end{pmatrix} =r$, 那么$A_{11}$是非奇异的. 用反证法, 假设$A_{11}$是奇异的, 那么$\mathrm{rank}\left(A_{11}\right)=k<r$, 且存在非奇异矩阵$S, T\in \mathbb{M}_r(\mathbb{F})$, 使得
$$
SA_{11}T = \begin{pmatrix}I_k & 0 \\ 0 & 0 \end{pmatrix} \implies \widehat{A} = \begin{pmatrix}S & 0 \\ 0 & I_{n-r} \end{pmatrix} A \begin{pmatrix}T & 0 \\ 0 & I_{n-r} \end{pmatrix} = \begin{pmatrix}\begin{pmatrix}I_k & 0 \\ 0 & 0\end{pmatrix} & SA_{12} \\ A_{21}T & A_{22}\end{pmatrix}
$$
因为$\widehat{A}$的秩是$r$, 并且第一个分块列和分块行的秩都是$r$, 根据第一个分块行的秩为$r$, 我们可以得到$SA_{12}$的第$r$行不为$0$, 但这意味着$A$的秩至少为$r+1$, 矛盾! 因此$A_{11}$是非奇异的. 

又因为我们可以通过初等行列变换将指标集$\alpha$变换到$\{1,2, \cdots, r\}$, 因此$A[\alpha]$是非奇异的.
#####
___

