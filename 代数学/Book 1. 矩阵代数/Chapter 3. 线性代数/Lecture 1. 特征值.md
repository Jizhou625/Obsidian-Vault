## 1. 特征值与特征向量
### 1.1. 特征值与特征向量

若非零向量$\boldsymbol{u}$作为线性算子$\mathcal{L}$的输入时, 所产生的输出与输入只相差一个常数因子$\lambda$, 即
$$
\mathcal{L}(\boldsymbol{u}) = \lambda \boldsymbol{u}, \quad \boldsymbol{u}\neq 0
$$
则称向量$\boldsymbol{u}$是线性算子$\mathcal{L}$的特征向量, 称标量$\lambda$为线性算子$\mathcal{L}$的特征值. 

当线性算子为矩阵时, 我们就得到了矩阵的特征值与特征向量. 写成
$$
(A-\lambda I)\boldsymbol{u} = 0,\quad \boldsymbol{u}\neq 0
$$

$A$的所有特征值$\lambda$组成的集合称为$A$的谱, 记为$\sigma(A)$. 

设$A\in \mathbb{M}_n$, $A$的谱半径定义为
$$
\rho(A) = \max\{|\lambda|\mid \lambda\in \sigma(A)\}
$$

### 1.2. 二次型极值观点下的特征值
对于给定的实对称矩阵$A\in \mathbb{M}_n(\mathbb{R})$
$$
\max \boldsymbol{x}^{\top} A\boldsymbol{x}, \quad \boldsymbol{x}\in \mathbb{R}^n, \ \boldsymbol{x}^{\top}\boldsymbol{x} = 1
$$
解决这样一个有限制条件的最优化问题的常规方法是引入Lagrange算子
$$
L = \boldsymbol{x}^{\top} A\boldsymbol{x} + \lambda(1-\boldsymbol{x}^{\top}\boldsymbol{x})
$$
取极值的必要条件是
$$
0 = \nabla_{\boldsymbol{x}}L = 2(A\boldsymbol{x} - \lambda \boldsymbol{x}) 
$$
这里的$\lambda$就是我们上面定义的特征值. 

### 1.3. 多项式函数的特征值
设$p(t)$是给定的$k$次多项式, 如果$\lambda$是$A\in \mathbb{M}_n$的特征值, $\boldsymbol{x}$是其对应的一个特征向量, 那么$p(\lambda)$就是$p(A)$的一个特征值, $\boldsymbol{x}$是其对应的一个特征向量. 反过来, 如果$k\ge 1$且$\mu$是$p(A)$的一个特征值, 那么就存在$A$的某个特征值$\lambda$使得$\mu = p(\lambda)$. 
___
##### Proof
正向的结论显然成立, 我们只要证明反过来的结论. 如果$\mu$是$p(A)$的一个特征值, 那么$p(A) - \mu I$是奇异的. 考虑多项式$q(t) = p(t) - \mu$. 其次数$k\ge 1$, 我们可以将其分解为
$$
q(t) = (t-\beta_1)\cdots (t-\beta_k)
$$
又因为$q(A)$是奇异的, 因此$q(A)$的某个因子$A -\beta_j I$是奇异的, 这就意味着$\beta_j$是$A$的特征值. 因此$\mu=p(\beta_j)$. 
#####
___

