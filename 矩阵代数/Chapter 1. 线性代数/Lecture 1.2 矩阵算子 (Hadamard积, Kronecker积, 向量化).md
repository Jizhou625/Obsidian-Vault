## 1. 矩阵的直和与Hadamard积
### 1.1 直和
$m\times m$矩阵$A$和$n\times n$矩阵$B$的直和记作$A\oplus B$, 它是一个$(m+n)\times (m+n)$矩阵, 定义为
$$
A \oplus B = \begin{pmatrix}
A & O_{m\times n} \\
O_{n\times m} & B
\end{pmatrix}
$$
递归的, 可以定义多个矩阵的直和
### 1.2 直和的性质
1. 若$A, B$是$m\times m$矩阵, 且$C, D$为$n\times n$矩阵, 则
  $$
  \begin{align}
  (A\pm B)\oplus (C\pm D) &= (A\oplus C)\pm (B\oplus D) \\
  (A\oplus C)(B\oplus D) &= AB\oplus CD
  \end{align}
  $$

2. 若$A,B, C$分别是$m\times m, n\times n, p\times p$矩阵, 则
   $$
   A\oplus (B\oplus C)=(A\oplus B)\oplus C=A\oplus B\oplus C
   $$
   
3. 若$A_{m\times m}$和$B_{n\times n}$均为正交矩阵, 则$A\oplus B$是$(m+n)\times (m+n)$正交矩阵

4. 矩阵直和的转置, 共轭转置与逆矩阵
  $$
  \begin{align}
  (A\oplus B)^{\top} &=A^{\top}  \oplus B^{\top}  \\
  (A\oplus B)^{\mathrm{H}} &= A^{\mathrm{H}}  \oplus B^{\mathrm{H}} \\
  (A\oplus B)^{-1} &= A^{-1}  \oplus B^{-1}
  \end{align}
  $$
  
5. 矩阵直和的迹, 秩和行列式
  $$
  \begin{aligned}
  \operatorname{tr}\left(\bigoplus_{i=0}^{N-1} \boldsymbol{A}_i\right) & =\sum_{i=0}^{N-1} \operatorname{tr}\left(\boldsymbol{A}_i\right) \\
  \operatorname{rank}\left(\bigoplus_{i=0}^{N-1} \boldsymbol{A}_i\right) & =\sum_{i=0}^{N-1} \operatorname{rank}\left(\boldsymbol{A}_i\right) \\
  \operatorname{det}\left(\bigoplus_{i=0}^{N-1} \boldsymbol{A}_i\right) & =\prod_{i=0}^{N-1} \operatorname{det}\left(\boldsymbol{A}_i\right)
  \end{aligned}
  $$
### 1.3. Hadamard积
$m\times n$矩阵$A$和$m\times n$矩阵$B$的Hadamard积记作$A\odot B$, 它仍然是一个$m\times n$矩阵, 其元素定义为两个矩阵的对应元素的乘积, 即Hadamard积是一映射$\mathbb{R}^{m\times n}\times \mathbb{R}^{m\times n}\mapsto \mathbb{R}^{m\times n}$
$$
A\odot B = \begin{pmatrix}
a_{11}b_{11} & a_{12}b_{12} & \cdots & a_{1n}b_{1n} \\
a_{21}b_{21} & a_{22}b_{22} & \cdots & a_{2n}b_{2n}  \\
\vdots & \vdots & & \vdots \\
a_{m1}b_{m1} & a_{m2}b_{m2} & \cdots & a_{mn}b_{mn}  \\
\end{pmatrix}
$$

### 1.4. Hadamard积的性质
1. **交换率、结合律和分配律**: 
  $$
  \begin{align}
  A\odot B &= B\odot A \\
  A\odot(B\odot C) &= (A\odot B)\odot C \\
  A\odot (B\pm C) &= A\odot B \pm A\odot C \\
  (A+B)\odot (C+D) &= A\odot C + A\odot D + B\odot C + B\odot D
  \end{align}
  $$

2. 若$AB^{\top}$为正方矩阵, 则$\mathrm{tr}\left\{AB^{\top}\right\}=\boldsymbol{1}^{\top}(A\odot B)\boldsymbol{1}$

