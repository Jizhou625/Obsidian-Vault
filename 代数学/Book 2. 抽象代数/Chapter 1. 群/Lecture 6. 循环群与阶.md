## 1. 循环群
### 1.1. 循环群
可以由一个元素生成的群称为循环群. 即若 $a\in G$, 则称 $\langle a\rangle$ 为 $G$ 的循环子群.
$$
\langle a\rangle=\left\{a^m \mid m \in \mathbb{Z}\right\} 
$$

**循环群的阶**: 定义循环群的阶为循环群中互不相同的元素的个数, 记为$o(a) = |\langle a\rangle|$. 

### 1.2. 循环群的同构
两个有限阶循环群同构当且仅当它们的阶相等.
___
##### Proof
必要性: 同构的群具有相同的代数结构，所以必要性显然。

充分性：设 $G_1=\left\langle a_1\right\rangle$ 与 $G_2=\left\langle a_2\right\rangle$ 都是 $n$ 阶循环群, 则有 $a_1^n=a_2^n=e$, 且 $a_i^k$, $0 \leq k \leq n-1$ 两两不同，则
$$
\begin{aligned}
\varphi: G_1 & \rightarrow G_2 \\
a_1^k & \mapsto a_2^k,\quad 0 \leq k \leq n-1
\end{aligned}
$$
是同构映射, 故 $G_1$ 与 $G_2$ 同构.
#####
___

### 1.3. 循环群的子群
1. 循环群的子群都是循环群. 
2. 设 $G=\langle a\rangle$ 为 $n$ 阶循环群, 则 $G$ 的子群的阶都是 $n$ 的因子. 进一步地, 对于任意 $d \mid n, G$ 的阶为 $d$ 的子群存在且唯一. 
___
##### Proof
1. 设 $G=\langle a\rangle, H \leq G$. 
	- 若 $H=\{e\}$, 则 $H=\langle e\rangle$ 为循环群. 
	- 若 $H \neq\{e\}$, 则存在 $a^m \in H$, 其中 $m \neq 0$. 又 $a^{-m}=\left(a^m\right)^{-1} \in H$, 从 而存在 $a$ 的正整数次幂在 $H$ 中. 取最小正整数 $s$ 满足 $a^s \in H$, 则$\left\langle a^s\right\rangle \subseteq H$. 另一方面, 任取 $a^n \in H$, 做带余除法 
         $$
         n=t s+r, 0 \leq r<s
         $$
         则 
         $$
         a^r=a^{n-t s}=a^n\left(a^s\right)^{-t} \in H
         $$ 
         由 $s$ 的取法知 $r=0$, 所以 $a^n=\left(a^s\right)^t \in\left\langle a^s\right\rangle$, 即 $H \subseteq\left\langle a^s\right\rangle$. 故 $H=\left\langle a^s\right\rangle$ 为循环群.
2. 设 $H \leq G$. 由于 $H=\left\langle a^s\right\rangle$, 对某个 $0 \leq s \leq n-1$, 所以 $H$ 的 阶为 $o\left(a^s\right)=\dfrac{n}{\operatorname{gcd}(n, s)}$, 为 $n$ 的因子. 对 $n$ 的每一个因子 $d$, 
   $$ 
   \left\langle a^{\frac{n}{d}}\right\rangle=\left\{a^{\frac{n}{d}}, a^{\frac{2 n}{d}}, \cdots, a^{\frac{(q-1) n}{d}}, a^{\frac{d n}{d}}=e\right\} 
   $$ 
   是 $G$ 的 $d$ 阶子群. 即对 $n$ 的每个因子 $d, G$ 都有 $d$ 阶子群. 
   
   进一步地, 设 $H$ 为 $G$ 的一个 $d$ 阶子群, 则存在自然数 $s$, 使得 $H=\left\langle a^s\right\rangle$. 所以 $o\left(a^s\right)=d$, 即 $a^{s d}=\left(a^s\right)^d=e$, 所以 $n \mid s d$, 或 $\frac{n}{d} \mid s$, 这推出 $a^s$ 为 $a^{\frac{n}{d}}$ 的方幂, 即 $a^s \in\left\langle a^{\frac{n}{d}}\right\rangle$, 故 $H \subseteq\left\langle a^{\frac{n}{d}}\right\rangle$. 由于 $H$ 与 $\left\langle a^{\frac{n}{d}}\right\rangle$ 都是 $d$ 阶群, 所以 $H=\left\langle a^{\frac{n}{d}}\right\rangle$.
#####
___


## 2. 阶
### 2.1. 元素的阶
设 $G$ 为一个群, $a \in G$, 称 $a$ 生成的循环子群 $\langle a\rangle$ 的阶为元素 $a$ 的阶, 记为 $o(a)$, 即 $o(a)$ 就是使 $a^n=e$ 成立的最小正整数 $n$, 若这样的 $n$ 不存在, 则 $o(a)=\infty$.

### 2.2. 阶的性质
1. 若 $G$ 为群, $a \in G$, 则 $a^k=e$ 当且仅当 $o(a) \mid k$.
2. 设 $o(a)=n$, $k$ 为正整数, 则 $o\left(a^k\right)=\dfrac{n}{\operatorname{gcd}(n, k)}$, 其中 $\operatorname{gcd}(n, k)$ 为 $n$ 与 $k$ 的最大公因数.
___
##### Proof
1. 充分性显然, 下证必要性, 设$k = to(a) + s$, 其中$0\le s< o(a)$, 则
   $$
   a^s =  a^{k-to(a)} = a^k (a^{o(a)})^{-t} = a^k e^{-t} = e
   $$
   根据$o(a)$的最小性, 可知$s=0$, 即$o(a)\mid k$.
