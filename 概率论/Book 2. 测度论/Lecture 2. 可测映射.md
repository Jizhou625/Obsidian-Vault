## 1. 可测映射和可测函数
### 1.1. 映射
设$X$和$Y$是任意给定的集合. 如果对每个$x\in X$, 存在唯一的$f(x)\in Y$与之对应, 则称对应关系$f$是从$X$到$Y$的映射. 对于任意的$B\subset Y$, 称
$$
f^{-1}(B) = \{x\mid f(x)\in B\}
$$
为集合$B$在映射$f$下的原像. 对任何$Y$上的集合系$\mathscr{E}$, 称
$$
f^{-1} \mathscr{E} \triangleq\left\{f^{-1} (B)\mid B \in \mathscr{E}\right\}
$$
为集合系$\mathscr{E}$在映射$f$下的原像. 

### 1.2. 原像的性质
1. $f^{-1} (\varnothing)=\varnothing, \quad f^{-1} (Y)=X$
2. $B_1 \subset B_2 \Longrightarrow f^{-1} (B_1) \subset f^{-1} (B_2)$
3. $\left(f^{-1} (B)\right)^c=f^{-1} (B^c), \quad \forall B \subset Y$
4. 对任意集合 $T$, 有
    $$
    \begin{aligned} 
        f^{-1} \bigcup_{t \in T} A_t &=\bigcup_{t \in T} f^{-1} A_t, & \forall\left\{A_t \subset Y, t \in T\right\} \\
    f^{-1} \bigcap_{t \in T} A_t &= \bigcap_{t \in T} f^{-1} A_t, \quad &\forall\left\{A_t \subset Y, t \in T\right\} 
    \end{aligned}
    $$
5. **原像和生成$\sigma$域可交换**: 对于 $Y$ 上的任何集合系 $\mathscr{E}$, 有
    $$
    \sigma\left(f^{-1} (\mathscr{E})\right)=f^{-1} (\sigma(\mathscr{E}))
    $$
___
**Proof**: 我们只证明结论5. 对$Y$上的任意集合系$\mathscr{E}$, 显然$f^{-1}(\sigma(\mathscr{E}))$是一个$\sigma$域, 故
$$
\sigma(f^{-1}(\mathscr{E}))\subset f^{-1}(\sigma(\mathscr{\mathscr{E}}))
$$ 
另一方面, 设
$$
\mathscr{G} = \{B\subset Y \mid f^{-1}(B)\in\sigma(f^{-1}(\mathscr{E}))\}
$$
显然$\mathscr{G}$是一个$\sigma$域且$\mathscr{E}\subset \mathscr{G}$, 因此$\sigma(\mathscr{E})\subset \mathscr{G}$, 因而
$$
f^{-1}(\sigma(\mathscr{E}))\subset f^{-1}(\mathscr{G})\subset \sigma(f^{-1}(\mathscr{E}))
$$
这就证明了结论5

### 1.3. 可测映射
给定可测空间$(X, \mathscr{F})$和$(Y, \mathscr{S})$以及$f:X\to Y$, 如果$f^{-1}(\mathscr{S})\subset \mathscr{F}$, 则称$f$是从$(X, \mathscr{F})$到$(Y, \mathscr{S})$的可测映射或随机元. 而$\sigma(f)=f^{-1}(\mathscr{S})$叫做使得映射$f$可测的最小$\sigma$域.

### 1.4. 可测映射的判定
1. **简化判定**: 设$\mathscr{E}$是$Y$上的任意给定的集合系. 则$f$是$(X, \mathscr{F})$到$(Y, \sigma(\mathscr{E}))$的可测映射当且仅当
   $$
   f^{-1}(\mathscr{E})\subset \mathscr{F}
   $$
2. **复合映射**: 设$g$是可测空间$(X, \mathscr{F})$到$(Y, \mathscr{S})$的可测映射, $f$是$(Y, \mathscr{S})$到$(Z, \mathscr{Z})$的可测映射, 则$f\circ g$是$(X, \mathscr{F})$到$(Z, \mathscr{Z})$的可测映射

### 1.5. 可测函数
从可测空间$(X, \mathscr{F})$到$(\overline{\mathbb{R}}, \mathscr{B}_{\overline{\mathbb{R}}})$的可测映射称为$(X, \mathscr{F})$上的可测函数. 特别地, 从$(X, \mathscr{F})$到$(\mathbb{R}, \mathscr{B}_{\mathbb{R}})$的可测映射称为$(X, \mathscr{F})$上的有限值可测函数或随机变量. 

根据Borel集的定义, 我们知道$f$是$(X, \mathscr{F})$上的可测函数当且仅当
1. $\{f<a\}\in \mathscr{F},\ \forall a\in \mathbb{R}$
2. $\{f\le a\}\in \mathscr{F},\ \forall a\in \mathbb{R}$
3. $\{f>a\}\in \mathscr{F},\ \forall a\in \mathbb{R}$
4. $\{f\ge a\}\in \mathscr{F},\ \forall a\in \mathbb{R}$

如果$f, g$是可测函数, 则
$$
\{f<g\}, \quad \{f\le g\}, \quad \{f = g\}\in \mathscr{F}
$$
特别地, $\{f=a\}\in \mathscr{F}, \ \forall a\in \overline{\mathbb{R}}$

## 2. 可测函数的运用
### 2.1. 可测函数的四则运算
如果$f, g$是可测函数, 则
1. 对于任何$a\in \overline{\mathbb{R}}$, $af$是可测函数. 
2. 如果$f+g$有意义, 即对每个$x\in X$, $f(x)+g(x)$均有意义, 则它是可测函数.
3. $fg$是可测函数.
4. 如果$g(x)\neq 0, \forall x\in X$, 则$\dfrac{f}{g}$是可测函数. 
   
### 2.2. 可测函数的极限
如果$\{f_n\mid n=1,2,\cdots\}$是可测函数序列, 则
1. $\inf\limits_{n}f_n$是可测函数.
2. $\sup\limits_{n}f_n$是可测函数.
3. $\mathop{\lim\inf}\limits_{n\to\infty}f_n$ 是可测函数.
4. $\mathop{\lim\sup}\limits_{n\to\infty}f_n$ 是可测函数.

### 2.3. 有限分割
有限个两两不交的集合$\{A_i\subset X, i=1,2,\cdots,n\}$如满足$\bigcup\limits_{i=1}^nA_i =X$, 就把它称为空间$X$的一个有限分割. 如果对每个$i=1,2,\cdots,n$有$A_i\in \mathscr{\mathscr{F}}$, 则$X$的有限分割$\{A_i\mid i=1,2,\cdots\}$称为可测空间$(X, \mathscr{F})$的有限可测分割. 对于可测空间$(X, \mathscr{F})$上的函数$f: X\to \mathbb{R}$, 如果存在有限可测分割$\{A_i\in \mathscr{F}\mid i=1,2\cdots, n\}$和实数$\{a_i\mid i=1,2,\cdots, n\}$使得
$$
f = \sum\limits_{i=1}^{n} a_i\mathbb{I}_{A_i}
$$
则称之为简单函数.