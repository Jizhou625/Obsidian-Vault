## 1. 交换与对角化
### 1.1. 直和的对角化
给定$B_1\in \mathbb{M}_{n_1}, \cdots, B_d\in \mathbb{M}_{n_d}$, 并设$B$是直和
$$
B = B_1\oplus \cdots \oplus B_d
$$
那么$B$是可对角化的当且仅当$B_1, \cdots, B_d$都是可对角化的.
___
##### Proof
如果$B_1, \cdots, B_d$是可以对角化的, 那么存在可逆矩阵$S_1, \cdots, S_d$使得$S_i^{-1} B_i S_i$是对角矩阵, 定义$S = S_1\oplus S_2\oplus\cdots \oplus S_d$, 则$S^{-1}B S$是对角的. 

关于逆命题, 我们用归纳法, 当$d=1$时结论显然成立, 假设结论对所有项数不超过$d-1$的直和成立, 设$C = B_1\oplus B_2\oplus \cdots \oplus B_{d-1}$, 并设$n = n_1+n_2+\cdots +n_{d-1}$, $m = n_d$, 设$S\in \mathbb{M}_{n+m}$是非奇异的, 并且
$$
\Lambda = S^{-1}BS = S^{-1}(C\oplus  B_d)S
$$
将此恒等式写成$BS = S\Lambda$, 分划$S = (\boldsymbol{s}_1, \boldsymbol{s}_2, \cdots, \boldsymbol{s}_{n+m})$, 并且
$$
\boldsymbol{s}_i = \begin{pmatrix}\boldsymbol{s}_{i1} \\ \boldsymbol{s}_{i2}\end{pmatrix} \in \mathbb{C}^{n+m}, \quad \boldsymbol{s}_{i1}\in \mathbb{C}^n, \quad \boldsymbol{s}_{i2}\in \mathbb{C}^m
$$
那么我们可以得到
$$
\begin{aligned} 
     C\boldsymbol{s}_{i1} &= \lambda_i \boldsymbol{s}_{i1} \\ 
    B_d\boldsymbol{s}_{i2} &= \lambda_i \boldsymbol{s}_{i2}
