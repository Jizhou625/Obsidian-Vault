## 1. 极限点和导集
### 1.1. 导集的定义
设$E\subset \mathbb{R}^n, \boldsymbol{x}\in \mathbb{R}^n$, 若存在$E$中的互异点列$\{\boldsymbol{x}_k\}$使得
$$
\lim\limits_{k\to\infty}\|\boldsymbol{x}_k - \boldsymbol{x}\| = 0
$$
则称$\boldsymbol{x}$为$E$的极限点(或聚点). 

$E$的极限点的全体记为$E^{\prime}$, 称为$E$的导集. 


### 1.2. 并集的导集等于导集的并集
设$E_1, E_2\subset \mathbb{R}^n$, 则
$$
(E_1\cup E_2)^{\prime} = E_1^{\prime}\cup E_2^{\prime}
$$
___
##### Proof
因为$E_1\subset E_1\cup E_2$, $E_2\subset E_1\cup E_2$. 所以
$$
E_1^{\prime} \subset (E_1\cup E_2)^{\prime}, \quad E_2^{\prime} \subset (E_1\cup E_2)^{\prime}
$$
因此
$$
E_1^{\prime}\cup E_2^{\prime} \subset (E_1\cup E_2)^{\prime}
$$
反之, 若$x\in (E_1\cup E_2)^{\prime}$, 则存在$E_1\cup E_2$中的互异点列$\{\boldsymbol{x}_k\}$使得
$$
\lim\limits_{k\to\infty} \|\boldsymbol{x}_k - \boldsymbol{x}\| = 0
$$
其中必存在一个子列属于$E_1$或属于$E_2$. 这就证明了
$$
E_1^{\prime}\cup E_2^{\prime} \supset (E_1\cup E_2)^{\prime}
$$
于是
$$
(E_1\cup E_2)^{\prime} = E_1^{\prime}\cup E_2^{\prime}
$$
#####
___

### 1.3. Bolzano-Weierstrass 定理
$\mathbb{R}^n$中任意一个有界无限点集$E$至少有一个极限点.


## 2. 开集
### 2.1. 开集的定义
设 $E \subset \mathbb{R}^n$,  如果对于任意的 $\boldsymbol{x} \in E$, 都存在 $\varepsilon>0$ 使得开球
$$
B_{\varepsilon}(\boldsymbol{x})=\left\{\boldsymbol{y} \mid\|\boldsymbol{y}-\boldsymbol{x}\|_2 \leq \varepsilon\right\}
$$
包含在$E$中, 则称$E$是一个开集. 

不难验证, 开集中的每个点都是极限点. 

### 2.2. 开集的例子
$$
\begin{aligned} 
   &\{x \mid a<x<b\}, \\ 
   &\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\} \\  
   &\{\boldsymbol{x} \mid \boldsymbol{x}>\mathbf{0}\} \\  
   &\{X \mid X \succ \mathbf{0}\} \overset{\Delta}{=}\mathbb{S}_{++}^n
\end{aligned}
$$

### 2.3. 开集的运算性质
1. 任意多个开集的并集还是开集, 也就是说, 若$\{G_{\alpha}\mid \alpha\in I\}$是$\mathbb{R}^n$中的一个开集族, 则其并集$G = \bigcup\limits_{\alpha\in I}G_{\alpha}$是开集. 
2. 有限个开集的交还是开集, 也就是说, 若$G_1, G_2, \cdots, G_k$是$\mathbb{R}^n$中的开集, 则$G = \bigcap\limits_{i=1}^kG_i$也是开集. 但是, 无限个开集的交不一定是开集. 考虑集合列$\left\{G_k = \left(0, 1 +\dfrac{1}{n}\right)\right\}$, 我们有$\bigcap\limits_{k=1}^{\infty}G_k = \left(0, 1\right]$不是开集

### 2.4. 开集的构造
1. $\mathbb{R}$中的非空开集是由可数个互不相交的开区间的并集, 这里的开区间也包括无穷开区间.
2. $\mathbb{R}^n$中的非空开集$G$是由可列个互不相交的半开半闭方体的并集
___
##### Proof: 
1. 设$G$是$\mathbb{R}$中的开集, 对于$G$中的任意一点$a$, 由于$a$是$G$的内点, 因此存在$\varepsilon>0$使得$(a-\varepsilon, a+\varepsilon)\subset G$. 现在设
   $$
   a^{\prime} = \inf\{x\mid (x, a)\subset G\}, \quad a^{\prime\prime} = \sup\{x\mid (a, x)\subset G\}
   $$
   显然$a^{\prime}<a< a^{\prime\prime}$且$(a^{\prime}, a^{\prime\prime})\subset G$. 我们称这样的开区间$(a^{\prime}, a^{\prime\prime})$为$G$关于点$a$的构成区间$I_{a}$. 考虑构成区间$I_a$和$I_b$, 不妨设$a<b$. 若有$I_a\cap I_b\neq \varnothing$, 则有$b^{\prime}< a^{\prime\prime}$, 取$x\in I_a\cap I_b$, 则有$I_x = I_a=I_b$, 这就证明了所有的构成区间或者重合, 或者互不相交. 最后, 因为$\mathbb{R}$中的有理数是可数的, 且每个开区间至少包含一个有理数, 因此构成区间是可数的.  
