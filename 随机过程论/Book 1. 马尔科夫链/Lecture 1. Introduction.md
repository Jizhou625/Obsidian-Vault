## 1. Markov链
### 1.1. 转移概率
假设
$$
p_{i j} \geqslant 0, \forall i, j \in S ; \quad \sum_{j \in S} p_{i j}=1, \forall i \in S .
$$
将 $p_{i j}$ 作为第 $i$ 行第 $j$ 列的元素, 得到矩阵 $P=\left(p_{i j}\right)_{S \times S}$. 称 $P$ 为 $S$ 上的一个转移概率矩阵, 简称转移矩阵. 称 $p_{i j}$ 为从 $i$ 到 $j$ 的转移概率(transition probability).

### 1.2. Markov链
若转移矩阵 $P$ 使得: $\forall n \geqslant 0, \forall i_0, \cdots, i_{n-1}, i, j \in S$,
$$
P\left(X_{n+1}=j \mid X_n=i, X_0=i_0, \cdots, X_{n-1}=i_{n-1}\right)=p_{i j}
$$
则称 $\left\{X_n\right\}$ 是 $S$ 上的一个(时齐的)马尔可夫链(Markov chain), 简称马氏链. 称 $P$ 为 $\left\{X_n\right\}$ 的转移矩阵.

### 1.3. Chapman-Kolmogorov等式
用$P^{(n)}$表示$n$步转移矩阵, 则对任何 $i, j \in S, m, n \geqslant 0$, 有
$$
p_{i j}^{(n+m)}=\sum_{k \in S} p_{i k}^{(n)} p_{k j}^{(m)}
$$
也就是说
$$
P^{(n+m)}=P^{(n)} P^{(m)}
$$

## 2. 不变分布与可逆分布
### 2.1. 不变分布
假设 $\boldsymbol{\pi}=\left\{\pi_j: j \in S\right\}$ 为 $S$ 上的测度. 若 $\boldsymbol{\pi}$ 满足如下不变方程:
$$
\pi_j=\sum_{k \in S} \pi_k p_{k j}, \quad \forall j \in S
$$
则称 $\boldsymbol{\pi}$ 为 $P$ 的一个不变测度. 进一步, 若 $\pi$ 还是分布, 则称 $\pi$ 为一个不变分布 (invariant distribution). 用线性代数的语言, 不变方程可以写成
$$
\boldsymbol{\pi}^{\prime} = \boldsymbol{\pi}^{\prime} P\iff P^{\prime}\boldsymbol{\pi} = \boldsymbol{\pi}
$$

![image-20230527160640924](./Lecture%201.%20Introduction.assets/image-20230527160640924.png)

不变分布意味着每个状态的总收和总支相抵. 

### 2.2. 不变分布的性质
假设 $\boldsymbol{\pi}=\left\{\pi_j: j \in S\right\}$ 为 $S$ 上的分布, 则 $\boldsymbol{\pi}$ 是不变分布当且仅当, 对$S$的任意子集$A$, 都有下式成立
$$
\sum\limits_{i\notin A, j\in A}^{} \pi_i p_{i j} = \sum\limits_{i\in A, j\notin A}^{} \pi_i p_{i j}
$$
即$S$可以被划分为两个系统, 这两个系统之间的总收和总支相等. 
___
##### Proof
我们将所有的流分为
#####
___



### 2.2. 可逆分布

假设 $P$ 不可约, $\boldsymbol{\pi}$ 为 $S$ 上的一个测度. 若细致平衡条件
$$
\pi_i p_{i j}=\pi_j p_{j i}, \quad \forall i, j \in S
$$
成立, 则称 $\boldsymbol{\pi}$ 为 $P$ 的配称测度 (symmetric measure). 此时, 称 $P$ 为可配称的. 进一步, 若 $\boldsymbol{\pi}$ 是一个分布, 则称 $\boldsymbol{\pi}$ 为 $P$ 的可逆分布 (reversible distribution). 此时, 称 $P$ 为可逆的(reversal). 

![image-20230527160737582](./Lecture%201.%20Introduction.assets/image-20230527160737582.png)

可逆分布意味着每对状态的收支平衡. 显然, 可逆分布是不变分布的特例. 

### 2.3. 可逆分布的意义
假设 $\boldsymbol{\pi}$ 是不变分布, $\left\{X_n\right\}$ 是以 $\boldsymbol{\pi}$ 为初分布,  $P$ 为转移矩阵的马氏链. 固定 $N$, 令 $Y_n:=X_{N-n}$, 则 $\left\{Y_n: 0 \leqslant n \leqslant N\right\}$ 被称为 $\left\{X_n: 0 \leqslant n \leqslant N\right\}$ 的时间倒逆过程, 简称逆过程. 那么, $\left\{Y_n: 0 \leqslant n \leqslant N\right\}$ 也是一个马氏链, 其转移概率为
$$
\tilde{p}_{i j}=\frac{\pi_j p_{j i}}{\pi_i}, \quad \forall i, j \in S
$$
因此, $\boldsymbol{\pi}$ 是可逆分布指的是 $\tilde{P}=P$, 即, 逆过程 $\left\{Y_n: 0 \leqslant n \leqslant N\right\}$ 与原过程 $\left\{X_n: 0 \leqslant n \leqslant N\right\}$ 具有相同的初分布和转移概率. 此时, 我们也称以 $\boldsymbol{\pi}$ 为初分布、 $P$ 为转移矩阵的马氏链是可逆的.

### 2.4. 可逆分布的算法
求可逆分布的步骤如下
1. 固定$o$, 


## 3. 访问频率与访问概率
### 3.1. 访问频率
假设 $L_1, L_2, \cdots$ 独立同分布, 取非负整数, $P\left(L_1=0\right)<1$. 令
$$
S_0=0, \quad S_r=L_1+\cdots+L_r, r \geqslant 1 .
$$
令
$$
R_n=\max \left\{r \geqslant 0: S_r \leqslant n\right\} .
$$
称$R_n$为时间$n$内的访问频率

### 3.2. 更新定理
$$
P\left(\lim _{n \rightarrow \infty} \frac{R_n}{n}=\frac{1}{\mathbb{E} L_1}\right)=1 .
$$