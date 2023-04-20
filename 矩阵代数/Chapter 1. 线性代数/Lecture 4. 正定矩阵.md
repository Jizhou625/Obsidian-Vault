## 1. 基础知识
### 1.1. 定义
In mathematics, a symmetric matrix $M$ with real entries is positive-definite if the real number $\boldsymbol{z}^{\prime} \mathrm{M} \boldsymbol{z}$ is positive for every nonzero real column vector $\boldsymbol{z}$. More generally, a Hermitian matrix is positive-definite if the real number $\boldsymbol{z}^{\mathrm{H}} M \boldsymbol{z}$ is positive for any nonzero complex column vector $\boldsymbol{z}$. We can denote positive definite matrix $M$ as $M \succ 0$
### 1.2 判别法则
There are many criteria to determine whether a matrix is positive definite, the most common criteria are listed as follows
1. **特征值方法**: A real symmetric $k\times k$ matrix $A$ is positive definite if and only if all its eigenvalues are strictly positive real numbers(所有特征值都严格大于0)
2. **Sylvester's criterion**: A real symmetric $k\times k$ matrix $A$ is positive definite if and only if all the principal minors of matrix $A$ have posive determinants.(主子式的行列式大于0) 



## 2. 正定矩阵性质
1. **Schur分解的正定性**: 正定矩阵$P = \begin{pmatrix}A & B \\ B^{\top} & C \end{pmatrix}$的Schur分解$P / A = C - B^{\top}A^{-1}B$仍然是正定矩阵. 

2. **Minkowski不等式**: 若$A, B$是非零半正定, 则
   $$
   \sqrt[m]{ |A+B| }\ge \sqrt[m]{ |A| } + \sqrt[m]{ |B| }
   $$

3. **Fischer不等式**: 设$P = \begin{vmatrix}A & B \\ B^{\top} & C \end{vmatrix}$ 是正定矩阵, $A, C$是非空方阵, 则
  $$
  \begin{vmatrix}
  A & B \\
  B^{\top} & C
  \end{vmatrix}\le |A||C|
  $$
___
***Proof***: 
**Schur分解的正定性**: 考虑$\boldsymbol{a}^{\top} = (\boldsymbol{\alpha}^{\top}, \boldsymbol{\beta}^{\top})$, 我们有
$$
\boldsymbol{a}^{\top} P \boldsymbol{a} = \boldsymbol{\alpha}^{\top} A\boldsymbol{\alpha} + \boldsymbol{\beta}^{\top} C \boldsymbol{\beta} + 2 \boldsymbol{\alpha}^{\top} B \boldsymbol{\beta}\ge 0
$$
对$\boldsymbol{\alpha}$求导, 可以得到
$$
0 = \mathrm{D}_{\boldsymbol{\alpha}}(\boldsymbol{a}^{\top} P \boldsymbol{a}) = 2\boldsymbol{\alpha}^{\top} A + 2\boldsymbol{\beta}^{\top} B^{\top} 
$$
带入$\boldsymbol{\alpha}=-A^{-1}B \boldsymbol{\beta}$, 可以得到
$$
\boldsymbol{\beta}^{\top}  C \boldsymbol{\beta} -  \boldsymbol{\beta}^{\top} B^{\top} A^{-1}B\boldsymbol{\beta}\ge 0,\quad \forall \boldsymbol{\beta}
$$
因此Schur分解$P / A$仍然是正定矩阵
**Minkowski不等式**: 利用同时对角化定理, 因为$A, B$都是非零半正定矩阵, 因此存在可逆矩阵$P$, 使得$P^{\top}\Gamma P = A$, $P^{\top}\Lambda P = B$, 其中$\Gamma, \Lambda$都是对角矩阵. 因此, 我们有
$$
\sqrt[m]{ |A+B| } = \sqrt[m]{ |P^{\top} (\Gamma + \Lambda)P| } = \sqrt[m]{ |P|^2 }\sqrt[m]{|\Gamma + \Lambda | }\ge\sqrt[m]{ |A| } + \sqrt[m]{ |B| } 
$$
**Fsicher不等式**: 根据Schur分解, 我们可以得到
$$
\begin{vmatrix}
A & B \\
B^{\top} & C
\end{vmatrix} = |A||C - B^{\top} A^{-1}B|
$$
因为$C - B^{\top} A^{-1}B$是正定矩阵, $B^{\top}A^{-1}B$是正定矩阵, 并且$C$也是正定矩阵, 因此$|C - B^{\top}A^{-1}B|\le |C|$. 于是有
$$
\begin{vmatrix}
A & B \\
B^{\top} & C
\end{vmatrix}\le |A||C|
$$
