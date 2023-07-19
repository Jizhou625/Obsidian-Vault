## 1. 偏好关系
### 1.1. 结果集上的偏好关系
参与人$i$在结果集合$O$上的偏好关系是一个二元关系, 表示为$\succsim_i$. 有了偏好关系$\succsim_i$, 就可以定义对应的严格偏好关系$\succ_i$, 它描述的是参与人$i$严格偏好某个结果. 
$$
x \succ_i y \Longleftrightarrow x \succsim_i y \text { and } y \succsim_i x \text {. }
$$
类似地, 可以定义无差异关系$\approx_i$, 它描述的是参与人认为两个可能的结果无差异的情形. 
$$
x \approx_i y \Longleftrightarrow x \succsim_i y \text { and } y \succsim_i x \text {. }
$$


### 1.2. 效用函数
假设$\widehat{\mathcal{L}}$是一个复合抽签的集合, $\succsim$是$\widehat{\mathcal{L}}$上的一个满足完备性, 自反性和传递性的偏好关系. 如果对所有的$x, y\in \widehat{\mathcal{L}}$, 下面的关系成立, 那么函数$u: \widehat{\mathcal{L}}\to \mathbb{R}$就被称为表示$\succsim$的效用函数
$$
x\succsim y \iff u(x)\geq u(y)
$$
1. 完备性: 偏好关系$\succsim_i$在$\widehat{\mathcal{L}}$上是完备的, 也就是说, 对$\widehat{\mathcal{L}}$中的任何一对结果$x$和$y$, 都有$x\succsim_i y$和$y\succsim_i x$中至少一个成立. 
2. 自反性: 偏好关系$\succsim_i$在$\widehat{\mathcal{L}}$上是自反的, 也就是说, 对任意的$x\in \widehat{\mathcal{L}}$, 都有$x\succsim_i x$成立
3. 传递性: 偏好关系$\succsim_i$在$\widehat{\mathcal{L}}$上是传递的, 也就是说, 对任意的$x,y,z\in \widehat{\mathcal{L}}$, 如果$x\succsim_i y$且$y\succsim_i z$, 则$x\succsim_i z$成立.

### 1.3. 线性效用函数
对于每一个抽签 $L=\left[p_1\left(A_1\right), p_2\left(A_2\right), \cdots, p_K\left(A_K\right)\right]$, 效用函数 $u_i$ 如果满足如下条件, 那么 $u_i$ 就被称为线性的(关于概率线性)
$$
u_i(L)=p_1 u_i\left(A_1\right)+p_2 u_i\left(A_2\right)+\cdots+p_K u_i\left(A_K\right)
$$

### 1.4. 冯诺依曼-摩根斯坦恩公理
1. **介值性**: 对于任意的三个结果$A\succsim_i B\succsim_i C$, 存在实数$\theta_i\in [0,1]$, 使得
   $$
   B \approx_i\left[\theta_i(A),\left(1-\theta_i\right)(C)\right]
   $$
2. **单调性**: 令 $\alpha, \beta \in[0,1]$, $A\succ_i B$. 当且仅当 $\alpha \geqslant \beta$, 下式成立:
   $$
   [\alpha(A),(1-\alpha)(B)] \succsim_i[\beta(A),(1-\beta)(B)]
   $$
3. **一致性**: 对每一个 $j=1, \cdots, J$, 令 $L_j$ 表示下面的简单抽签:
   $$
   L_j=\left[p_1^j\left(A_1\right), p_2^j\left(A_2\right), \cdots, p_K^j\left(A_K\right)\right]
   $$
   令 $\widehat{L}$ 表示下面的复合抽签:
   $$
   \widehat{L}=\left[q_1\left(L_1\right), q_2\left(L_2\right), \cdots, q_J\left(L_J\right)\right]
   $$
   对每一个 $k=1,2, \cdots, K$, 定义
   $$
   r_k=q_1 p_k^1+q_2 p_k^2+\cdots+q_J p_k^J
   $$
   $r_k$是复合抽签 $\widehat{L}$ 的结果 $A_k$ 出现的综合概率. 考虑如下的简单抽签
   $$
   L=\left[r_1\left(A_1\right), r_2\left(A_2\right), \cdots, r_K\left(A_K\right)\right]
   $$
   那么
   $$
   \widehat{L} \approx_i L
   $$
4. **独立性**: 假设 $\widehat{L}=\left[q_1\left(L_1\right), \cdots, q_J\left(L_J\right)\right]$ 是一个复合抽签, $M$ 是一个简单抽签。如果 $L_j \approx_i M$, 那么
$$
\widehat{L} \approx_i\left[q_1\left(L_1\right), \cdots, q_{j-1}\left(L_{j-1}\right), q_j(M), q_{j+1}\left(L_{j+1}\right), \cdots, q_J\left(L_J\right)\right]
$$

