## 1. 奇异值分解
### 1.1. Intuition
考虑双线性函数
$$
f(\boldsymbol{x}, \boldsymbol{y}) = \boldsymbol{x}^{\top}A \boldsymbol{y},\quad A\in \mathbb{R}^{n\times n}
$$
引入线性变换$\boldsymbol{x} = U\boldsymbol{\xi},\ \boldsymbol{y} = V\boldsymbol{\eta}$, 将双线性函数变为 $f(\boldsymbol{x}, \boldsymbol{y})= \boldsymbol{\xi}^{\top}S\boldsymbol{\eta}$, 其中
$$
S = U^{\top} A V
$$
如果约束$U, V$均为正定矩阵, 则它们的选择存在$n^2-n$个自由度. 这就得到了正方矩阵的奇异值分解. 后来又推广到了长方矩阵中. 
### 1.2. 奇异值分解
**完全奇异值分解**: 设$A\in \mathbb{R}^{m\times n}$的秩是$r$, 则$A$可以被分解为
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
正交矩阵$U$的前$r$列构成了矩阵$A$的列空间的标准正交基, 后$n-r$列构成了矩阵$A$的零空间的标准正交基. 矩阵$V$的前$r$列组成了矩阵$A$的行空间的标准正交基, 后$n-r$列构成了矩阵$A^{\top}$的零空间的标准正交基
**截断奇异值分解**: 设$A\in \mathbb{R}^{m\times n}$的秩是$r$, 则$A$可以被分解为
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
**奇异值与特征值**: 事实上
$$
AA^{\top} = U\Sigma^2 U^{\top} 
$$
这表明
$$
\sigma^2(A) = \lambda(A A^{\top})
$$
注意: $\sigma(A)$和$\lambda(A)$并没有必然的联系


### 1.3. 奇异值的奇异性
设$A\in \mathbb{R}^{m\times n} (m>n)$的奇异值为
$$
\sigma_1\ge \sigma_2\ge \cdots\ge \sigma_r > 0 
$$
则
$$
\sigma_k = \min_{E\in \mathbb{R}^{m\times n}}\left\{\|E\|_2: \mathrm{rank}(A+E)\le k-1\right\}, \quad k=1,2,\cdots, n
$$
并且存在$\|E_k\|_2=\sigma_k$ 使得
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







