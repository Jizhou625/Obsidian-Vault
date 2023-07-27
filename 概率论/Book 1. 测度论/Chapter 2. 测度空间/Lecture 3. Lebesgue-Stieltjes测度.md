## 1. 准分布函数
### 1.1. 准分布函数的定义
$\mathbb{R}^n$上的实值函数$F$将称为准分布函数, 如果它满足
1. 对每个$i=1,2,\cdots, n$和每个$x_1, x_2, \cdots, x_{i-1}, x_{i+1}, \cdots, x_n\in \mathbb{R}$.
   $$
   F(x_1, x_2, \cdots, x_{i-1}, \cdot, x_{i+1}, \cdots, x_n)
   $$
   作为第$i$个变量的函数右连续
2. 对任何的$\boldsymbol{a} = (a_1, a_2, \cdots, a_n)\in \mathbb{R}^n$和$\boldsymbol{b} = (b_1, b_2, \cdots, b_n)\in \mathbb{R}^n$, 记
   $$
   C = \{\boldsymbol{c} = (c_1, \cdots, c_n)\mid c_i = a_i \text{ or } b_i, i=1, 2, \cdots, n\}
   $$
   对每个$\boldsymbol{c} = (c_1, c_2, \cdots, c_n)\in C$, 记$n(c) = \# \{i\mid c_i = a_i\}$, 则当$\boldsymbol{a}\le \boldsymbol{b}$时, 有
   $$
   \sum\limits_{\boldsymbol{c}\in C}^{}  (-1)^{n(c)} F(\boldsymbol{c}) \ge 0 
   $$

### 1.2. $n$次增量
对任意满足$a\le b$的$a, b\in \mathbb{R}$, 定义$F$的一次增量为
$$
\Delta_{(a, b]} F = F(b) - F(a)
$$
接下来, 我们定义二次增量, 首先对$F(\cdot, \cdot)$的第一个变量求一次增量
$$
\Delta_{(a_1, b_1]}F(\cdot, \cdot) = F(b_1, \cdot) - F(a_1, \cdot)
$$
接着, 对$\Delta_{(a_1, b_1]}F(\cdot, \cdot)$的第二个变量求一次增量
$$
\Delta_{(a_2, b_2]}\left(\Delta_{(a_1, b_1]}F(\cdot, \cdot)\right) = F(b_1, b_2) - F(b_1, a_2) - F(a_1, b_2) + F(a_1, a_2)
$$
交换求增量的顺序, 仍然可以得到相同的结果, 因此我们可以把二次增量定义为
$$
\Delta^2_{(\boldsymbol{a}, \boldsymbol{b}]} F = F(b_1, b_2) - F(b_1, a_2) - F(a_1, b_2) + F(a_1, a_2)
$$
依此类推, 可以得到$n$次增量的定义
$$
\Delta^n_{(\boldsymbol{a}, \boldsymbol{b}]} F = \sum\limits_{\boldsymbol{c}\in C}^{}  (-1)^{n(c)} F(\boldsymbol{c})
$$
因此准分布函数中的第2条定义可以理解为$n$次增量非负. 

### 1.3. $\mathscr{Q}_{\mathbb{R}^n}$上准分布函数导出的测度
如果$F$是准分布函数, 则
$$
\mu_F((\boldsymbol{a}, \boldsymbol{b}]) = \begin{cases} \Delta^n_{(\boldsymbol{a}, \boldsymbol{b}]} F, \quad & \boldsymbol{a}\le \boldsymbol{b} \\ 0, \quad & \boldsymbol{a} > \boldsymbol{b} \end{cases}
$$
则$\mu$是半环$\mathscr{Q}_{\mathbb{R}^n}$上的测度.
___
##### Proof: 
不难证明$\mu_F(\varnothing)=0$, 因此我们只要验证$\mu$具有可列可加性. 为了证明该结论, 我们首先需要推广$n$次增量的定义方式, 设$F: \mathbb{R}^d\to \mathbb{R}$, 其一次增量定义为
$$
\Delta_{(a, b]} F(\cdot , x_2, \cdots, x_d) = F(b, x_2, \cdots, x_d) - F(a, x_2, \cdots, x_d)
$$
类似地, 其$n$次增量定义为
$$
\Delta_{(\boldsymbol{a}, \boldsymbol{b}]} F(\cdot , x_{n+1}, \cdots, x_m) = F(\boldsymbol{b}, x_{n+1}, \cdots, x_m ) - F(\boldsymbol{a}, x_{n+1}, \cdots, x_m), \quad n\le  m
$$
考虑函数$F(\cdot , x_{n+1}, \cdots, x_m)$, 它是一个$\mathbb{R}^n\to \mathbb{R}$的准分布函数. 因此这样的定义方式是合理的. 