2. 考虑将$\mathbb{R}^n$用格点分为可列个边长为$1$的半开闭方体, 其全体记为$\Gamma_0$. 再将$\Gamma_0$中的每个方体的每一条边二等分, 得到$\Gamma_1$, 按此方法二分下去, 得到所含方体越来越小的方体族组成的序列$\{\Gamma_k\}$. 现在把$\Gamma_0$中在$G$内的所有方体取出来, 记其全体为$H_0$, 再把$\Gamma_1$中含于$G \backslash \bigcup\limits_{J\in H_0} J$的方体取出来, 记其全体为$H_1$. 以此类推, $H_k$为$\Gamma_k$中含于
   $$
   G \backslash \bigcup\limits_{i=0}^{k-1} \bigcup\limits_{J\in H_i} J
   $$
   的方体全体. 因为$G$是开集, 因此对任意的$x\in G$, 存在$\delta>0$, 使得$B(x, \delta)\subset G$. 而$\Gamma_k$中的方体的直径当$k\to\infty$时趋于$0$. 从而得到$x$最终必然落入某个$\Gamma_k$的方体, 这说明
   $$
   G = \bigcup\limits_{k=0}^{\infty} \bigcup\limits_{J\in H_k} J
   $$
   又因为可列个可列集的并仍然是可列集, 因此$G$是可列个半开半闭方体的并集.
#####
___


### 2.5. 内点集
设$E\subset \mathbb{R}^n$, 对$x\in E$, 若存在$\delta>0$, 使得$B(x, \delta)\subset E$, 则称$x$是$E$的内点. $E$的内点全体记为$E^{\circ}$, 称为$E$的内核. 

$$
\begin{gathered}
(\{x \mid a \leq x \leq b\})^{\circ}=\{x \mid a<x<b\} \\
(\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\})^{\circ}=\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\} \\
(\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x} \geq \mathbf{0}\})^{\circ}=\{\boldsymbol{x} \mid \mathbf{1}>\boldsymbol{x}>\mathbf{0}\} \\
(\{X \mid I \succeq X \succeq 0\})^{\circ}=\{X \mid I \succ X \succ 0\}
\end{gathered}
$$


## 3. 闭集
### 3.1. 闭集的定义
设 $E \subset \mathbb{R}^n$, 如果它的补集$E^c=\mathbb{R}^n \backslash E$是开集, 则称$E$是一个闭集.

### 3.2. 闭集的例子
$$
\begin{aligned} 
   &\{x \mid a \leq x \leq b\}\\ 
   &\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\}\\ 
   &\{\boldsymbol{x} \mid \boldsymbol{x} \geq \mathbf{0}\}\\ 
   &\{X \mid X \succeq \mathbf{0}\} = \mathbb{S}_{+}^n
\end{aligned}
$$

### 3.3. 闭集的运算性质
1. 有限多个闭集的并集还是闭集, 也就是说, 如果$F_1, F_2, \cdots, F_k$是$\mathbb{R}^n$中的闭集, 则其并集$\bigcup\limits_{i=1}^{k}F_i$也是闭集. 但是, 可数个闭集的并未必是闭集. 考虑集合列$\left\{F_k = \left[\dfrac{1}{n}, 1\right]\right\}$, 我们有$\bigcup\limits_{k=1}^{\infty}F_k = \left(0, 1\right]$不是闭集
2. 任意多个闭集的交集仍然是闭集. 也就是说, 如果$\{F_{\alpha}\mid \alpha \in I\}$是$\mathbb{R}^n$中的一个闭集族, 则其交集$F = \bigcap\limits_{\alpha\in I}F_{\alpha}$是闭集. 


### 3.4 闭集与导集
设$E\supset \mathbb{R}^n$. 若$E\supset E^{\prime}$(即$E$包含$E$的一切极限点), 则$E$是闭集. 
___
##### Proof
用反证法, 假设集合$E^c$不是开集, 则存在某个$x\in E^c$和序列$\{x_k\}$满足
$$
x_k \notin E^c, \quad \lim_{k\to\infty}x_k = x
$$ 
于是$x_k\in E$, $\lim\limits_{k\to\infty}x_k = x\in E^{\prime}$, 由于$E\supset E^{\prime}$, 因此$x\in E$, 这与$x\in E^c$矛盾. 从而$E^c$是开集, $E$是闭集.
#####
___

