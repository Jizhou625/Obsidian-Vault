
## 1. Borel集
### 1.1. Borel集合系
用$\mathscr{O}_{\mathbb{R}^d}$表示$\mathbb{R}^d$中开集组成的集合系, 定义$\mathscr{B}_{\mathbb{R}^n} = \sigma(\mathscr{O}_{\mathbb{R}^n})$是由$\mathscr{B}_{\mathbb{R}^n}$生成的$\sigma$代数. $\mathscr{B}_{\mathbb{R}^n}$中的集合称为$\mathbb{R}^n$中的Borel集.


### 1.2. $\mathscr{B}_{\mathbb{R}}$的生成
设$\mathscr{Q}_{\mathbb{R}} = \{(a, b]\mid a, b\in \mathbb{R}\}$是$\mathbb{R}$上的半环. $\mathscr{P}_{\mathbb{R}}=\{(-\infty, a]\mid a\in \mathbb{R}\}$是$\mathbb{R}$上的$\pi$系. 则
$$
\mathscr{B}_{\mathbb{R}} = \sigma(\mathscr{Q}_{\mathbb{R}}) = \sigma(\mathscr{P}_{\mathbb{R}})
$$
也就是说, 下列的等式成立
$$
\begin{aligned} 
    \mathscr{B}_{\mathbb{R}} &= \sigma(\{(-\infty, a)\mid a\in \mathbb{R}\}) = \sigma(\{(-\infty, a]\mid a\in \mathbb{R}\}) \\ 
    & = \sigma(\{(a, +\infty)\mid a\in \mathbb{R}\}) = \sigma(\{[a, +\infty)\mid a\in \mathbb{R}\}) \\
\end{aligned}
$$
___
##### Proof
因为$\mathscr{B}_{\mathbb{R}}$是由$\mathbb{R}$上全体开集组成的集合系, 又因为$\sigma$代数关于交运算封闭, 因此对任意的$a, b\in \mathbb{R}$, 都有$(-\infty, a]\in \mathscr{B}_{\mathbb{R}}$. 这意味着$\mathscr{B}_{\mathbb{R}} \supset \sigma(\mathscr{P}_{\mathbb{R}})$. 又因为
$$
(a, b] = (-\infty, b]\cap (-\infty, a]^c
$$
于是$\sigma(\mathscr{Q}_{\mathbb{R}})\subset \sigma(\mathscr{P}_{\mathbb{R}})$. 这样, 我们就有$\mathscr{B}_{\mathbb{R}} \supset \sigma(\mathscr{P}_{\mathbb{R}}) \supset \sigma(\mathscr{Q}_{\mathbb{R}})$. 下面只要证明$\sigma(\mathscr{Q}_{\mathbb{R}})\supset \mathscr{B}_{\mathbb{R}}$. 由于$\mathbb{R}$上的开集可以表示为一系列的开区间的并. 因此我们有$\sigma(\mathscr{Q}_{\mathbb{R}})\supset \mathscr{B}_{\mathbb{R}}$成立. 这就证明了
$$
\mathscr{B}_{\mathbb{R}} = \sigma(\mathscr{Q}_{\mathbb{R}}) = \sigma(\mathscr{P}_{\mathbb{R}})
$$
#####
___

### 1.4. $\mathscr{B}_{\mathbb{R}^n}$的生成
设$\mathscr{Q}_{\mathbb{R}^n} = \{(x_1, x_2, \cdots, x_d)\mid a_i< x_i \le  b_i, i=1,2,\cdots, d\}$是$\mathbb{R}^n$上的半环. $\mathscr{P}_{\mathbb{R}^n}=\{(x_1, x_2, \cdots, x_d)\mid x_i\le b\}$是$\mathbb{R}$上的$\pi$系. 则
$$
\mathscr{B}_{\mathbb{R}^n} = \sigma(\mathscr{Q}_{\mathbb{R}^n}) = \sigma(\mathscr{P}_{\mathbb{R}^n})
$$

## 2. $\mathscr{B}_{\mathbb{R}^n}$的进一步讨论

### 2.1. $F_{\sigma}, G_{\delta}$集
若$E\subset \mathbb{R}^n$是可数个闭集的并集, 则称$E$是$F_{\sigma}$集. 

若$E\subset \mathbb{R}^n$是可数个开集的交集, 则称$E$是$G_{\delta}$集.

### 2.2. $F_{\sigma}, G_{\delta}$集的例子
设$\mathbb{R}^n$中全体有理点为$\{r_k\}$, 则有理点集
$$
\bigcup\limits_{k=1}^{\infty} \{r_k\}
$$
是$F_{\sigma}$集.

若$f(\boldsymbol{x})$是定义在开集$G\subset\mathbb{R}^n$上的实值函数, 则$f(\boldsymbol{x})$的连续点集是$G_{\delta}$集

### 2.3. $\mathbb{R}^n$中的闭集和开集
$\mathbb{R}^n$中的每一个闭子集都是一个$G_{\delta}$集, 并且每一个开子集都是一个$F_{\sigma}$集.
___
##### Proof
假设$F$是$\mathbb{R}^n$中的一个闭子集. 定义集合
$$
U_n = \left\{\boldsymbol{x}\in \mathbb{R}^n\mid \|\boldsymbol{x} - \boldsymbol{y}\|< \dfrac{1}{n}, \quad y\in F\right\}
$$
显然$U_n$是一个开集并且$F\subset \bigcap\limits_{n}^{} U_n$. 又因为$F$是闭集, 并且$\bigcap\limits_{n}^{} U_n$的极限是$F$中的点. 因此$\mathbb{R}^n$中的每一个闭子集都是一个$G_{\delta}$集. 同样地, 可以证明, 每一个开子集都是一个$F_{\sigma}$集.
#####
___
