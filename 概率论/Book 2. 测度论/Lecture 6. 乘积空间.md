## 1. 有限维乘积空间
### 1.1. 有限个集合的乘积
设$\{X_k\mid k=1,2,\cdots, n\}$是$n$个非空集合, 我们把集合
$$
\prod_{k=1}^n X_k \stackrel{\text { def }}{=}\left\{\left(x_1, \cdots, x_n\right)\ \Big|\ x_k \in X_k, k=1, \cdots, n\right\}
$$
称为这$n$个集合的乘积. $\prod\limits_{k=1}^{n} X_k$乘积空间. 

### 1.2. 有限个可测空间的乘积
设 $\left\{\left(X_k, \mathscr{F}_k\right), k=1, \cdots, n\right\}$ 是可测空间. 那么称
$$
\mathscr{Q} = \left\{\prod_{k=1}^n A_k\ \Big|\   A_k \in \mathscr{F}_k, \ k=1, \cdots, n\right\}
$$
中的集合为由$\{\mathscr{F}_k\}$确定的可测矩形. 称由$\mathscr{Q}$生成的$\sigma$域
$$
\prod_{k=1}^n \mathscr{F}_k \xlongequal{\text { def }} \sigma(\mathscr{Q})
$$
为 $\left\{\mathscr{F}_k\mid  k=1, \cdots, n\right\}$ 的乘积; 称
$$
\left(\prod_{k=1}^n X_k, \prod_{k=1}^n \mathscr{F}_k\right)
$$
为可测空间 $\left\{\left(X_k, \mathscr{F}_k\right)\mid  k=1, \cdots, n\right\}$ 的乘积. 特别地, $n$ 个相同的可测空间 $(X, \mathscr{F})$ 的乘积空间将记为 $\left(X^n, \mathscr{F}^n\right)$.

### 1.3. 可测空间乘积的性质
设 $\left\{\left(X_k, \mathscr{F}_k\right), k=1, \cdots, n\right\}$ 是可测空间. 则由下式定义的
$$
\mathscr{Q} = \left\{\prod_{k=1}^n A_k\ \Big|\   A_k \in \mathscr{F}_k, \ k=1, \cdots, n\right\}
$$
$\mathscr{Q}$是一个半环并且$\prod\limits_{k=1}^{n} X_k\in \mathscr{Q}$
___
##### Proof:
设$A = A_1\times A_2\times \cdots \times A_n,\ B = B_1\times B_2\times \cdots\times B_n$, 于是我们有
$$
A\cap B = (A_1\cap B_1)\times (A_2\cap B_2)\times \cdots \times (A_n\cap B_n)
$$
这意味着$\mathscr{Q}$是一个$\pi$系. 又如果$A\supset B$, 则有$A_i\supset B_i, A_i\backslash B_i\in \mathscr{F}$, 设
$$
C_i = A_1\times A_2\times \cdots \times (A_i\backslash B_i) \times \cdots \times B_n \in \mathscr{Q}
$$
则可以证明所有的$C_i$彼此不交, 并且
$$
A\backslash B = C_1\cup C_2\cup \cdots \cup C_n
$$
于是我们证明了结论.
#####
___

### 1.4. 投影
对每个$k=1,2, \cdots, n$, 把从乘积空间$\prod\limits_{k=1}^{n} X_k$到$X_k$的映射
$$
\pi(x_1, x_2, \cdots, x_n) = x_k
$$
称为$\prod\limits_{k=1}^{n} X_k$到$X_k$的投影. 

设$\{(X_k, \mathscr{F}_k\mid k=1,2,\cdots, n)\}$是可测空间
1. 对每个$k=1,2,\cdots, n$, 投影$\pi_k$是$\left(\prod\limits_{k=1}^n X_k, \prod\limits_{k=1}^n\mathscr{F}_k\right)$ 到 $\left(X_k, \mathscr{F}_k\right)$ 的可测映射;
2. $\prod\limits_{k=1}^n \mathscr{F}_k$  是使每个 $\pi_1, \cdots, \pi_n$ 都可测的最小 $\sigma$ 域, 即
$$
\prod_{k=1}^n \mathscr{F}_k=\sigma\left(\bigcup_{k=1}^n \pi_k^{-1}(\mathscr{F}_k)\right) .
$$

___
##### Proof:
1. 对任何的$k=1,2,\cdots, n$和任何的$A_k\in \mathscr{F}_k$, 有
   $$
   \pi_k^{-1} (A_k)=\prod_{i=1}^{k-1} X_i \times A_k \times \prod_{i=k+1}^n X_i \in \mathscr{Q} \subset \prod_{k=1}^n \mathscr{F}_k
   $$
   因此结论1成立