3. 若$A, B, D$为$m\times m$矩阵且$D$为对角矩阵, 则$(DA)\odot(BD)=D(A\odot B) D$

4. 若$A, B, C$为$m\times n$矩阵, 则
   $$
   \mathrm{tr}\left\{A^{\top} (B\odot C)\right\}=\mathrm{tr}\left\{(A^{\top} \odot B^{\top} )C\right\}
   $$

5. **正定性(Schur积定理)**: 若$m\times m$矩阵$A, B$是正定(或半正定)的, 则它们的Hadamard积$A\odot B$也是正定(或半正定)的

6. **Oppenheim不等式**: 令$A, B$是$n\times n$半正定矩阵, 则
   $$
   |A\odot B|\ge a_{11}a_{22}\cdots a_{nn}|B|
   $$
    等号成立当且仅当$B$是一个对角矩阵. 

7. **Hadamard积的秩不等式**: 令$A$和$B$是$n\times n$矩阵, 则
   $$
   \mathrm{rank}(A\odot B)\le \mathrm{rank}(A)\mathrm{rank}(B)
   $$
   
___
***Proof***: 我们只证明加粗部分的结论
**Schur积定理**:  For any matrices $M$ and $N$, the Hadamard product $M \circ N$ considered as a bilinear form acts on vectors $a, b$ as
$$
a^{\top} (M \odot N) b=\operatorname{tr}\left(M^{\top} \operatorname{diag}\left(a\right) N \operatorname{diag}(b)\right)
$$
where $\operatorname{tr}$ is the matrix trace and $\operatorname{diag}(a)$ is the diagonal matrix having as diagonal entries the elements of $a$.
Suppose $M$ and $N$ are positive definite. We can consider their square-roots $C_{M}^{\top}C_M$ and $C_{N}^{\top}C_N$ and write
$$
\begin{align}
\operatorname{tr}\left(M^{\top} \operatorname{diag}\left(a\right) N \operatorname{diag}(b)\right)&=\operatorname{tr}\left(C_{M}^{\top}C_M \operatorname{diag}\left(a\right) C_{N}^{\top}C_N\operatorname{diag}(b)\right) \\
&=\operatorname{tr}\left(C_M\operatorname{diag}\left(a\right) C_{N}^{\top}C_N\operatorname{diag}(b) C_{M}^{\top}\right)
\end{align}
$$
Then, for $a=b$, this is written as $\operatorname{tr}\left(A^{\top} A\right)$ for $A=C_{N}\operatorname{diag}(a) C_{M}^{\top}$ and thus is strictly positive for $A \neq 0$, which occurs if and only if $a \neq 0$. This shows that $(M \odot N)$ is a positive definite matrix.
**Oppenheim不等式**: Consider about partition $A=\left(\begin{array}{ll}a_{11} & A_{12} \\ A_{21} & A_{22}\end{array}\right)$ and partition $B=\left(\begin{array}{ll}b_{11} & B_{12} \\ B_{21} & B_{22}\end{array}\right)$, where $A_{22}, B_{22}$ is of order $n-1$. We will use induction on the order of $A$ and $B$. Since $n=1$ is obvious, we assume $n>1$ and the result holds for positive definite matrices of order $K<n$. Let $E = \dfrac{1}{b_{11}}B_{21}B_{12}$, then
$$
\begin{aligned}
|A \odot B| & =\begin{vmatrix}
a_{11}b_{11} & A_{12} \odot B_{12} \\
A_{21}\odot B_{21} & A_{22}\odot B_{22}
\end{vmatrix} \\
&= a_{11}b_{11}|(A\odot B) / (a_{11}b_{11})|  \\
& =a_{11} b_{11} |A_{22} \odot\left(B /b_{11}\right)+\left(A / a_{11}\right) \odot E|
\end{aligned} 
$$
Next, we prove that if $B$ is positive definite, then $B / b_{11}$ is positive definite. For any $(n-1)\times 1$ vector $\boldsymbol{\alpha}$ and any scalar value $a$, we have
$$(a, \boldsymbol{\alpha}^{\top} ) \left(\begin{array}{ll}b_{11} & B_{12} \\ B_{21} & B_{22}\end{array}\right) \begin{pmatrix}
a \\
\boldsymbol{\alpha}
\end{pmatrix} = a^2 b_{11} + 2 a \boldsymbol{\alpha}^{\top} B_{21}+ \boldsymbol{\alpha}^{\top} B_{22}\boldsymbol{\alpha}\geq 0,\quad  \forall a$$
minimize for $a$, we can get that when $a = -\dfrac{\boldsymbol{\alpha}^{\top}B_{21}}{b_{11}}$
$$
\boldsymbol{\alpha}^{\top} B_{22} \boldsymbol{a} - \dfrac{1}{b_{11}}\boldsymbol{\alpha}^{\top} B_{21}B_{12}\boldsymbol{\alpha}\geq 0 
$$
which means that $B / b_{11}$ is positive definite. Using Schur Product theorem, we know that $A_{22} \odot\left(B / b_{11}\right)$ is positive definite, and $\left(A / a_{11}\right) \odot E$ is also positive definite for the same reason. Minkowski's inequality allows us to say
$$
|A_{22} \odot\left(B /b_{11}\right)+\left(A / a_{11}\right) \odot E|\ge |A_{22} \odot\left(B /b_{11}\right)| + |\left(A / a_{11}\right) \odot E|
$$
Using our inductive hypothesis and the fact that $|(A / a_{11} )\odot E| \geq 0$, we have
$$
\begin{aligned}
|A \odot B | & \geq a_{11} b_{11} |A_{22} \odot (B / b_{11})| \\
& \geq a_{11} b_{11}\left[a_{22} \cdots a_{n n} |B / b_{11}|\right] \\
& =\left(\prod_{i=1}^n a_{ii}\right) |B| .
\end{aligned}
$$
Next, suppose that equality holds; i.e., $|A \odot B|=a_{11} \cdots a_{n n} |B|$. Then we must have $(A / a_{11} )\odot E=0$. Since the result is invariant under simultaneous permutational similarity of $A$ and $B$. Then we know that all off-diagonal entries of $B$ are zero, and $B$ is a diagonal matrix.If $B$ is diagonal, then it is obvious that
$$
|A \odot B| =\left(\prod_{i=1}^n a_{ii}\right) |B|
$$
**Hadamard积的秩不等式**: 设$\mathrm{rank}(A) = r_1, \mathrm{rank}(B)=r_2$, 根据秩分解定理
$$
A = \boldsymbol{\alpha}_{11}\boldsymbol{\beta}_{11}^{\top} + \boldsymbol{\alpha}_{12}\boldsymbol{\beta}_{12}^{\top}+ \cdots + \boldsymbol{\alpha}_{1r_1}\boldsymbol{\beta}_{1r_1}^{\top}
$$
$$
B = \boldsymbol{\alpha}_{21}\boldsymbol{\beta}_{21}^{\top} + \boldsymbol{\alpha}_{22}\boldsymbol{\beta}_{22}^{\top}+ \cdots + \boldsymbol{\alpha}_{2r_2}\boldsymbol{\beta}_{2r_2}^{\top}
$$
于是
$$
\begin{align}
A\odot B &=(\boldsymbol{\alpha}_{11}\boldsymbol{\beta}_{11}^{\top} + \boldsymbol{\alpha}_{12}\boldsymbol{\beta}_{12}^{\top}+ \cdots + \boldsymbol{\alpha}_{1r_1}\boldsymbol{\beta}_{1r_1}^{\top}) \odot (\boldsymbol{\alpha}_{21}\boldsymbol{\beta}_{21}^{\top} + \boldsymbol{\alpha}_{22}\boldsymbol{\beta}_{22}^{\top}+ \cdots + \boldsymbol{\alpha}_{2r_2}\boldsymbol{\beta}_{2r_2}^{\top}) \\
&=\sum\limits_{i=1}^{r_1} \sum\limits_{j=1}^{r_2}  (\boldsymbol{\alpha}_{1i}\boldsymbol{\beta}_{1i}^{\top} )\odot (\boldsymbol{\alpha}_{2i}\boldsymbol{\beta}_{2i}^{\top}) \\
& = \sum\limits_{i=1}^{r_1} \sum\limits_{j=1}^{r_2} (\boldsymbol{\alpha}_{1i}\odot \boldsymbol{\alpha}_{2j})(\boldsymbol{\beta}_{1i}^{\top} \odot\boldsymbol{\beta}_{2j}^{\top} ) \\
\end{align}
$$
这个加法表达式中每一项的秩都小于等于$1$, 因此我们有
$$
\mathrm{rank}(A\odot B)\le \mathrm{rank}(A)\mathrm{rank}(B)
$$
___