### 1.4. 特征向量的多项式构造
给定$A\in \mathbb{M}_n$, 那么$A$有特征值, 事实上, 对每个给定的非零的$\boldsymbol{y}\in \mathbb{C}^n$, 存在一个至多$n-1$次多项式$g(t)$, 使得$g(A)\boldsymbol{y}$是$A$的特征向量. 
___
##### Proof
设$m$是使得向量$\boldsymbol{y}, A\boldsymbol{y}, A^2\boldsymbol{y}, \cdots, A^m\boldsymbol{y}$线性相关的最小的整数$m$. 显然$m\ge 1$, 且有$m\le n$, 设$a_0, a_1, \cdots, a_m$是不全为零的纯量, 它们使得
$$
p(A)\boldsymbol{y} = a_m A^m\boldsymbol{y} + a_{m-1}A^{m-1}\boldsymbol{y} + \cdots + a_1A\boldsymbol{y} + a_0\boldsymbol{y} = 0
$$
如果$a_m=0$, 这就意味着$\boldsymbol{y}, A\boldsymbol{y}, \cdots , A^{m-1}\boldsymbol{y}$是线性相关的, 这和$m$的最小性矛盾. 于是$a_m\neq 0$, 于是我们可以不妨设这个多项式是首$1$的, 也就是说$a_m=1$. 这样, $0$是$p(A)$的一个特征值, $\boldsymbol{y}$是其对应的一个特征向量. 根据[2.3. 多项式函数的特征值](#2.3.%20多项式函数的特征值),我们有$p(t) = 0$的某个零点有一个是$A$的特征值. 不妨设这个特征值为$\lambda$. 我们有分解
$$
p(t) = (t-\lambda)q(t)
$$
其中$q(t)$是一个$m-1$次多项式, 并且$q(A)\boldsymbol{y}\neq 0$. 但
$$
0 = p(A)\boldsymbol{y} = (A - \lambda I)(q(A)\boldsymbol{y})
$$
因此我们有$q(A)\boldsymbol{y}$是$A$对应于$\lambda$的特征向量.
#####
___

### 1.5. 特征向量的线性无关性
设$\lambda_1, \lambda_2, \cdots, \lambda_k$是$A\in \mathbb{M}_n$的$k\ge 2$个不同的特征值, 又假设对每个$i=1,2, \cdots, k$, $\boldsymbol{x}^{(i)}$是与$\lambda$相伴的特征向量. 那么$\boldsymbol{x}^{(1)}, \boldsymbol{x}^{(2)}, \cdots, \boldsymbol{x}^{(k)}$是线性无关的.
___
##### Proof
用反证法, 假设存在不全为$0$的纯量$a_1, a_2, \cdots, a_k$, 使得$a_1\boldsymbol{x}^{(1)} + a_2\boldsymbol{x}^{(2)} +\cdots + a_k\boldsymbol{x}^{(k)}=0$. 设
$$
B_1 = (A - \lambda_2I)(A - \lambda_3I)\cdots (A - \lambda_kI)
$$
由于对每个$i=1,2,\cdots, n$, $\boldsymbol{x}^{(i)}$是与特征值$\lambda_i$相伴的特征向量, 因此我们有
$$
B_1\boldsymbol{x}^{(i)} = (\lambda_i - \lambda_2)(\lambda_i - \lambda_3)\cdots (\lambda_i - \lambda_k)\boldsymbol{x}^{(i)}
$$
当$i\neq 1$时, $B_1\boldsymbol{x}^{(i)} = 0$, 从而
$$
0= B_1(a_1\boldsymbol{x}^{(1)} + a_2\boldsymbol{x}^{(2)} +\cdots + a_k\boldsymbol{x}^{(k)}) = a_1B_1\boldsymbol{x}^{(1)}
$$
由于$B_1\boldsymbol{x}^{(1)}\neq 0$, 因此$\alpha_1=0$, 重复上面的讨论, 可以得到$a_1 = a_2 = \cdots = a_k = 0$. 这就得到了矛盾! 因此$\boldsymbol{x}^{(1)}, \boldsymbol{x}^{(2)}, \cdots, \boldsymbol{x}^{(k)}$是线性无关的.
#####
___

## 2. 代数重数与几何重数
### 2.1. 特征方程
设$A\in \mathbb{M}_n$, $A$的特征多项式定义为
$$
p_A(t) = \det(tI - A)
$$
我们把方程$p_A(t)=0$称为$A$的特征方程.

每一个$A$的特征多项式的次数都是$n$, 并且
$$
p_A(t) = t^n - \mathrm{tr}\left(A\right) t^{n-1} + \cdots + (-1)^n\det(A)
$$
此外, $p_A(\lambda)=0$当且仅当$\lambda\in \sigma(A)$, 故而$\sigma(A)$至多包含$n$个复数. 

### 2.2 代数重数和几何重数
1. **代数重数**: 设$A\in \mathbb{M}_n$, $A$的特征值$\lambda$的代数重数是指它作为特征多项式$p_A(t)$的零点的重数. 
2. **几何重数**: 设$A\in \mathbb{M}_n$, $A$的特征值$\lambda$的几何重数是指与$\lambda$相伴的特征空间的维数.
3. **半单**: 一个特征值称为半单特征值, 如果其代数重数等于其几何重数. 

### 2.3. 代数重数和几何重数的关系
给定$A\in \mathbb{M}_n$以及$\lambda\in \mathbb{C}$, 又设$k\ge 1$是给定的正整数. 
1. $\lambda$是$A$的几何重数至少为$k$的特征值
2. 对每个$m=n-k+1, \cdots, n$, $\lambda$是$A$的每一个$m\times m$主子矩阵的特征值. 
3. $\lambda$是$A$的代数重数至少为$k$的特征值

那么$1\implies 2\implies 3$
___
##### Proof
对于$1\implies 2$, 假设$\lambda$是$A$的几何重数至少为$k$的特征值, 这就意味着$\mathrm{rank}\left(A - \lambda I\right) \le n-k$. 假设$m>n-k$, 那么$A - \lambda I$的每个$m\times m$子式都为$0$. 特别地, $A- \lambda I$的每个主子矩阵都是奇异的. 因此, $\lambda$是$A$的每个$m\times m$主子矩阵的特征值.

对于$2\implies 3$, 假设对每个$m\ge n-k+1$, $\lambda$是$A$的每个$m\times m$主子矩阵的特征值. 那么$A - \lambda I$的每个阶至少为$n-k+1$的主子式都是$0$, 
#####
___

### 2.4. 有亏的和有损的
设$A\in \mathbb{M}_n$. 我们称$A$是有亏的, 如果$A$的某个特征值的几何重数严格小于其代数重数. 我们称$A$是有亏的(defective), 如果$A$的每个特征值的几何重数都与它的代数重数相同, 那么我们就称$A$是无亏的(nondefective). 如果$A$的每个特征值的几何重数都是$1$, 我们称$A$是无损的(nonderogatory); 否则就称为有损的(derogatory).
## 3. 相似性
### 3.1. 相似性
设$A, B\in \mathbb{M}_n$, 如果存在一个非奇异矩阵$S\in \mathbb{M}_n$使得
$$
B = S^{-1}AS
$$
则称$A$与$B$相似, 记为$A\sim B$. 相似性是$\mathbb{M}_n$上的一个等价关系.

### 3.2. 基变换与相似性
如果$\mathcal{B}$是向量空间$V$的一组给定的基, $T$是$V$上一个给定的线性变换, 如果$A={}_{\mathcal{B}}[T]_{\mathcal{B}}$是$T$的$\mathcal{B}$的基表示, 则$T$的所有可能基表示的集合是
$$
\{{}_{\mathcal{B}_1}[I]_{\mathcal{B}}{}_{\mathcal{B}}[T]_{\mathcal{B}}{}_{\mathcal{B}}[I]_{\mathcal{B}_1}\mid \mathcal{B}_1 \mathrm{\ is\ basis\ of\ }V\} = \{S^{-1}AS\mid S\in \mathbb{M}_{n}(\mathbb{F}) \mathrm{\ is\ invertible}\}
$$
这恰好是所有与给定的矩阵$A$相似的矩阵的集合. 

### 3.3. 相似与特征值
设$A, B\in \mathbb{M}_n$, 如果$B\sim A$, 那么$A$和$B$有相同的特征多项式. 也就有相同的特征值. 

### 3.4. 相似对角化
如果$A\in \mathbb{M}_n$与一个对角矩阵相似, 那么就说$A$是可对角化的.

$A$与一个形如$\begin{pmatrix}\Lambda_{k\times k} & C \\  0 & D\end{pmatrix}$的分块矩阵相似, 当且仅当在$\mathbb{C}^n$中存在$k$个线性无关的向量, 它们中的每一个都是$A$的特征向量. 特别地, 矩阵$A$是可以对角化的, 当且仅当存在$n$个线性无关的向量, 它们中的每一个都是$A$的特征向量. 并且, 我们有$\Lambda$的对角元素是$A$的特征值.
___
##### Proof
先证明$k=n$时结论成立, 事实上如果有$\mathbb{C}^n$的一组基$\{\boldsymbol{x}^{(1)}, \cdots, \boldsymbol{x}^{(n)}\}$, 满足对每个$i=1,2, \cdots, n$有$A\boldsymbol{x}^{(i)} = \lambda_i \boldsymbol{x}^{(i)}$. 设$\Lambda = \mathrm{diag}\left\{\lambda_1, \cdots, \lambda_n\right\}$以及$S = (\boldsymbol{x}^{(1)}, \cdots, \boldsymbol{x}^{(n)})$. 这表明$S^{-1}AS = \Lambda$. 反过来, 如果$S$是非奇异的, 并且$S^{-1}AS = \Lambda$, 那么$AS = S\Lambda$, 因此$S$的每一列都是$A$的特征向量.
#####
___

### 3.5. 对角化的充分条件
如果$A\in \mathbb{M}_n$有$n$个不同的特征根, 那么$A$是可以对角化的.

### 1.1. 特征值分解

设$A$是一个$n\times n$的对称矩阵, 则$A$可以被写成
$$
A = Q\Lambda Q^{\top} 
$$
其中$Q\in \mathbb{R}^{n\times n}$是正交矩阵, $\Lambda=\mathrm{diag}\{\lambda_1, \lambda_2,\cdots,\lambda_n\}$. $\lambda_i$是矩阵$A$的实特征值. $Q$的列是矩阵$A$的对应于$\lambda_i$的特征向量. 该分解称为矩阵$A$的特征值分解.
**特征值的求法**: 我们用$\lambda_i(A)$表示矩阵$A$第$i$大的特征值, $\lambda_1(A) = \lambda_{\mathrm{max}}(A)$, $\lambda_n(A) = \lambda_{\mathrm{min}}(A)$. 可以证明对于对称矩阵$A$
$$
\lambda_{\mathrm{max}}(A)=\sup_{\boldsymbol{x}\neq 0}\frac{\boldsymbol{x}^{\top} A\boldsymbol{x}}{\boldsymbol{x}^{\top} \boldsymbol{x}},\quad \lambda_{\mathrm{min}}(A)=\inf_{\boldsymbol{x}\neq 0} \frac{\boldsymbol{x}^{\top} A\boldsymbol{x}}{\boldsymbol{x}^{\top} \boldsymbol{x}}
$$
此外, 如果我们已经得到了$\lambda_1, \lambda_2, \cdots,\lambda_k$和对应的特征向量$\boldsymbol{x}_1, \boldsymbol{x}_2, \cdots, \boldsymbol{x}_k$, 那么
$$
\lambda_{k+1}(A) = \sup_{\boldsymbol{x}\neq 0, \langle\boldsymbol{x}_i, \boldsymbol{x}  \rangle = 0, \forall i=1,2,\cdots,k} \frac{\boldsymbol{x}^{\top}A\boldsymbol{x}}{\boldsymbol{x}^{\top} \boldsymbol{x}} 
$$
**正定矩阵的squareroot**: 设$A$是正定矩阵, 其特征值分解是
$$
A = Q\mathrm{diag}\{\lambda_1, \lambda_2, \cdots, \lambda_n\}Q^{\top}
$$
我们可以定义$A$的对称的平方根矩阵为
$$
A^{1/2}=Q\mathrm{diag}\{\lambda_1^{1/2}, \lambda_2^{1/2}, \cdots, \lambda_n^{1/2}\}Q^{\top}
$$
则Square root $A^{1/2}$是矩阵方程$X^2=A$的唯一的对称半正定解.

## 1. 奇异值分解
### 1.1. 完全奇异值分解
设$A\in \mathbb{R}^{m\times n}$的秩是$r$, 则$A$可以被分解为
$$
A = U\begin{pmatrix}
\Sigma_1 & O \\
O & O
\end{pmatrix}V^{\top} 
$$
这里$U\in \mathbb{R}^{m\times m}$, $V\in \mathbb{R}^{n\times n}$都是正交矩阵并且$\Sigma_1  =\mathrm{diag}\{\sigma_1, \sigma_2, \cdots, \sigma_r\}$满足
$$
\sigma_1\ge \sigma_2\ge \cdots\ge \sigma_r > 0 
$$
正交矩阵$U$的前$r$列构成了矩阵$A$的列空间的标准正交基, 后$n-r$列构成了矩阵$A$的零空间的标准正交基. 矩阵$V$的前$r$列组成了矩阵$A$的行空间的标准正交基, 后$n-r$列构成了矩阵$A^{\top}$的零空间的标准正交基. 
___
##### Proof
因为$A^{\top}A\succeq 0$, 我们有$\boldsymbol{\sigma}(A^{\top}A) =\{\sigma_i\mid i=1,2,\cdots, n\} \subseteq [0, \infty)$. 不妨设
$$
\sigma_1\ge \sigma_2\ge \cdots \sigma_r > 0 = \sigma_{r+1} = \cdots = \sigma_n
$$
设$\boldsymbol{v}_1, \cdots, \boldsymbol{v}_n$是对应的正交的特征向量, 令
$$
V_1 = (\boldsymbol{v}_1, \cdots, \boldsymbol{v}_r), \quad V_2 = (\boldsymbol{v}_{r+1}, \cdots, \boldsymbol{v}_n)
$$
令$S =\mathrm{diag}\left\{\sigma_1, \cdots, \sigma_r\right\}$, 我们有$A^{\top}AV_1 = V_1S^2$. 令$U_1 = AV_1S^{-1}$, 我们有$U_1^{\top}U_1 = I$. 选择$U_2$使得$U = (U_1, U_2)$是正交矩阵. 则
$$
U^{\top} A V = \begin{pmatrix}U_1^{\top}AV_1 & U_1^{\top}AV_2 \\ U_2^{\top}AV_1 & U_2^{\top}AV_2\end{pmatrix} = \begin{pmatrix}
\Sigma_1 & O \\
O & O
\end{pmatrix}
$$
因此我们得到了想要的奇异值分解
#####
___

### 1.2. 截断奇异值分解
设$A\in \mathbb{R}^{m\times n}$的秩是$r$, 则$A$可以被分解为
$$
A = U\Sigma V^{\top} 
$$
这里$U\in \mathbb{R}^{m\times r}$满足$U^{\top}U=I$, $V\in \mathbb{R}^{n\times r}$ 满足$V^{\top}V = I$. 并且$\Sigma=\mathrm{diag}\{\sigma_1, \sigma_2, \cdots, \sigma_r\}$ 满足
$$
\sigma_1\ge \sigma_2\ge \cdots\ge \sigma_r > 0 
$$
我们也可以把奇异值分解写成类似谱分解的形式
$$
A = \sum\limits_{i=1}^{r} \sigma_i \boldsymbol{u}_i \boldsymbol{v}_i^{\top}  
$$

### 1.3. 奇异值与特征值
事实上
$$
AA^{\top} = U\Sigma^2 U^{\top} 
$$
这表明
$$
\sigma^2(A) = \lambda(A A^{\top})
$$
但是, $\sigma(A)$和$\lambda(A)$并没有必然的联系


### 1.4. 奇异值的奇异性
设$A\in \mathbb{R}^{m\times n} (m>n)$的奇异值为
$$
\sigma_1\ge \sigma_2\ge \cdots\ge \sigma_r > 0 
$$
则
$$
\sigma_k = \min_{E\in \mathbb{R}^{m\times n}}\left\{\|E\|_2: \mathrm{rank}(A+E)\le k-1\right\}, \quad k=1,2,\cdots, n
$$
并且存在一个满足$\|E_k\|_2=\sigma_k$的误差矩阵$E_k$使得
$$
\mathrm{rank}(A+E_k) = k-1, \quad k=1,2,\cdots,n
$$



## 2. 奇异值的性质
1. **奇异值交织定理(interlacing theorem for singular values)**: 设$A$是一个$m\times n$矩阵, 其奇异值为$\sigma_1\ge \sigma_2\ge \cdots\ge \sigma_r \ge 0$, 其中$r=\min\{m,n\}$(这里我们将$0$也当成了奇异值看待). 若$p\times q$矩阵$B$是$A$的子矩阵, 其奇异值为$\gamma_1\ge \cdots\ge \gamma_{\min\{p,q\}}$, 则
   $$
   \sigma_i\ge \gamma_i, \quad i=1,2,\cdots,\min\{p,q\}
   $$
   并且 
   $$
   \gamma_i\ge \sigma_{i+(m-p)+(n-q)}, \quad i\le \min\{p+q-m, p+q-n\}
   $$







