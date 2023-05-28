## 1. 戴德金分割
### 1.1. 最小上界性
设$S$是有序集, 如果对于$\forall E\neq \varnothing\subset S$, $E$上有界$\Longrightarrow\sup E \in S$, 则称$S$具有最小上界性. 具有最小上界性的每个有序集合都一定有最大下界性. 
___
##### Proof
设$S$是具有最小上界性的有序集合, 对于任意的$B\subset S$, $B$不空且$B$下有界. 令$L$是$B$的所有下界的集合, 因为$S$具有最小上界性, 因此$\alpha =\sup L\in S$, 容易证明$\alpha=\inf B$
#####
___
### 1.2. 分划
对任意集合$\alpha\subset \mathbb{Q}$, 如果$\alpha$满足下列三个条件
1. **非空非全性**: $\alpha$不空, $\alpha\neq \mathbb{Q}$
2. **左传递性**: $\forall p\in \alpha$, 如果 $\exists q\in \mathbb{Q}$ 满足 $q<p$, 则$q\in \alpha$
3. **没有最大元**: $\forall p\in \alpha$, $\exists r\in \alpha$满足$p<r$
   
则称$\alpha$是一个分划

### 1.3. 有理分割
将集合$\{x\in \mathbb{Q}\mid x<r\}$记作$D_r$, 并称为有理分割, 可以证明, 有理分割是一个分划

### 1.4. 存在不是有理分割的分划
考虑下面的集合
$$
T = \{x\in \mathbb{Q}\mid x<0, x^2>2\}
$$
我们证明这是一个分划
1. 显然$T$非空非全
2. 对于任意的$s<0$并且$s^2>2$, 取$y\in \mathbb{Q}$, 若$y<s<0$, 则我们有$y^2>ys>s^2>2$, 因此我们有$y\in T$
3. 对任意的$s\in T$, 构造$y=s -\dfrac{s^2-2}{s+2}$, 容易有$y>s$, 而$y^2-2 = 2 \dfrac{s^2-2}{(s+2)^2}>0$, 因此我们有$y^2>2$, 也就是说$y\in T$. 

因此$T$是一个分划. 下面证明$T$不是一个有理分割. 假设$\exists r\in \mathbb{Q}$, 使得$D_r = T$, 即
$$
\{x\in \mathbb{Q}\mid x<r\} = \{x\in \mathbb{Q}\mid x<0, x^2>2\}
$$
显然可以得到$r<0$. 若$r^2>2$, 构造一个数$y = r-\dfrac{r^2-2}{r+2}= \dfrac{2r+2}{r+2}$, 容易有$y>r$, 因此我们有$y\notin D_r$. 但我们有$y\in T$, 这就与$D_r = T$产生了矛盾. 同理, 当$r^2<2$的时候也可以得到矛盾. 而当$r^2=2$时, 不难证明$r$不是有理数. 因此存在不是有理分割的分划. 
### 1.3. 戴德金分割
把所有分划集合$\alpha$组成的集合族记作为$\mathbb{R}$, 我们定义在$\mathbb{R}$上的偏序关系为: 如果$\alpha\subsetneqq \beta$, 则$\alpha < \beta$. 分划$\alpha$和由$\alpha$定义的集合族$\mathbb{R}$
___
##### Proof: 
设$A$是$\mathscr{R}$的不空真子集, 且$A$上有界$\beta\in \mathscr{R}$. 设$\gamma = \bigcup\limits_{\alpha\in A}\alpha$. 显然$r$满足分划的三条性质, $r\in \mathscr{R}$. 又因为$\gamma$是$A$的最小上界, 因此$S$具有最小上界性
#####
___


## 2. Cauchy序列构造实数
### 2.1. Cauchy序列
一个比例数序列$\{a_n\}_{n=0}^{\infty}$被叫做是Cauchy序列, 当且仅当对于$\forall \varepsilon>0$, $\exists N\ge0$, 使得对一切$i,j\ge N,\ d(a_i,a_j)\le \varepsilon$. 

### 2.2. 用比例数界定实数
设$x$是一个正的实数, 
