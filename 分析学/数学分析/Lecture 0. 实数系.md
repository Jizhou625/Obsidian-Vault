## 1. 戴德金分割
### 1.1. $\sqrt{2}$的构造
1. 设 $A$ 是使得 $p^2<2$ 的一切正有理数 $p$ 组成的集合, $B$ 是使得 $p^2>2$ 的一切正有理数 $p$ 组成的集合.
2. 对于每个有理数 $p>0$, 配置一个数 $q=p-\dfrac{p^2-2}{p+2}$, 则 $q^2-2=2 \dfrac{p^2-2}{(p+2)^2}$
3. 如果 $p$ 在 $A$ 中, 那么由 $p^2-2<0$, 根据 (2) 中的构造, 容易得到 $q^2<2$ 且 $q>p$, 因而$A$ 中没有最大数; 同理, 如 果 $p$ 在 $B$ 中, 则 $q$ 也在 $B$ 中且 $q<p$. 这就说明了 $B$ 中没有最小数. 于是, $A, B$ 的划分就定义了唯一的 $\sqrt{2}$. 

### 1.2. 最小上界性
**上确界**: 设$S$是有序集, $E\subset S$, 如果$\exists \beta \in S$, 对$\forall x \in E$都有$x\le \beta$, 我们就说$E$有上界, 并称$\beta$是$E$的一个上界. 如果存在一个$\alpha \in S$, 它具有下列性质
1. $\alpha$是$E$的上界
2. 对$\forall \gamma<\alpha$, $\gamma$不是$E$的上界

则称$\alpha$为$E$的最小上界或上确界, 记作$a=\sup E$

**最小上界性**: 设$S$是有序集, 对于$\forall E\neq \varnothing\subset S$, $E$上有界$\Longrightarrow\sup E \in S$, 则称$S$具有最小上界性. 

**最小上界性和最大下界性**: 设$S$是具有最小上界性的有序集合, $B\subset S$, $B$不空且$B$下有界. 令$L$是$B$的所有下界的集合, 因为$S$具有最小上界性, 因此$\alpha =\sup L\in S$, 容易证明$\alpha=\inf B$. 这意味着有最小上界性的每个有序集合都一定有最大下界性. 

### 1.3. 戴德金分割
**分划**: 规定分划是具有以下三种性质的任意集合$\alpha\subset Q$
1. **非空非全集**: $\alpha$不空, $\alpha\neq Q$
2. **左传递**: $\forall p\in \alpha$, 如果$\exists q\in Q$满足$q<p$, 则$q\in \alpha$
3. **没有最大元**: $\forall p\in \alpha$, $\exists r\in \alpha $满足$p<r$
   
把所有满足上述条件的分划集合$\alpha$组成的集合族记作为$\mathscr{R}$, 我们定义在$\mathscr{R}$上的偏序关系为: 如果$\alpha\subsetneqq \beta$, 则$\alpha < \beta$. 根据分划的左传递性, 不难验证$\mathscr{R}$是一个有序集合. 此外, $\mathscr{R}$具有最小上界性
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
