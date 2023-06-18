## 1. 线性可分性
### 1.1. 线性分类器(感知机)
定义$\mathbb{R}^d$ 上的线性分类器族为$\mathcal{F} = \{\text{sgn}(\boldsymbol{w}^\top \boldsymbol{x} + b) : \boldsymbol{w} \in \mathbb{R}^d, b \in \mathbb{R}\}$, 其中, 函数表达式
$$
f(\boldsymbol{x}) = \text{sgn}(\boldsymbol{w}^\top \boldsymbol{x} + b)
$$
也被称为感知机. 

### 1.2. 线性可分性
给定数据集$D = \{\boldsymbol{x}_i, y_i\}_{i=1}^n$, 其中$\boldsymbol{x} \in \mathbb{R}^d$并且$y = {\pm 1}$, 如果存在一个方程$f \in \mathcal{F}$使得 
$$
\sum\limits_{i=1}^n \mathbb{I}[f(x_i) \neq y_i] = 0
$$
换句话说, 如果存在$\boldsymbol{w} \in \mathbb{R}^d, b \in \mathbb{R}$, 使得
$$
y_i(\boldsymbol{w}^\top \boldsymbol{x}_i + b) \geq 0, \quad \forall i \in [n]
$$
则称数据集$D$线性可分. 否则称数据集$D$线性不可分

### 1.3. 线性可分性的类梯度下降算法
![image-20230619005230486](./Lecture%202.%20%E7%BA%BF%E6%80%A7%E5%88%86%E7%B1%BB%E9%97%AE%E9%A2%98.assets/image-20230619005230486.png)






### 1.2. 感知机
为了高效地解决线性可分问题, 我们可以使用线性规划(Linear Programming, LP). 其表达式为
$$
\begin{aligned}
\max_{\boldsymbol{w},b,t} \quad & t \\
\text{s.t.} \quad & y_i(\boldsymbol{w}^\top \boldsymbol{x}_i + b) \geq t, \quad \forall i \in [n]
\end{aligned}
$$
如果 $t > 0$, 则称数据集线性可分. 

### 1.2. 最大间隔分类器
当训练集线性可分的时候, 可能会有很多可行的线性分类器, 因此我们希望找到使得间隔最大化的分类器. 
$$
\begin{aligned}
\max_{\boldsymbol{w},b,t} \quad & t \\
\text{s.t.} \quad & y_i(\boldsymbol{w}^\top \boldsymbol{x}_i + b) \geq t, \quad \forall i \in [n] \\
& \|\boldsymbol{w}\|_2 = 1
\end{aligned} \tag{1}
$$
然而, 这既不是一个LP问题, 也不是一个QP问题, 因此我们并不能被找到有效的求解算法. 幸运的是, 下面的QP问题和优化问题(1)等价. 
$$
\begin{aligned}
\min_{\boldsymbol{w},b} \quad & \frac{1}{2} \|\boldsymbol{w}\|^2_2 \\
\text{s.t.} \quad & y_i(\boldsymbol{w}^\top \boldsymbol{x}_i + b)  \geq 1, \quad \forall i \in [n]
\end{aligned} \tag{2}
$$
___
##### Proof

设$(\boldsymbol{w}^*, b^*)$是优化问题(1)的最优解, $t^{*}$是优化问题(1)的最优目标函数值, $(\boldsymbol{w}^{\prime}, b^{\prime})$是优化问题(2)的最优解, $\dfrac{1}{2t^{\prime 2}}$是优化问题(2)的最优目标函数值. 

考虑$\left(\dfrac{\boldsymbol{w}^*}{t^*}, \dfrac{b^*}{t^*}\right)$, 其满足优化问题(2)的约束条件, 因此
$$
\dfrac{1}{2t^{\prime 2}} \le \dfrac{1}{2t^{* 2}}\Longrightarrow t^* \le t^{\prime}
$$
考虑$\left(\dfrac{\boldsymbol{w}^{\prime}}{\|\boldsymbol{w}^{\prime}\|}, \dfrac{b^{\prime}}{\|\boldsymbol{w}^{\prime}\|}\right)$和$t = t^{\prime}$. 其满足优化问题(1)的约束条件, 因此
$$
t^{\prime} \le t^{*}
$$
综上所述, 我们有$t^{\prime} = t^*$. 因此优化问题(1)的解和优化问题(2)的解可以互相转化, 这意味着它们是等价的.  