如果参与人 $i$ 在 $\widehat{\mathcal{L}}$ 上的偏好关系 $\succsim_i$ 满足完备性、自反性和传递性, 并且满足四个冯诺依曼-摩根斯坦公理, 那么这个偏好关系就可以用线性效用函数来表示
___
##### Proof
根据偏好关系 $\succsim_i$ 的完备性, 我们可以不妨设
$$
A_k \succsim_i A_{k-1} \succsim_i \cdots \succsim_i A_1
$$

首先处理$A_k\approx_i A_1$的退化情形, 即参与人认为所有的结果都是无差异的. 考虑简单抽签$L = [p_1(A_1), \cdots , p_K(A_K)]$, 重复使用独立性公理, 可以得到
$$
L \approx_i \left[p_1\left(A_1\right), p_2\left(A_1\right), \cdots, p_K\left(A_1\right)\right]
$$
根据简化公理, 可以得到$L\approx_i[1(A_1)]$, 不难证明对每一个复合抽签$\widehat{L}$都满足$\widehat{L}\approx_i[1(A_1)]$, 这意味着参与人认为任意两个复合抽签都是无差异的, 因此任何一个常数函数$u_i$都表示他的偏好. 

接下来处理$A_K\succ_i A_1$的非退化情形. 首先, 定义抽签集上的函数$u_i$. 根据介值性和单调性, 存在唯一的实数$0\le \theta_i^k\le 1$满足
$$
A_k\approx_i [\theta_i^k(A_K), (1-\theta_i^k)(A_1)]
$$
定义复合抽签集$\widehat{\mathcal{L}}$上的函数$u_i$如下
$$
u_i(\widehat{L})=r_1 \theta_i^1+r_2 \theta_i^2+\cdots+r_K \theta_i^K
$$
不难证明, 对于简单抽签$L = [p_1(A_1), \cdots, p_K(A_k)]$, 有
$$
u_i(L) = \sum\limits_{k=1}^{K}p_k\theta_i^k
$$
并且对于所有的$1\le k\le K$, $u_i(A_k)=\theta_i^k$. 对每一个复合抽签$\widehat{L}$, 根据简化公理
$$
\widehat{L} \approx_i\left[r_1\left(A_1\right), r_2\left(A_2\right), \cdots, r_K\left(A_K\right)\right]
$$
对每一个 $1 \leqslant k \leqslant K$, 令 $M_k=\left[\theta_i^k\left(A_K\right),\left(1-\theta_i^k\right)\left(A_1\right)\right]$. 根据定义, 对每一个 $1 \leqslant k \leqslant K, A_k \approx_i M_k$. 因此,独立性公理应用 $K$ 次就可得到
$$
\widehat{L} \approx_i\left[r_1\left(M_1\right), r_2\left(M_2\right), \cdots, r_K\left(M_K\right)\right]
$$
再根据简化公理就得到了
$$
\widehat{L}\approx_i [u_i(\widehat{L})(A_K), (1-u_i(\widehat{L}))(A_1)]
$$
根据单调性公理, 对任何一对复合抽签 $\widehat{L}$ 和 $\widehat{L}^{\prime}$, 都有
$$
\widehat{L} \succsim_i \widehat{L}^{\prime} \iff u_i(\widehat{L}) \geqslant u_i\left(\widehat{L}^{\prime}\right)\quad  \forall \widehat{L}, \widehat{L}^{\prime} \in \widehat{\mathcal{L}}
$$
这就完成了定理的证明. 
#####
___

### 1.5. 效用函数和放射变换
假设 $u: X \rightarrow \mathbb{R}$ 是一个函数. 如果存在一个正实数 $\alpha>0$ 和一个实数 $\beta$ 使得下式成立,那么函数 $v: X \rightarrow \mathbb{R}$ 叫做 $u$ 的正仿射变换
$$
v(x)=\alpha u(x)+\beta, \quad \forall x \in X
$$
如果 $u_i$ 是表示参与人 $i$ 的偏好关系 $\succsim_i$ 的线性效用函数, 那么 $u_i$ 的任意正仿射变换$v_i$也是表示 $\succsim_i$ 的线性效用函数.  