## 2. Kronecker积
### 2.1. 定义
$m\times n$矩阵$A$和$p\times q$矩阵$B$的Kronecker积记为$A\otimes B$, 是一个$mp\times nq$, 定义为
$$
A\otimes B = \begin{pmatrix}
a_{11}B & a_{12}B & \cdots & a_{1n}B \\
a_{21}B & a_{22}B & \cdots & a_{2n}B \\
\vdots&\vdots& & \vdots \\
a_{m1}B & a_{m2}B & \cdots & a_{mn}B
\end{pmatrix}
$$
Kronecker积也称为直积或者张量积
### 2.2. 交换矩阵
**定义**: 对于一个$m\times n$矩阵$A$, 向量$\mathrm{vec}(A)$和向量$\mathrm{vec}(A^{\top})$含有相同的元素, 但排列次序不同, 因此, 存在唯一的一个$mn\times mn$置换矩阵, 可以将一个矩阵的向量化$\mathrm{vec}(A)$变换为其转置矩阵的向量化$\mathrm{vec}(A^{\top})$, 这一置换矩阵称为交换矩阵(commutation matrix), 记为$K_{mn}$, 定义为
$$
K_{mn}\mathrm{vec}(A) = \mathrm{vec}(A^{\top} )
$$
交换矩阵具有下列的性质
1. $K_{mn}\mathrm{vec}(A) = \mathrm{vec}(A^{\top})$和$K_{nm}\mathrm{vec}(A^{\top}) = \mathrm{vec}(A)$, 其中$A$为$m\times n$矩阵

