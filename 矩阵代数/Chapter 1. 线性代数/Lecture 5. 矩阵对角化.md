## 1. 相似对角化和相合对角化
### 1.1. 相似对角化
设$A, B$是$n$阶方阵, 若存在$n$阶可逆矩阵$P$, 使得$P^{-1}AP$和$P^{-1}BP$都是对角矩阵, 则称$A, B$可以同时相似对角化
### 1.2. 相合对角化
设$A, B$是$n$阶方阵, 若存在$n$阶可逆矩阵$P$, 使得$P^{\top}AP$和$P^{\top}BP$都是对角矩阵, 则称$A, B$可以同时相合对角化
### 1.3. 正交相合对角化
设$A, B$是$n$阶方阵, 若存在$n$阶正交矩阵$P$, 使得$P^{\top}AP$和$P^{\top}BP$都是对角矩阵, 则称$A, B$可以同时正交相合对角化



## 3. 同时对角化
**注**: 接下来, 我们说同时对角化, 如果不另外说明, 都是指同时相合对角化
### 3.1. 正定矩阵和对称矩阵的同时对角化
___
Suppose $A$ is a $n \times n$ positive definite matrix. $B$ is a symmetric matrix. Then there exists invertible matrix $G$ satisfies $G^{\prime} A G=I$ and $G^{\prime} B G=\operatorname{diag}\left\{\mu_1, \mu_2, \cdots, \mu_n\right\}$. Here, $\mu_1, \mu_2, \cdots, \mu_n$ is the root of $|\lambda A-B|$.
___
***Proof***: Since $A$ is $n \times n$ positive definite matrix, there exists $C \in G L_n(\mathbb{R})$, which satisfies $C^{\prime} A C=I$. Because $C^{\prime} B C$ is symmetric matrix, we know there exists an orthogonal matrix $T$ satisfies $T^{\prime}\left(C^{\prime} B C\right) T=\operatorname{diag}\left\{\mu_1, \mu_2, \cdots, \mu_n\right\}$. Here $\mu_i$ is the root of function
$$
0=\left|\lambda I-C^{\prime} B C\right|=\left|\lambda I-A^{-1} B\right|=|\lambda A-B|
$$
Then, $G=C T$ is what we want.

### 3.2. 半正定矩阵的同时对角化
___
Suppose $A, B$ are $n \times n$ semi-positive definite matrix. Then there exists an invertible matrix $P, P^{\prime} A P$ and $P^{\prime} B P$ are diagonal matrix.
___
***Proof***: Since $A$ and $B$ are semi-positive definite matrix, we know that $A+B$ is semi-positive definite matrix. We know that there exists invertible matrix $M$ which satisfies $M^{\prime}(A+B) M=$ $\left(\begin{array}{cc}I_r & 0 \\ 0 & 0\end{array}\right)$. Notice that $M^{\prime} A M$ and $M^{\prime} B M$ are also semi-positive definite matrices. As a result, $M^{\prime} A M=\left(\begin{array}{cc}H_r & 0 \\ 0 & 0\end{array}\right)$ where $H_r$ is a symmetric matrix. Then there exists an orthogonal matrix $T$ which satisfies 
$$
T^{\prime} H_r T=\operatorname{diag}\left\{\lambda_1, \lambda_2, \cdots, \lambda_n\right\}
$$
Let $P=M\left(\begin{array}{cc}T & 0 \\ 0 & I_{n-r}\end{array}\right)$. We can find that $P^{\prime} A P$ and $P^{\prime} B P$ are diagonal matrix.

### 3.3. 可交换矩阵的同时对角化
___
设$A, B$是对称矩阵, 则$A, B$可以同时正交相合对角化的充分必要条件是$A, B$可交换, 也就是说, $AB=BA$
___
***Proof***: 先证明必要性
$$
P^{\top} ABP = \mathrm{diag}\{\lambda_1, \cdots, \lambda_n\}\mathrm{diag}\{\mu_1, \cdots, \mu_n\} = P^{\top} BAP \implies AB=BA
$$
再证明充分性: 先对$A$做正交合同对角化得到$P^{\top}AP = \Lambda$. 其中$\Lambda$的对角元素是按照大小排序的$A$的特征值, 考虑矩阵$C = P^{\top}BP$,  由于$AB$可交换, 因此$\Lambda C = C\Lambda$. 假设$\Lambda$可以写成分块
$$
\mathrm{diag}\{\lambda_1I_1, \lambda_2I_2, \cdots, \lambda_k I_k \}
$$ 
由此可以得到$C$是一个分块对角矩阵, 于是$C = \mathrm{diag}\{C_1, C_2,\cdots,C_k\}$, 对其中每一个分块做正交合同对角化, 记录
$$
Q = \mathrm{diag}\{Q_1, Q_2,\cdots,Q_k\}
$$ 
设$T = PQ$, 不难验证得到, $T^{\top}AT$和$T^{\top}BT$都是对角矩阵. 因此充分性成立