#####

___

### 1.2. Lagrangian Duality

Consider an optimization problem:
$$
\begin{aligned}
    x=&\arg\min_{x}f(x)\\
    \text{s.t. } &g_i(x)\leqslant 0,\quad i\in[n]\\
    &h_j(x)=0,\quad j\in[m]
\end{aligned}
$$
We ask $f, g_1,\ldots,g_n$ to be convex and $h_1,\ldots, h_m$ to be linear. It’s easy to see that the problem is equivalent to the following optimization problem
$$
x=\arg\min_x\max_{\{\lambda_i\}_{i=1}^n,\{\mu_j\}_{j=1}^m}\left\{f(x)+\sum_{i=1}^n\lambda_ig_i(x)+\sum_{j=1}^m \mu_jh_j(x)\right\}\\\text{s.t. }\lambda_i\geqslant 0, \quad i\in[n]
$$
The function
$$
\mathcal{L}(x;\lambda_i,\mu_j)\equiv f(x)+\sum_{i=1}^n\lambda_ig_i(x)+\sum_{j=1}^m \mu_jh_j(x)
$$
is called the Lagrangian function. $\mathcal{L}(x, \lambda_i, \mu_i)$ is convex with respect to $x$ and linear with respect to $\lambda_i$ and $\mu_j$. Therefore, the minimax theorem holds for $\mathcal{L}(x, \lambda_i, \mu_j)$. Thus the optimal value of the primal problem is equal to
$$
\begin{gathered}
\max _{\left\{\lambda_i\right\}_{i=1}^n,\left\{\mu_j\right\}_{j=1}^m} \min_x\mathcal{L}\left(x ; \lambda_i, \mu_j\right) \\
\text { s.t. } \lambda_i \geqslant 0, \quad i \in[n]
\end{gathered}
$$
Notice that $\min\limits_{x}\mathcal{L}(x, \lambda_i, \mu_j)$ is a convex optimization problem, it has a unique global minimum point
$$
x^*=\phi\left(\lambda_i, \mu_j\right) \quad \Leftrightarrow \quad \nabla_x \mathcal{L}\left(x^* ; \lambda_i, \mu_j\right)=0
$$
Therefore, the optimal value of the primal problem is equal to
$$
\begin{aligned}
& \max_{\left\{\lambda_i\right\}_{i=1}^n,\left\{\mu_j\right\}_{j=1}^m}\mathcal{L}\left(\phi\left(\lambda_i, \mu_j\right) ; \lambda_i, \mu_j\right) \\
& \text { s.t. } \lambda_i \geqslant 0, \quad i \in[n]
\end{aligned}
$$
This is called the Lagrangian duality of the primal optimization problem.

### 2.3. KKT conditions

If the primal optimization problem has a solution $x^*$ and its dual problem has a solution $\left(\lambda_i^*, \mu_j^*\right)$, then there hold the following KKT conditions:

1. **Stationary**: $\nabla_{x, \lambda, \mu} \mathcal{L}\left(x^* ; \lambda_i^*, \mu_j^*\right)=0$
2. **Primal Feasible**: $g_i\left(x^*\right) \leqslant 0, h_j\left(x^*\right)=0, \forall i \in[n], \forall j \in[m]$
3. **Dual Feasible**: $\lambda_i^* \geqslant 0, \forall i \in[n]$
4. **Complementary Slackness**: $\lambda_i^*g_i\left(x^*\right)=0, \forall i \in[n]$