2. $K_{mn}^{-1} = K_{nm}$

3. $K_{mn}^{\top}=K_{nm}$

4. $K_{mn}$可以表示为基本向量的Kronecker积
   $$
   K_{mn}=\sum_{j=1}^n(\boldsymbol{e}_j^{\top} \otimes I_m\otimes \boldsymbol{e}_j)
   $$

5. 交换矩阵的秩为$\mathrm{rank}(K_{mn}) = 1+d(m-1, n-1)$, 其中$d(m,n)$是$m$和$n$之间的最大公约数
### 2.3. Kronecker积的性质
1. $m$维与$n$维两个单位矩阵的Kronecker积为$mn$维单位矩阵, 即$I_m\otimes I_n = I_{m\times n}$

2. 对于矩阵$A_{m\times n}$, $B_{n\times k}, C_{l\times p}, D_{p\times q}$, 有
   $$
   (AB)\otimes (CD) = (A\otimes C)(B\otimes D)
   $$

3. 对于矩阵$A_{m\times n}, B_{p\times q}, C_{p\times q}$, 有
  $$
  \begin{align}
  A \otimes (B\pm C) &= A\otimes B \pm A\otimes C \\
  (B\pm C) \otimes A &= B\otimes A \pm C \otimes A
  \end{align} 
  $$
  对于矩阵$A_{m\times n}, B_{m\times n}, C_{p\times q}, D_{p\times q}$, 有
  $$
  (A+B)\otimes (C+D) = A\otimes C + A\otimes D+B\otimes C+B\otimes D
  $$

4. **转置**: $(A\otimes B)^{\top} = A^{\top}\otimes B^{\top}$, $(A\otimes B)^{\mathrm{H}} = A^{\mathrm{H}}\otimes B^{\mathrm{H}}$

