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