反之, 若$u_i$和$v_i$是参与人$i$的两个线性效用函数. 而且这个偏好关系满足冯诺依曼-摩根斯坦公理, 那么存在一个正实数$\alpha$和一个实数$\beta$使得$v_i$是$u_i$的正仿射变换.
___
##### Proof
令$v_i = \alpha u_i + \beta$是$u_i$的正仿射变换. 由于$u_i$是表示参与人$i$的偏好关系$\succsim_i$的线性效用函数, 因此
$$
\widehat{L}_1 \gtrsim_i \widehat{L}_2 \iff u_i\left(\widehat{L}_1\right) \geqslant u_i\left(\widehat{L}_2\right) \iff v_i\left(\widehat{L}_1\right) \ge v_i\left(\widehat{L}_2\right)
$$
接下来我们需要证明$v_i$是线性的. 假设$L = [p_1(A_1), p_2(A_2), \cdots, p_K(A_K)]$是一个简单抽签. 
$$
v_i(L) = \alpha u(L) +\beta = p_1v_i(A_1) + p_2 v_i(A_2) + \cdots + p_K v_i(A_K)
$$
这就证明了$v_i$是线性的.

若$u_i$和$v_i$是参与人$i$的两个线性效用函数. 而且这个偏好关系满足冯诺依曼-摩根斯坦公理, 不妨设
$$
A_k \succsim_i A_{k-1} \succsim_i \cdots \succsim_i A_1
$$
考虑$u_i(A_1) \le u_i(A_K)$和$v_i(A_1) \le v_i(A_K)$, 存在$\alpha >0$和$\beta \in \mathbb{R}$使得$v_i(A_j) = \alpha u_i(A_j) + \beta$这里$j=1, K$. 根据介值性, 对任意的$1 \le j \le K$, 都有
$$
v_i(A_j) = \alpha u_i(A_j) + \beta
$$
再根据线性性, 我们可以得到对于任意的$L$, 有
$$
v_i(L) = \alpha u_i(L) + \beta
$$
#####
___

## 2. 对冯诺依曼-摩根斯坦公理的讨论
### 2.1. 对完备性假定的背离
完备性假定看起来非常合理, 但不能想当然地认为它一定得到满足. 在一些情况下, 人们在两个不同的结果之间, 很难清楚表达他们的偏好. 设想一个孩子他的父母离婚了, 这个时候让他选择更愿意和爸爸呆一天还是和妈妈呆一天, 很多孩子会认为这很难选择. 

### 2.2. 对传递性假定的背离
孔多塞悖论指出, 如果一个参与人是一个群体, 即使每个人的偏好都是传递的, 集体的偏好关系仍然有可能不满足传递性. 下面是一个简单的例子
$$
\begin{aligned}
A\succ_D B \succ_D C \\
B\succ_D C \succ_D A \\
C\succ_D A \succ_D B
\end{aligned}
$$

### 2.3. 对一致性假定的背离
一致性假定忽略了参与人仅仅从参与抽签中所得到的快乐 (或者不快乐). 因此, 面对每个结果出现的概率完全相同的简单抽签和复合抽签, 一个人更偏好其中的某一个是完全有可能的.

### 2.4. 对概率的认知问题
如果一个人对三个可能结果 $(A, B, C)$ 的偏好关系如下: $A\succ B\succ C$, 那么我们可以通过试错的方法, 给他提供各个不同的概率值 $p$, 直到最终找到一个值 $p_0$, 满足
$$
B \approx\left[p_0(A),\left(1-p_0\right)(C)\right]
$$
举个例子, 假设参与人汇报说下面的事情是无差异的:
$$
\$ 7000 \approx\left[\frac{2}{3}(\$ 20000), \frac{1}{3}(\$ 0)\right]
$$
然而, 经验表明, 如果问同一个人多大的 $x$ 才使得他认为下面的事情是无差异的:
$$
\$ 7000 \approx\left[\frac{2}{3}(\$ x), \frac{1}{3}(\$ 0)\right]
$$
此时答案经常不是 $20000$.

## 3. 风险态度
### 3.1. 风险态度的定义
如果对于每一个具有有限可能结果的抽签$L=\left[p_1\left(x_1\right), p_2\left(x_2\right), \cdots, p_K\left(x_K\right)\right]$, 下式成立, 那么参与人$i$就被称为是风险中性的
$$
u_i(L) = u_i\left([1(\mu_L)]\right),\quad \mu_L = \sum\limits_{k=1}^{K}p_kx_k
$$
如果对每一个具有有限可能结果的抽签$L=\left[p_1\left(x_1\right), p_2\left(x_2\right), \cdots, p_K\left(x_K\right)\right]$, 下式成立, 那么参与人$i$就被称为是风险厌恶的. 
$$
u_i(L) \leqslant u_i\left(\left[1\left(\mu_L\right)\right]\right),\quad \mu_L = \sum\limits_{k=1}^{K}p_kx_k
$$
如果对每一个具有有限可能结果的抽签 $L=\left[p_1\left(x_1\right), p_2\left(x_2\right), \cdots, p_K\left(x_K\right)\right]$, 下式成立, 那么参与人 $i$ 就被称为是风险偏好的:
$$
u_i(L) \geqslant u_i\left(\left[1\left(\mu_L\right)\right]\right),\quad \mu_L = \sum\limits_{k=1}^{K}p_kx_k
$$