5. **逆矩阵**: $(A\otimes B)^{-1} = A^{-1}\otimes B^{-1}$

6. **秩**: $\mathrm{rank}(A\otimes B) = \mathrm{rank}(A)\mathrm{rank}(B)$

7. **行列式**: $|A_{n\times n}\otimes B_{m\times m}|= |A|^m |B|^n$

8. **迹**: $\mathrm{tr}\left\{A\otimes B\right\}=\mathrm{tr}\left\{A\right\}\mathrm{tr}\left\{B\right\}$

9. **交换矩阵**: 设$A\in \mathbb{C}^{m\times n}, B\in \mathbb{C}^{p\times q}, \boldsymbol{b}\in \mathbb{C}^p$, 则
  $$
  \begin{align}
  K_{pm}(A\otimes B)&=(B\otimes A)K_{qn} \\
  K_{pm}(A\otimes B)K_{nq} &= B\otimes A \\
  K_{pm}(A\otimes \boldsymbol{b}) &= \boldsymbol{b}\otimes A \\
  K_{mp}(\boldsymbol{b}\otimes A) &= A\otimes \boldsymbol{b}
  \end{align}
  $$




## 3. 向量化
### 3.1. 向量化算子
矩阵$A\in \mathbb{R}^{m \times n}$的向量化$\mathrm{vec}(A)$是一个线性变换, 它将矩阵$A$的元素按照列堆叠, 排列成一个$mn\times 1$的向量
$$
\mathrm{vec}(A) = (a_{11}, \cdots, a_{m1}, \cdots, a_{1n}, \cdots, a_{mn})^{\top}
$$

### 3.2. 向量化算子的性质
1. **转置矩阵的向量化**: $\mathrm{vec}(A^{\top})=K_{mn}\mathrm{vec}(A)$, 其中$A\in \mathbb{C}^{m\times n}$

2. **线性性**: $\mathrm{vec}(A+B) = \mathrm{vec}(A)+\mathrm{vec}(B)$

3. **迹和向量化**: 
  $$
  \begin{align}
  \mathrm{tr}\left\{A^{\top} B\right\} &= (\mathrm{vec}(A))^{\top} \mathrm{vec}(B) \\
  \mathrm{tr}\left\{A^{\mathrm{H}}B\right\} & = (\mathrm{vec}(A))^{\mathrm{H}} \mathrm{vec}(B) \\
  \mathrm{tr}\left\{ABC\right\} &= (\mathrm{vec}(A))^{\top} (I_p\otimes B)\mathrm{vec}(C) \\
  \mathrm{tr}\left\{ABCD\right\} &= (\mathrm{vec}(D^{\top} ))^{\top} (C^{\top} \otimes A)\mathrm{vec}(B) = (\mathrm{vec}(D))^{\top} (A\otimes C^{\top} )\mathrm{vec}(B^{\top} )
  \end{align}
  $$

4. **Hadamard积**: $\mathrm{vec}(A\odot B) = \mathrm{vec}(A)\odot \mathrm{vec}(B) = \mathrm{diag}(\mathrm{vec}(A))\mathrm{vec}(B)$

5. **向量化转Kronecker积**: 设有矩阵$A_{m\times p}, B_{p\times q}$和$C_{q\times n}$
  $$
  \begin{align}
  \mathrm{vec}(ABC)&=(C^{\top} \otimes A)\mathrm{vec}(B)  \\
  \mathrm{vec}(ABC)&=(I_q\otimes AB)\mathrm{vec}(C)=(C^{\top} B^{\top} \otimes I_m)\mathrm{vec}(A) \\
  \mathrm{vec}(AB) &= (I_p\otimes A)\mathrm{vec}(B) =(B^{\top} \otimes I_m)\mathrm{vec}(A)  \\
  \end{align}
  $$

6. **Kronecker积的向量化**: 设$X\in \mathbb{R}^{p\times m}$和$Y\in \mathbb{R}^{n\times q}$, 则
   $$
   \mathrm{vec}(X\otimes  Y)= (I_m\otimes K_{qp}\otimes I_n)(\mathrm{vec}X\otimes \mathrm{vec}Y)
   $$
   
___