2. 记 $d=\operatorname{gcd}(n, k)$, 且 $n=n_1 d, k=k_1 d$, 则$\operatorname{gcd}\left(n_1, k_1\right)=1$. 设 $o\left(a^k\right)=m$, 由于 
   $$
   \left(a^k\right)^{n_1}=\left(a^{k_1 d}\right)^{n_1}=\left(a^n\right)^{k_1}=e^{k_1}=e
   $$ 
   故 $m \mid n_1$. 另一方面, 由于 
   $$
   a^{k m}=\left(a^k\right)^m=e
   $$ 
   有 $n \mid k m$, 即 $n_1 \mid k_1 m$, 又 $n_1$ 与 $k_1$ 互素, 从而 $n_1 \mid m$. 这样便有 $m=n_1$. 即 $o\left(a^k\right)=n_1=\dfrac{n}{\operatorname{gcd}(n, k)}$.
#####
___

### 2.3. 可交换乘积的阶
设 $G$ 是一个群, $a, b \in G, a b=b a$. 若 $o(a)=m, o(b)=n$ 且 $\operatorname{gcd}(m, n)=1$, 则 $o(a b)=m n$. 
___
##### Proof
记 $o(a b)=r$. 由于 $a, b$ 可交换, 所以
$$
(a b)^{m n}=a^{m n} b^{m n}=\left(a^m\right)^n\left(b^n\right)^m=e
$$
故 $r \mid m n$. 另一方面, 由于 $a^r b^r=(a b)^r=e$, 有 $a^r=b^{-r}$. 从而 
$$
a^{n r}=\left(a^n\right)^r=\left(a^r\right)^n=\left(b^{-r}\right)^n=\left(b^n\right)^{-r}=e^{-r}=e
$$ 
所以 $m \mid n r$, 又 $m$ 与 $n$ 互素, 故 $m \mid r$. 同理可得 $n \mid r$. 再根据 $m$ 与 $n$ 互素, 得 $m n \mid r$. 所以 $r=m n$, 即 $o(a b)=m n$.
#####
___


## 3. 群的方次数
### 3.1. 群的方次数的定义
对所有$a\in G$, 都有$a^t=e$的最小正整数$t$称为群$G$的方次数, 记为$\exp(G)$. 

### 3.2. 交换群的方次数的判定
设$G$是有限交换群, $g$为$G$中的最大阶元素, 则有$\exp(G) = o(g)$
___
##### Proof
只需要证明对任意的$h\in G$, 都有$h^{o(g)} =e$. 设
$$
o(g) = p_1^{e_1}p_2^{e_2}\cdots p_s^{e_s}, \quad o(h) = p_1^{f_1}p_2^{f_2}\cdots p_s^{f_s}
$$
其中$e_i, f_i\ge 0,\ 1\le i\le s$. 我们只需要证明对于任意的$i$, 都有$e_i\ge f_i$. 否则, 采用反证法, 如果存在某个$j$, 使得$e_j< f_j$, 不妨设$j=1$. 设$g_1 = g^{p_1^{e_1}}$并且$h_1 = h^{p_2^{f_2}\cdots p_s^{f_s}}$. 我们有$o(g_1) = p_2^{e_2}\cdots p_s^{e_s}$并且$o(h_1) = p_1^{f_1}$. 因为$G$为交换群, 并且$\operatorname{gcd}(o(g_1), o(h_1))=1$, 从而 
$$
o\left(g_1 h_1\right)=p_1^{f_1} p_2^{e_2} \cdots p_s^{e_s}>o(g)
$$
与 $g$ 为最大阶元素矛盾. 这就证明了原命题
#####
___

### 3.3. 什么样的群是循环群
1. 设$G$是有限交换群, 则$G$是循环群当且仅当$\exp(G) = |G|$
2. 设$G$是有限交换群, 则$G$是循环群当且仅当对于任意的正整数$m$, 方程$x^m=e$在$G$中的解不超过$m$个
___
##### Proof
1. 必要性显然成立, 下证充分性, 根据[3.2. 交换群的方次数的判定](#3.2.%20交换群的方次数的判定), 可以得到存在$g\in G$, 使得$o(g) = \exp(G)$, 于是$\langle g\rangle$是$G$的子群且其阶为$G$, 所以$G=\langle g\rangle$, 即$G$为循环群.
2. 先证充分性, 设$m=\exp(G)$, 此时$G$中的每个元素都是方程$x^m=e$的根, 于是$\exp(G)=|G|$, 从而$G$是一个循环群. 
   再证必要性, 设$G= \langle g\rangle$, 对于任意的正整数$m$, 设
   $$
   H = \{x\in G\mid x^m=e\}
   $$
   容易验证$H\le G$, 故$H = \langle g^s\rangle$, 其中$s\mid n$并且$|H| = \dfrac{n}{s}$. 根据$H$的定义可以得到
   $$
   (g^s)^m = g^{s m} = e 
   $$
   因此 $n\mid ms\Longrightarrow \dfrac{n}{s}\mid m$, 于是$|H|\le m$. 
#####
___
