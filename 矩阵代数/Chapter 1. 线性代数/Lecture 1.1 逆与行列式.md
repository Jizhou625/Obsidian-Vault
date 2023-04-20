## 2. 行列式
### 2.1. 定义
$A$ is a $n \times n$ square matrix. Given a permutation $\sigma$. The signature of $\sigma$ is defincd to be $+1$ whenever the reordering given by $\sigma$ can be achicved by successively interchanging two entries an even number of times, and $-1$ whenever it can be achieved by an odd number of such interchangings.
$$
\operatorname{det}(A)=\sum_{\sigma \in S_n}\left(\operatorname{sgn}(\sigma) \prod_{i=1}^n a_{i, \sigma_i}\right)
$$
### 2.2. Cofactor Expansion
The minor $M_{i, j}$ is defined to be the determinant of the $(n-1) \times(n-1)$ matrix that results from $A$ by removing the $i$ th row and the $j$ th column. The expansion $(-1)^{i+j} M_{i, j}$ is known as a cofactor. For every $i$, one has the equality
$$
\operatorname{det}(A)=\sum_{j=1}^n(-1)^{i+j} a_{i j} M_{i j}
$$
### 2.3. Laplace Expansion
Let $A\left(\begin{array}{llll}i_1, & i_2, & \cdots, & i_k \\ j_1, & j_2, & \cdots, & j_k\end{array}\right)$ denote the determinant of $i_1, i_2, \cdots, i_k$ rows and $j_1, j_2, \cdots, j_k$ columns of matrix $A$.
$$
|A|=\sum_{1 \leq j_1<\cdots<j_k \leq n} (-1)^{i_1+\cdots+i_k+j_1+\cdots+j_k} A\left(\begin{array}{llll}
i_1, & i_2, & \cdots, & i_k \\
j_1, & j_2, & \cdots, & j_k
\end{array}\right)A\left(\begin{array}{llll}
i_1^{\prime}, & i_2^{\prime}, & \cdots, & i_{n-k}^{\prime} \\
j_1^{\prime}, & j_2^{\prime}, & \cdots, & j_{n-k}^{\prime}
\end{array}\right)
$$
这里$\{i_1<i_2<\cdots<i_k\}\bigcup \{i_1^{\prime}<i_2^{\prime}<\cdots<i_{n-k}^{\prime}\} = \{1,2,\cdots,n\}$ and $\{j_1<j_2<\cdots<j_k\}\bigcup \{j_1^{\prime}<j_2^{\prime}<\cdots<j_{n-k}^{\prime}\} = \{1,2,\cdots,n\}$

### 2.4. Inequalities 
1. **Cauchy-Schwartz不等式**: 若$A,B$都是$m\times n$矩阵, 则
   $$
   |A^{\top} B|^2 \le |A^{\top} A||B^{\top} B|
   $$

2. **Hadamard不等式**: 对于$m\times m$矩阵$A$, 有
   $$
   |A|\le \prod_{i=1}^m\left(\sum\limits_{j=1}^{m}|a_{ij}|^2 \right)^{ \frac{1}{2} }
   $$
   

---
***Proof***: 
**Cauchy-Schwartz不等式**: 
**Hadamard不等式**:


## 3. Schur Complement
### 3.1. 定义
Suppose $p, q$ are nonnegative integers, $A, B, C, D$ are respectively $p \times p, p \times q, q \times p$ and $q \times q$ matrices of complex numbers. Let
$$
M=\left[\begin{array}{ll}
A & B \\
C & D
\end{array}\right]
$$
So that $M$ is $(p+q) \times(p+q)$ matrix. If $D$ is invertible, then the Schur complement of the block $D$ of the matrix $M$ is the $p \times p$ matrix defined by
$$
M / D:=A-B D^{-1} C
$$
If $A$ is invertible, the Schur complement of the block $A$ of the matrix $M$ is the $q \times q$ matrix defined by
$$
M / A:=D-C A^{-1} B
$$
If $D$ is invertible, the LDU decomposition of $M$ will be
$$
M=\left[\begin{array}{cc}
A & B \\
C & D
\end{array}\right]=\left[\begin{array}{cc}
I_p & B D^{-1} \\
0 & I_q
\end{array}\right]\left[\begin{array}{cc}
A-B D^{-1} C & 0 \\
0 & D
\end{array}\right]\left[\begin{array}{cc}
I_p & 0 \\
D^{-1} C & I_q
\end{array}\right]
$$
Thus, the inverse of $M$ can be expressed involving $D^{-1}$ and the inverse of Schur's complement as
$$
M^{-1}=\left[\begin{array}{cc}
(M / D)^{-1} & -(M / D)^{-1} B D^{-1} \\
-D^{-1} C(M / D)^{-1} & D^{-1}+D^{-1} C(M / D)^{-1} B D^{-1}
\end{array}\right]
$$
### 3.2. Specific Case for $2\times 2$ Matrix
When $p$ and $q$ are both 1 (i.e. $A, B, C, D$ are all scalars). we get the familiar formula for the inverse of a $2 \times 2$ matrix
$$
M^{-1}=\frac{1}{A D-B C}\left[\begin{array}{cc}
D & -B \\
-C & A
\end{array}\right]
$$
### 3.3. Properties
**Schur Formula**: When $A$ is invertible, the determinant of $M$ is clearly seen to be given by
$$
|M|=|A|\left|D-C A^{-1} B\right|=|A||M / A|
$$
When $D$ is invertible
$$
|M|=\left|D\left\|A-B D^{-1} C|=| D\right\| M / D\right|
$$
**Guttman Rank Additivity Formula**: If $D$ is invertible, then the rank of $M$ is given by
$$
\operatorname{rank}(M)=\operatorname{rank} D+\operatorname{rank}\left(A-B D^{-1} C\right)
$$