### 3.2. 风险态度的等价条件
参与人$i$是风险中性的, 当且仅当对每一个$p\in [0,1]$和每一对结果$x, y\in \mathbb{R}$, 下式成立
$$
u_i([p(x),(1-p)(y)])=u_i([1(p x+(1-p) y)])
$$
参与人 $i$ 是风险厌恶的,当且仅当对每一个 $p \in[0,1]$ 和每一对结果 $x, y \in \mathbb{R}$, 下式成立:
$$
u_i([p(x),(1-p)(y)]) \leqslant u_i([1(p x+(1-p) y)])
$$
参与人 $i$ 是风险追求的, 当且仅当对每一个 $p \in[0,1]$ 和每一对结果 $x, y \in \mathbb{R}$, 下式成立:
$$
u_i([p(x),(1-p)(y)]) \geqslant u_i([1(p x+(1-p) y)])
$$

如果参与人的偏好关系满足冯诺依曼-摩根斯坦公理. 则参与人是风险中性的当且仅当$u_i(\cdot)$是线性函数; 是风险厌恶的当且仅当$u_i(\cdot)$是concave函数; 是风险偏好的当且仅当$u_i(\cdot)$是convex函数.

### 3.3. 阿罗-帕拉特绝对风险厌恶
假设 $U_i$ 是定义在 $\mathbb{R}$ 上的单调递增、 严格凹且连续二阶可导的函数,假设 $U_i$ 是参与人 $i$ 对钱的效用函数。参与人 $i$ 的Arrow–Pratt measure of absolute risk aversion为:
$$
r_{U_i}(x):=-\frac{U_i^{\prime \prime}(x)}{U_i^{\prime}(x)}
$$
将这个度量乘以常数 $\dfrac{1}{2}$, 就是为了避免参加一个公平的抽签 (这个抽签基于一个期望值为零且无限接近于零的金钱数量 $\$ h$ ), 拥有初始金钱 $\$ x$ 的风险厌恶的参与人愿意放弃的金钱数量 (用抽签的方差单位来衡量).
___
##### Proof
假设参与者拥有初始金钱 $\$ x$, 他需要参加一个公平的抽签, 以相同的概率得到或者失去$\$ h$. 设他最终的钱数是$Y$, 则
$$
\mathbb{E} Y = x, \quad \operatorname{Var}(Y)=h^{2}
$$
抽签给他带来的效用损失(以方差计量)是
$$
\lim\limits_{h\to 0} \dfrac{\Delta u_h}{h^2} = \dfrac{\dfrac{1}{2}\left[u(x) - u(x+h)\right]+ \dfrac{1}{2}\left[u(x) - u(x-h)\right]}{h^2} = -\dfrac{u_i^{\prime\prime}(x)}{2}
$$
又因为
$$
\lim\limits_{h\to 0} \dfrac{\Delta u_h}{\Delta x_h} = u^{\prime}_i(x)
$$
我们得到了
$$
\lim _{h \rightarrow 0} \frac{\Delta x_h}{\operatorname{Var}(Y)}=-\frac{U_i^{\prime \prime}(x)}{2 U_i^{\prime}(x)}=\frac{1}{2} r_{U_i}(x)
$$
#####
___