根据$\mu_F$的定义, 不难证明$\mu_F$是有限可加的, 为了证明$\mu_F$是可列可加的, 我们分成两部分来证明: 


1. 如果$(\boldsymbol{a}_i, \boldsymbol{b}_i)\in \mathscr{Q}_{\mathbb{R}^d}$两两不交并且
   $$
   \bigcup\limits_{i=1}^{\infty} (\boldsymbol{a}_i, \boldsymbol{b}_i] \subset (\boldsymbol{a}, \boldsymbol{b}]
   $$
   则有
   $$
   \mu((\boldsymbol{a}, \boldsymbol{b}])\ge \sum\limits_{i=1}^{\infty} \mu((\boldsymbol{a}_i, \boldsymbol{b}_i])\tag{2.1.1}
   $$
2. 如果$(\boldsymbol{a}_i, \boldsymbol{b}_i)\in \mathscr{Q}_{\mathbb{R}^d}$两两不交并且
   $$
   \bigcup\limits_{i=1}^{\infty} (\boldsymbol{a}_i, \boldsymbol{b}_i] = (\boldsymbol{a}, \boldsymbol{b}]
   $$
   则有
   $$
   \mu((\boldsymbol{a}, \boldsymbol{b}])\le \sum\limits_{i=1}^{\infty} \mu((\boldsymbol{a}_i, \boldsymbol{b}_i]) \tag{2.1.2}
   $$

首先证明**结论1**, 我们使用数学归纳法: 
当$d=1$时, 因为$(a_i, b_i]$两两不交, 因此我们可以将其重新排序得到
$$
a\le a_{(1)} \le b_{(1)} \le a_{(2)} \le b_{(2)}\le \cdots \le b_{(n)} \le b
$$
对任意的$n\ge 1$, 有
$$
\begin{aligned} 
\mu((a, b]) &= F(b) - F(a) \\ 
& = F(a_{(1)}) - F(a) + \sum\limits_{i=1}^{n} [F(b_{(i)}) - F(a_{(i)})] +\sum\limits_{i=1}^{n-1} [F(a_{(i+1)}) - F(b_{(i)})] + F(b) - F(b_{(n)}) \\
& \ge \sum\limits_{i=1}^{n} [F(b_{(i)}) - F(a_{(i)})] \\
& = \sum\limits_{i=1}^{n} \mu((a_{(i)}, b_{(i)}])
\end{aligned}
$$
取$n\to\infty$可以得到
$$
\mu((a, b])\ge \sum\limits_{i=1}^{\infty} \mu((a_i, b_i])
$$
假设对任意的$d\le k$, 结论1都成立, 我们来证明$d=k+1$时结论1成立. 事实上, 我们有
$$
\mu((\boldsymbol{a}, \boldsymbol{b}]) = \Delta^{k+1}_{(\boldsymbol{a}, \boldsymbol{b}]}F = \Delta_{(\boldsymbol{a}_{k}, \boldsymbol{b}_{k}]}^k F(\cdot, b_{k+1}) - \Delta_{(\boldsymbol{a}_{k}, \boldsymbol{b}_{k}]}^k F(\cdot, a_{k+1})
$$
考虑所有的$(\boldsymbol{a}_{i}, \boldsymbol{b}_{i}] (1\le i\le n)$在前$k$维度上的投影, 如果它们的投影有交集, 则在第$k+1$维将空间切分成几个不同的子区域, 使得每个子区域内的超长方体的投影在前$k$维度上不相交. 不妨设子区域的分割为$a_{k+1} = x_{(0)} < x_{(1)} < \cdots < x_{(t)} < x_{(t+1)} = b_{k+1}$. 于是, 我们有
$$
\begin{aligned} 
\mu((\boldsymbol{a}, \boldsymbol{b}]) &= \Delta_{(\boldsymbol{a}_{k}, \boldsymbol{b}_{k}]}^k F(\cdot, b_{k+1}) - \Delta_{(\boldsymbol{a}_{k}, \boldsymbol{b}_{k}]}^k F(\cdot, a_{k+1}) \\ 
&= \sum\limits_{i=1}^{t+1} \Delta_{(\boldsymbol{a}_{k}, \boldsymbol{b}_{k}]}^k F(\cdot, x_{(i)}) - \Delta_{(\boldsymbol{a}_{k}, \boldsymbol{b}_{k}]}^k F(\cdot, x_{(i-1)}) \\
\end{aligned}
$$
在每个子区域内, 我们可以利用$k$维的归纳假设, 得到
$$
\mu((\boldsymbol{a}, \boldsymbol{b}])\ge \sum\limits_{i=1}^{\infty} \mu((\boldsymbol{a}_i, \boldsymbol{b}_i])
$$