\end{aligned} \qquad i = 1, 2, \cdots, n+m 
$$
因为$(\boldsymbol{s}_{1,1}, \cdots, \boldsymbol{s}_{m+n, 1})\in \mathbb{M}_{n, n+m}$的行秩为$n$, 因为这个矩阵由非奇异矩阵$S$的前$n$行组成, 从而向量组$(\boldsymbol{s}_{1,1}, \cdots, \boldsymbol{s}_{m+n, 1})$包含由$n$个向量组成的线性无关组, 其中每一个都是$C$的特征向量, 因此根据[对角化的充分条件](Lecture%201.%20特征值.md#3.5.%20对角化的充分条件), $C$是可对角化的, 由归纳假设, $B_1, \cdots, B_{d-1}$都是可对角化的, 同理, $B_d$也是可对角化的. 这就证明了结论对$d$也成立. 
#####
___

### 1.2. 可交换与同时对角化
设$A, B\in \mathbb{M}_n$是可对角化的. 那么$A$和$B$可交换当且仅当$A$和$B$可以同时对角化.
___
##### Proof
假设$A$和$B$可交换, 对$A$和$B$做相似变换, 使得$A$可以对角化. 因此可以不妨设$A$是一个对角矩阵
$$
A = \mathrm{diag}\left\{\mu_1I_{n_1},\ \mu_2I_{n_2},\ \cdots,\ \mu_dI_{n_d}\right\}, \quad \mu_i\neq \mu_j
$$
由于$AB = BA$, 于是我们有$B = \mathrm{diag}\left\{B_1, B_2, \cdots, B_d\right\}$是与$A$共形的分块对角矩阵. 由于$B$是可以对角化的, 因此根据[1.1. 直和的对角化](#1.1.%20直和的对角化)可以得到$B_1, B_2, \cdots, B_d$都是可以对角化的. 设$T_i\in \mathbb{M}_{n_i}$是非奇异的并且使得$T_i^{-1}B_iT_i$为对角矩阵, 令$T = T_1\oplus T_2\oplus\cdots \oplus T_d$. 那么, 我们有$T^{-1}AT = A$与$T^{-1}BT$都是对角矩阵. 

假设$A, B$可以同时对角化, $S^{-1}AS = \Lambda_1$并且$S^{-1}BS = \Lambda_2$, 也就是说$A = S\Lambda_1 S^{-1}$并且$B = S\Lambda_2 S^{-1}$. 这样
$$
AB = S\Lambda_1\Lambda_2 S^{-1} = S\Lambda_2\Lambda_1 S^{-1} = BA
$$
这就证明了结论成立.
#####
___


## 2. 交换族
### 2.1. 交换族
矩阵族$\mathcal{F}\subseteq \mathbb{M}_n$是矩阵的一个非空的集合, 交换族是这样的一族矩阵, 其中每一对矩阵都是可交换的. 

### 2.2. 不变子空间
对于给定的$A\in \mathbb{M}_n$, 我们称子空间$W\subseteq \mathbb{C}^n$是$A$不变的, 如果对于每个$\omega\in W$都有$A\omega\in W$. 

对于一个给定的族$\mathcal{F}\subseteq \mathbb{M}_n$, 我们称子空间$W\subseteq \mathbb{C}^n$是$\mathcal{F}$不变的, 如果对每个$A\in \mathcal{F}$, $W$都是$A$不变的. 

给定的族$\mathcal{F}\subseteq \mathbb{M}_n$称为是可约的, 如果$\mathbb{C}^n$中某个非平凡的子空间是$\mathcal{F}$不变的. 反之, 则称$\mathcal{F}$是不可约的.

### 2.3. 分块三角矩阵的相似和不变子空间
假设$n\ge 2$, 给定的$A\in \mathbb{M}_n$与一个形如$\begin{pmatrix}B & C \\ 0 & D\end{pmatrix}$的分块三角矩阵相似当且仅当$\mathbb{C}^n$的某个非平凡子空间是$A$不变的. 此外, 如果$W\subseteq \mathbb{C}^n$是一个非零的$A$不变子空间, 那么$W$中的某个向量就是$A$的一个特征向量.

一个给定的族$\mathcal{F}\subseteq \mathbb{M}_n$是可约的, 当且仅当存在某个$k\in\{2, 3,\cdots, n-1\}$以及一个非奇异的$S\in \mathbb{M}_n$, 使得对每个$A\in \mathcal{F}$, $S^{-1}AS$具有形式$\begin{pmatrix}B & C \\ 0 & D\end{pmatrix}$, 其中$B\in \mathbb{M}_k$并且$D\in \mathbb{M}_{n-k}$.
___
##### Proof
考虑$W\subseteq\mathbb{C}^n$是一个$k$维子空间, 设$\boldsymbol{s}_1, \boldsymbol{s}_2, \cdots, \boldsymbol{s}_k$是$W$的一组基, $\boldsymbol{s}_1, \boldsymbol{s}_2, \cdots, \boldsymbol{s}_k, \boldsymbol{s}_{k+1}, \cdots, \boldsymbol{s}_n$是经过施密特正交化扩充得到的$\mathbb{C}^n$的基. 并且设$S_1 = (\boldsymbol{s}_1, \boldsymbol{s}_2, \cdots, \boldsymbol{s}_k)$, $S_2 = (\boldsymbol{s}_{k+1}, \cdots, \boldsymbol{s}_n)$, $S = (S_1, S_2)$. 显然$S$是非奇异的. 

如果$W$是$A$不变的, 那么每个$A\boldsymbol{s}_j$都是$\boldsymbol{s}_1, \cdots, \boldsymbol{s}_k$的线性组合, 也就是说, 存在某个$B\in \mathbb{M}_k$, 满足$AS_1 = S_1B$, 这意味着
$$
S^{-1}AS = \begin{pmatrix}S^{-1}S_1B & S^{-1}AS_2\end{pmatrix} = \begin{pmatrix} \begin{pmatrix} I_k \\ 0 \end{pmatrix}B & S^{-1}AS_2\end{pmatrix}  = \begin{pmatrix}B & C \\ 0 & D\end{pmatrix}
$$
也就是说$A\sim  \begin{pmatrix}B & C \\ 0 & D\end{pmatrix}$. 

反过来, 如果$A\sim  \begin{pmatrix}B & C \\ 0 & D\end{pmatrix}$, 那么
$$
AS_1 = AS\begin{pmatrix} I_k \\ 0\end{pmatrix} = S\begin{pmatrix}B & C \\ 0 & D\end{pmatrix}\begin{pmatrix} I_k \\ 0\end{pmatrix} = S_1B
$$
这样, 由$S_1$的列生成的$k$维子空间是$A$不变的. 

接下来, 
#####
___