### 3.5. 闭包
设$E\subset \mathbb{R}^n$, 则$E$的闭包定义为
$$
\overline{E} = E \cup E^{\prime}
$$
利用内点集的定义, 闭包也可以被定义为
$$
\overline{E} = \left((E^c)^{\circ}\right)^c
$$
下面给出了闭包的一些例子
$$
\begin{gathered}
\overline{\{x \mid a \leq x<b\}}=\{x \mid a \leq x \leq b\} \\
\overline{\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\}}=\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\} \\
\overline{\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x}>\mathbf{0}\}}=\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x} \geq \mathbf{0}\} \\
\overline{\{X \mid I \succ X \succ 0\}}=\{X \mid I \succeq X \succeq 0\}
\end{gathered}
$$

### 3.6. 边界点
设$E\subset \mathbb{R}^n$, 如果$x\in \overline{E}$, 但$x\notin E^{\circ}$, 则称$x$为$E$的边界点. $E$的边界点集记为$\partial E$.
$$
\begin{gathered}
\partial(\{x \mid a \leq x<b\})=\{a, b\} \\
\partial(\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\})=\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|=1\}\\
\partial(\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x}>\mathbf{0}\})=\left\{\boldsymbol{x} \mid 0 \leq x_i \leq 1 . \forall i, \text { and } \exists j \text { such that } x_j=0 \text { or } 1\right\} \\ 
\partial(\{X \mid I \succ X \succ 0\})=\left\{X \mid 0 \leq \lambda_i(X) \leq 1, \forall i \text { and } \exists j \text { such that } \lambda_j(X)=0 \text { or } 1\right\}
\end{gathered}
$$


## 4. 紧集
### 4.1. 紧集的定义
设$E\subset \mathbb{R}^n$, 如果$E$的任何一个开覆盖都包含有限子覆盖, 我们就称$E$为紧集. 

### 4.2. Heine-Borel有限子覆盖定理
$\mathbb{R}^n$中的有界闭集的任一开覆盖均含有一个有限子覆盖. 

反之, 设$E\subset \mathbb{R}^n$, 若$E$的任一开覆盖都包含有限子覆盖, 则$E$是有界闭集. 
___
##### Proof
设$F$是$\mathbb{R}^n$中的有界闭集, $\Gamma$是$F$的一个开覆盖. 由于有理数是可数的, 因此$\mathbb{R}^n$中点集$E$的任意一个开覆盖都含有一个可数的子覆盖. 因此我们可以假定$\Gamma$由可列个开集组成
$$
\Gamma = \{G_1, G_2, \cdots, G_i, \cdots\}
$$
令
$$
H_k = \bigcup\limits_{i=1}^{k} G_i, \quad L_k = F\cap H_k^c, \quad k=1,2,\cdots 
$$
显然, $H_k$是开集, $L_k$是闭集且有$L_k\supset L_{k+1}$. 
1. 若存在$k_0$, 使得$L_{k_0}$是空集, 则已经得证
2. 若一切$L_k$都不是空集, 由Cantor闭区间套定理, 可以得到存在$x_0\in L_k$, 即$F$中存在点$x_0$, 不属于一切$H_k$, 与原假设矛盾

综上所述, 我们得到了$\mathbb{R}^n$中的有界闭集的任一开覆盖均含有一个有限子覆盖. 

反之, 若$E$的任一开覆盖都包含有限子覆盖, 设$y\in E^c$, 则对于每一个$x\in E$, 存在$\delta_x>0$使得
$$
B(x, \delta_x) \cap B(y, \delta_x) = \emptyset
$$
显然, $\{B(x, \delta_x)\mid x\in E\}$是$E$的一个开覆盖. 由题设知道存在有限的子覆盖, 设为
$$
B(x_1, \delta_{x_1}),\ B(x_2, \delta_{x_2}),\ \cdots,\ B(x_n, \delta_{x_n})
$$
这就得到了$E$是有界集合, 再设
$$
\delta_0 = \min\{\delta_{x_1}, \cdots, \delta_{x_n}\}
$$
则$B(y, \delta_0)\cap E=\varnothing$, 即$y\notin E^{\prime}$. 这说明$E^{\prime}\subset E$, 即$E$是一个闭集.
#####
___

### 4.3. 紧集的判定
设$E\subset \mathbb{R}^n$, $E$是紧集当且仅当$E$是有界闭集