2. 我们已经证明了$\bigcup\limits_{k=1}^{n} \pi_k^{-1}(\mathscr{F}_k)\subset \mathscr{Q}$, 从而
   $$
   \sigma\left(\bigcup_{k=1}^n \pi_k^{-1}  (\mathscr{F}_k)\right) \subset \sigma(\mathscr{Q})=\prod_{k=1}^n \mathscr{F}_k 
   $$
   另外, 由于对任意 $\left\{A_k \in \mathscr{F}_k \mid k=1, \cdots, n\right\}$, 均有
   $$
   \prod_{k=1}^n A_k=\bigcap_{k=1}^n \pi_k^{-1}(A_k) \in \sigma\left(\bigcup_{k=1}^n \pi_k^{-1} (\mathscr{F}_k)\right)
   $$
   故又得
   $$
   \prod_{k=1}^n \mathscr{F}_k=\sigma(\mathscr{Q}) \subset \sigma\left(\bigcup_{k=1}^n \pi_k^{-1} (\mathscr{F}_k)\right) 
   $$
   因此我们得到了结论2也成立
#####
___

### 1.5. 可测的分解

设 $(\Omega, \mathscr{S})$ 和 $\left\{\left(X_k, \mathscr{F}_k\right), k=1, \cdots, n\right\}$ 是可测空间. 而 $f=\left(f_1, \cdots, f_n\right)$ 是 $\Omega$ 到 $\prod\limits_{k=1}^n X_k$ 的一个映射. 则 $f$ 是 $(\Omega, \mathscr{S})$ 到 $\left(\prod\limits_{k=1}^n X_k, \prod\limits_{k=1}^n \mathscr{F}_k\right)$ 的可测映射当且仅当对每个 $k=1, \cdots, n, f_k$ 是 $(\Omega, \mathscr{S})$ 到 $\left(X_k, \mathscr{F}_k\right)$ 的可测映射.
___
##### Proof:
事实上, 我们有
$$
\begin{aligned} 
f^{-1}\left(\prod_{k=1}^n \mathscr{F}_k\right) &= f^{-1}\sigma\left(\bigcup_{k=1}^n \pi_k^{-1} (\mathscr{F}_k)\right) \\ 
& = \sigma\left(f^{-1}\left(\bigcup_{k=1}^n \pi_k^{-1} (\mathscr{F}_k)\right)\right) \\
& = \sigma\left(\bigcup_{k=1}^n f^{-1}\left(\pi_k^{-1} (\mathscr{F}_k)\right)\right) \\ 
& = \sigma\left(\bigcup_{k=1}^n \left(\pi_k \circ f\right)^{-1} (\mathscr{F}_k)\right) \\ 
& = \sigma\left(\bigcup_{k=1}^n f_k^{-1} (\mathscr{F}_k)\right)
\end{aligned}
$$
#####
___

### 1.6. 截口的可测性
设$\{(X_k, \mathscr{F}_k)\}$为可测空间
1. 任意固定$1\le k_1< k_2<\cdots< k_i\le n$和$(x_{k_1}, x_{k_2}, \cdots, x_{k_i})\in\prod\limits_{j=1}^{i} X_{k_j}$, 集合$A\in \prod\limits_{k=1}^{n} \mathscr{F}_k$在$(x_{k_1}, x_{k_2}, \cdots, x_{k_i})$处的截口为$\mathscr{F} \mid_{k_1,\cdots, k_i}$中的集合
2. 对任意固定的$1\le k_1< k_2<\cdots< k_i\le n$和$(x_{k_1}, x_{k_2}, \cdots, x_{k_i})\in\prod\limits_{j=1}^{i} X_{k_j}$, 乘积可测空间$\left(\prod\limits_{k=1}^{n} X_k, \prod\limits_{k=1}^{n} \mathscr{F}_k\right)$上的可测函数$f$在$(x_{k_1}, x_{k_2}, \cdots, x_{k_i})$处的截口是$\mathscr{F} \mid_{k_1,\cdots, k_i}$可测函数. 

## 2. 二维乘积可测空间上的测度
### 2.1. 测度转移函数
定义在$\Omega\times \mathscr{F}$上的广义实值函数$p$称为是从可测空间$(\Omega, \mathscr{S})$到$(X, \mathscr{F})$的测度转移函数, 如果它满足下列条件