接下来, 证明**结论2**: 

对任意的$\varepsilon>0$, 根据$F$的右连续性, 我们可以找到$\boldsymbol{\delta}_i>0$, 使得
$$
F(\boldsymbol{b}_i+\boldsymbol{\delta}_i) - F(\boldsymbol{b}_i) < \frac{\varepsilon}{2^i}
$$
于是, 对任意的$\boldsymbol{\eta}>0$, 开区间列$\{(\boldsymbol{a}_i, \boldsymbol{b}_i+\boldsymbol{\delta}_i)\}$形成了闭区间$[\boldsymbol{a}+\boldsymbol{\eta}, \boldsymbol{b}]$的一个开覆盖, 因此, 存在$n$使得
$$
\bigcup\limits_{i=1}^{n} (\boldsymbol{a}_i, \boldsymbol{b}_i+\boldsymbol{\delta}_i]\supset[\boldsymbol{a}+\boldsymbol{\eta}, \boldsymbol{b}]\supset (\boldsymbol{a}+\boldsymbol{\eta}, \boldsymbol{b}]
$$
对维度使用数学归纳法, 我们可以证明
$$
\begin{aligned} 
   \mu((\boldsymbol{a} + \boldsymbol{\eta}, \boldsymbol{b}])) &= \Delta_{(\boldsymbol{a}_{k} + \boldsymbol{\eta}_k, \boldsymbol{b}_{k}]}^k F(\cdot, b_{k+1}) - \Delta_{(\boldsymbol{a}_{k} + \boldsymbol{\eta}_k, \boldsymbol{b}_{k}]}^k F(\cdot, a_{k+1} + \eta_{k+1}) \\ 
   &\le \sum\limits_{i=1}^{n}\mu((\boldsymbol{a}_i, \boldsymbol{b}_i]) +\varepsilon  \\ 
   & \le \sum\limits_{i=1}^{\infty}\mu((\boldsymbol{a}_i, \boldsymbol{b}_i]) +\varepsilon
\end{aligned}
$$
在这里, 先令$\boldsymbol{\eta}\to 0$, 由$F$的右连续性, 可以得到
$$
\mu((\boldsymbol{a}, \boldsymbol{b}]) \le \sum\limits_{i=1}^{\infty}\mu((\boldsymbol{a}_i, \boldsymbol{b}_i]) +\varepsilon
$$
再令$\varepsilon\to 0$, 可以得到
$$
\mu((\boldsymbol{a}, \boldsymbol{b}]) \le \sum\limits_{i=1}^{\infty}\mu((\boldsymbol{a}_i, \boldsymbol{b}_i]) 
$$
这就证明了结论2. 


结合$(2.1.1)$和$(2.1.2)$, 我们证明了$\mu$是可列可加的, 因此$\mu$是$\mathscr{E}$上的测度.
#####
___