## 4. 对风险厌恶的进一步讨论
### 4.1. 风险厌恶与方差厌恶
假设 $U: \mathbb{R} \rightarrow \mathbb{R}$ 是一个concave函数, $X\sim\mathcal{N}(\mu, \sigma)$, $Y\sim \mathcal{N}(\mu, \lambda \sigma)$, $\lambda>1$. 则有
$$
\mathbb{E}[U(X)] \geqslant \mathbb{E}[U(Y)]
$$
___
#####
设$\beta(\mu+c\sqrt{\lambda}) + (1-\beta)(\mu-c\sqrt{\lambda}) = \mu+c$, 则我们有$(1-\beta)(\mu+c\sqrt{\lambda}) + \beta(\mu-c\sqrt{\lambda}) = \mu-c$. 从而有
$$
\begin{aligned} 
U(\mu+c\sqrt{\lambda}) + U(\mu - c\sqrt{\lambda}) &= \left[\beta(\mu+c\sqrt{\lambda}) + (1-\beta)(\mu-c\sqrt{\lambda}) \right] \\ 
& + \left[(1-\beta)(\mu+c\sqrt{\lambda}) + \beta(\mu-c\sqrt{\lambda})\right] \\ 
& \le U(\mu+c) + U(\mu-c) 
\end{aligned} \tag{1}
$$
不妨设$\mu=0, \sigma=1$, 否则可以做变换$X^{\prime} = \dfrac{X - \mu}{\sigma}$, $Y^{\prime} = \dfrac{Y -\mu}{\sigma}$,  $U^{\prime}(x) = U(\sigma(x+\mu))$. 不改变不等式的方向. 重写(1)得到
$$
U(c\sqrt{\lambda}) + U(-c\sqrt{\lambda}) \le U(c) + U(-c)
$$
令$Y = \sqrt{\lambda}Z$, 这里$Z\sim\mathcal{N}(0,1)$
$$
\begin{aligned} 
\mathbb{E}U(Y) &=\mathbb{E}U(\sqrt{\lambda}Z) =  \int_{-\infty}^{\infty}   \phi(z)u(\sqrt{\lambda}z)\mathrm{d}z \\
&= \int_{0}^{\infty}\phi(z)\left[u(\sqrt{\lambda}z) + u(-\sqrt{\lambda}z)\right]\mathrm{d}z \\
&\le \int_{0}^{\infty}\phi(z)\left[u(z) + u(-z)\right]\mathrm{d}z\\ 
&= \mathbb{E}U(X)
\end{aligned}
$$
#####
___

### 4.2. 风险厌恶未必意味着方差厌恶
假设参与人的效用函数是$U(x) = 1-e^{-x}$, 对每个$a\in (0,1)$以及$p\in (0,1)$, 假设$X_{a, p}$是一个随机变量, 其分布为
$$
\mathbb{P}(X_{a, p} = 1-a) = \dfrac{1-p}{2}, \quad \mathbb{P}(X_{a, p} = 1) = p, \quad \mathbb{P}(X_{a, p} = 1+a) = \dfrac{1-p}{2}
$$
则存在$a_1, a_2, p_1, p_2\in(0,1)$, 使得
$$
\mathbb{E}X_{a_1, p_1} = \mathbb{E}X_{a_2, p_2}, \quad \mathrm{Var}(X_{a_1, p_1}) = \mathrm{Var}(X_{a_2, p_2})
$$
并且(2)和(3)分别成立
$$
\begin{align} 
\mathbb{E}U(X_{a_1, p_1}) &< \mathbb{E}U(X_{a_2, p_2})  \tag{2}\\ 
\mathbb{E}U(X_{a_1, p_1}) &= \mathbb{E}U(X_{a_2, p_2})   \tag{3}
\end{align}
$$
___
##### Proof
首先计算$X_{a,p}$的期望和方差
$$
\mathbb{E} X_{a, p} =1, \quad \mathrm{Var}(X_{a, p}) =(1-p) a^2 
$$
接下来计算抽签$X_{a, p}$的效用的期望为
$$
\begin{aligned} 
\mathbb{E} U(X_{a, p}) &= \dfrac{1-p}{2}(1-e^{a-1} + 1-e^{-a-1}) + p(1-e^{-1}) \\ 
& = 1 - \dfrac{1}{2e}\left[(1-p)(e^a + e^{-a} - 2)+2\right]
\end{aligned}
$$
令$c^2 = (1-p)a^2$, 则有
$$
h(a) = \mathbb{E} U(X_{a, p}) = 1 - \dfrac{1}{2e}\left[(e^a + e^{-a} - 2)\dfrac{c^2}{a^2}+2\right]
$$
方差相等条件转化为
$$
a_1^2(1-p_1) = c_1 = c_2 = a_2^2(1-p_2) 
$$
令$f(a) = \dfrac{e^{a}+e^{-a} - 2}{a^2}$, 求导可以得到
$$
f^{\prime}(a) = \dfrac{(a+2)e^a - (a-2)e^{-a} -4}{a^3}
$$
令$g(a) = (a+2)e^a - (a-2)e^{-a} -4$, $g^{\prime}(a) = a(e^a + e^{-a}) + 3(e^a - e^{-a})\ge 0$. 因此$g(a)$单调递增, $g(0) = -4$, $g(1) = 3e - e^{-1}-4 >0$. 因此$f(a)$在$(0,1)$上先减再增. 即$h(a)$在$(0,1)$上先增再减. 这就证明了结论成立. 
#####
___