KKT conditions are necessary conditions for $x^*$ and $(\lambda_i^*, \mu_j^*)$ to be solutions of the primal & dual problems. Given $f, g_1, \cdots, g_n$ convex and $h_1, \cdots, h_m$ linear, the KKT conditions are also sufficient conditions.
___
##### Example
When applying the KKT conditions to the problem.
$$
\begin{aligned}
& \qquad(\boldsymbol{w}, b)=\arg \min _{\boldsymbol{w}, b} \frac{1}{2}\|\boldsymbol{w}\|_2^2 \\
& \text { s.t. } y_i\left(\boldsymbol{w}^{\top} \boldsymbol{x}_i+b\right) \geqslant 1, \quad i=1,2, \ldots, n
\end{aligned}
$$
It's easy to writhe the dual problem as
$$
\begin{gathered}
\min_{\left\{\lambda_i\right\}_{i=1}^n}\left\{\frac{1}{2} \sum_{i=1}^n \sum_{j=1}^n \lambda_i \lambda_j y_i y_j \boldsymbol{x}_i^{\top} \boldsymbol{x}_j-\sum_{i=1}^n \lambda_i\right\} \\
\text { s.t. } \lambda_i \geqslant 0, \quad i \in[n] \\
\text { and } \sum_{i=1}^n \lambda_i y_i=0
\end{gathered}
$$
#####
___

## 1. Minimax Theorem

### 1.1 Two-player Matrix Game

There are two players, Alice (row player) and Bob (column player). $M=((m_{ij},m'_{ij}))_{m\times n}$ is a matrix where every element is a pair of numbers $(m_{ij},m'_{ij})\in \mathbb{R}^2$. Alice choose a row $i$ while Bob choose a column $j$. Then the number $m_{ij}$ and $m'_{ij}$ is the feedback of Alice and Bob respectively. $M$ is known to Alice and Bob before making choices.

When we have $m_{ij} + m^{\prime}_{ij}= 0$, then we call the two-player matrix game a zero-sum game.

### 1.2. Pure Strategy

If only one specific strategy can be selected, we call the strategy a pure strategy. If row player moves first

1. Alice choose a determined row i
2. Bob observed Alice’s strategy. According to the information about M and Alice’s strategy, Bob choose a determined column j
3. Alice pays $m_{ij}$ to Bob

If Alice go first, she always assume that if she choose row $i$, Bob will choose column $j\ \text{s.t.}\ m_{ij}=\max\limits_{l} m_{il}$. So Alice should minimize $\max\limits_{l} m_{il}$, that is to say Alice will pay $\min\limits_{i}\max\limits_{j} m_{ij}$ to Bob at least. In the same way, if Bob move first, Alice will pay $\max\limits_{j}\min\limits_{i} m_{ij}$ to Bob at least.

We have the following inequality:
$$
\min\limits_{i}\max\limits_{j} m_{ij} \ge  \max\limits_{j}\min\limits_{i} m_{ij}
$$
___
##### Proof: 
Let $m_{i_0 j_0}=\min\limits_{i}\max\limits_{j} m_{ij}$ and $m_{i_1 j_1}=\max\limits_{j}\min\limits_{i} m_{ij}$. Then $m_{i_0 j_0}\geq m_{i_0 j_1}\geq m_{i_1 j_1}$.
#####
___

### 1.3. Mix Strategy and von Neumann's Minimax Theorem

If row player moves first

1. Alice chooses a probability distribution $P=(p_1,p_2,...,p_m)^T, \text{s.t.}\sum\limits_{i\in [m]}p_i=1, p_i\geq 0\ \forall i\in [m]$ over all rows.
2. Bob, after observing Alice's probability distribution $P$, chooses his probability distribution $Q$ over all columns.
3. Alice pays the expectation $P^TMQ$ to Bob.

We have the following equality holds
$$
\min_P\max_Q P^TMQ=\max_Q\min_P P^TMQ
$$
This theorem is the special case of  [[#1.4. Sion's Minimax Theorem]]

### 1.4. Sion's Minimax Theorem

Let $f(x, y)$ be convex with respect to $x \in \mathcal{X}$ and concave with respect to $y\in \mathcal{Y}$. Then
$$
\min_x\max_y f(x,y)=\max_y\min_x f(x,y)
$$
In this generalized setting, the equilibrium $(x^*, y^*)$ is called the saddle point of function $f(x, y)$, which satisfy
$$
f(x^*, y)\le f(x^*, y^*)\le f(x, y^*), \quad \forall x\in \mathcal{X}, y\in \mathcal{Y}
$$