## 2. Lebesgue-Stieltjes测度
### 2.1. $\mathscr{Q}_{\mathbb{R}^n}$上的Lebesgue-Stieltjes测度
考虑$\mathbb{R}^n$上的准分布函数$F$, 根据[$\mathscr{Q}_{\mathbb{R} n}$上准分布函数导出的测度](Lecture%203.%20Lebesgue-Stieltjes测度#1.3.%20$%20mathscr{Q}_{%20mathbb{R}%20n}$上准分布函数导出的测度), 我们可以得到$F$在半环$\mathscr{Q}_{\mathbb{R}^n}$上定义的有限测度$\mu_F$.
$$
\mu_F((\boldsymbol{a}, \boldsymbol{b}]) = \begin{cases} \Delta^n_{(\boldsymbol{a}, \boldsymbol{b}]} F, \quad & \boldsymbol{a}\le \boldsymbol{b} \\ 0, \quad & \boldsymbol{a} > \boldsymbol{b} \end{cases}
$$
测度$\mu_F$称为半环$\mathscr{Q}_{\mathbb{R}^n}$上的Lebesgue-Stieltjes测度.

特别地, 如果
$$
F(\boldsymbol{b})  =b_1b_2\cdots b_n \Longrightarrow \mu_F((\boldsymbol{a}, \boldsymbol{b}]) = \prod\limits_{i=1}^{n} (b_i - a_i)
$$
为$\mathbb{R}^n$中矩体的体积, 我们称测度$\mu_F$为半环$\mathscr{Q}_{\mathbb{R}^n}$上的Lebesgue测度.

### 2.2. $\mathscr{B}_{\mathbb{R}^n}$上的Lebesgue-Stieltjes测度
考虑$\mathbb{R}^n$上的所有单位半开闭矩体 
$$
\mathbb{R}^n = \bigcup\limits_{k_1 = -\infty}^{\infty}\bigcup\limits_{k_2 = -\infty}^{\infty}\cdots \bigcup\limits_{k_n = -\infty}^{\infty} [k_1, k_1+1) \times [k_2, k_2+1) \times \cdots \times [k_n, k_n+1) 
$$
用$\alpha_i$表示$\mathbb{R}^n$上的某个单位半开闭矩体, 根据可列个可列集的并仍然是可列集, $\mathbb{R}^n$可以被写成
$$
\mathbb{R}^n = \bigcup\limits_{i=1}^{\infty} \alpha_i, \quad \alpha_i \cap \alpha_j = \varnothing, \quad i \neq j
$$
根据[测度扩张定理](Lecture%202.%20外测度与测度扩张#2.3.%20测度扩张定理), $\mu_F$在$\sigma(\mathscr{Q}_{\mathbb{R}^n}) = \mathscr{B}_{\mathbb{R}^n}$上有唯一的扩张, 仍然记为$\mu_F$. 这就定义了在$\mathscr{B}_{\mathbb{R}^n}$上的Lebesgue-Stieltjes (Lebesgue) 测度.

### 2.3. $\mathscr{F}_{\lambda_F}$上的Lebesgue-Stieltjes测度
根据[Caratheodory定理](Lecture%202.%20外测度与测度扩张#1.5.%20Caratheodory定理), $\mu_F$的生成外测度$\lambda_F$在全体$\lambda_F$可测集组成的$\sigma$域$\mathscr{F}_{\lambda_F}$上是一个测度. 

我们将$\mathscr{F}_{\lambda_F}$中的集合叫做$\mathbb{R}^n$中的Lebesgue-Stieljes可测集, 将$\lambda_F$叫做$\mathbb{R}^n$上的Lebesgue-Stieljes测度, 将$(\mathbb{R}^n, \mathscr{F}_{\lambda_F})$上的可测函数叫做Lebesgue-Stieljes可测函数.

特别地, 如果
$$
F(\boldsymbol{b})  =b_1b_2\cdots b_n \Longrightarrow \mu_F((\boldsymbol{a}, \boldsymbol{b}]) = \prod\limits_{i=1}^{n} (b_i - a_i)
$$
我们将$\mathscr{F}_{\lambda_F}$中的集合叫做$\mathbb{R}^n$中的Lebesgue可测集, 将$\lambda_F$叫做$\mathbb{R}^n$上的Lebesgue测度, 将$(\mathbb{R}^n, \mathscr{F}_{\lambda_F})$上的可测函数叫做Lebesgue可测函数.

## 3. 不可测集
### 3.1. Steinhaus定理
设$E$是$\mathbb{R}^n$中的可测集, 且$m(E)> 0$, 做向量差点集
$$
E - E = \{ \boldsymbol{x} - \boldsymbol{y} \mid \boldsymbol{x}, \boldsymbol{y} \in E \}
$$
则存在$\delta_0>0$, 使得$E - E \supset B(0, \delta_0)$

### 3.2. 不可测集
设$\mathbb{Q}^n$为$\mathbb{R}^n$中的有理点集, 对于$\mathbb{R}^n$中的点$\boldsymbol{x}$和$\boldsymbol{y}$, 若$\boldsymbol{x} - \boldsymbol{y}\in \mathbb{Q}$, 则记为$x\sim y$. 这样, 我们在$\mathbb{R}^n$中得到了若干个等价类. 根据选择公理, 从每一类中取一点并只取一点形成点集, 记为$W$, 则$W$为不可测集. 