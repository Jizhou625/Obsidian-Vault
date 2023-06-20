## 1. 凸函数
### 1.1. 凸函数的定义
函数 $f: \mathbb{R}^n\to \mathbb{R}$ 是凸的, 如果 $\mathrm{dom} f$ 是一个凸集并且对任意的 $\boldsymbol{x}, \boldsymbol{y}\in \mathrm{dom} f$ 和任意的$0\le \theta\le 1$, 都有
$$
f(\theta\boldsymbol{x} +(1-\theta)\boldsymbol{y}) \le \theta f(\boldsymbol{x}) + (1-\theta) f(\boldsymbol{y})
$$
当不等号变成严格不等式时, 函数 $f$ 是严格凸的.

函数$f$是凸的, 当且仅当其在与其定义域相交的任何直线上都是凸的. 换言之, 函数$f$是凸的, 当且仅当对于任意的$x\in \mathrm{dom} f$和任意向量$\boldsymbol{v}$. 函数$g(t) = f(\boldsymbol{x} + t\boldsymbol{v})$是凸的. 
___
##### Proof: 
If $f$ is convex, then $\mathrm{dom}g$ is obviously convex. Moreover, for all $t, s\in \mathrm{dom} g$ and $\theta \in [0, 1]$
$$
\begin{aligned}
g(\theta t+(1-\theta) s) &=f(\boldsymbol{x}+[\theta t+(1-\theta) s] \boldsymbol{v})\\ 
& =f(\theta(\boldsymbol{x}+t \boldsymbol{v})+(1-\theta)(\boldsymbol{x}+s \boldsymbol{v})) \\
& \leq \theta f(\boldsymbol{x}+t \boldsymbol{v})+(1-\theta) f(\boldsymbol{x}+s \boldsymbol{v}) \\
& =\theta g(t)+(1-\theta) g(s) .
\end{aligned}
$$
Now assume that all $g(t)$ is convex. For all $\boldsymbol{x}, \boldsymbol{y}\in \mathrm{dom} f$ and $\theta\in [0,1]$, define $g(t) = f(\boldsymbol{x} + t(\boldsymbol{y} - \boldsymbol{x}))$. Then from $0, 1 \in \mathrm{dom} g$ we have $\theta \in \mathrm{dom}g$, which means that $\theta \boldsymbol{y} + (1-\theta)\boldsymbol{x}\in \mathrm{dom} f$. So $\mathrm{dom} f$ is convex. Moreover, from $g(\theta) = g(\theta\cdot 1 + (1-\theta)\cdot 0)\le \theta g(1) + (1-\theta)g(0)$, we have 
$$
f(\theta \boldsymbol{y} + (1-\theta)\boldsymbol{x})\le \theta f(\boldsymbol{y}) + (1-\theta) f(\boldsymbol{x})
$$
___


### 1.2. $\boldsymbol{\mu}$-strongly convex
函数$f$是$\mu$-strongly convex, 如果对于任意的$\boldsymbol{x}, \boldsymbol{y}\in \mathrm{dom} f$ 和任意的$0\le \theta\le 1$, 都有
$$
f(\theta \boldsymbol{x}+(1-\theta) \boldsymbol{y}) \leq \theta f(\boldsymbol{x})+(1-\theta) f(\boldsymbol{y})-\frac{\theta(1-\theta) \mu}{2} \|\boldsymbol{y}-\boldsymbol{x} \|^2, \quad \forall \theta \in[0,1]
$$
$f(\boldsymbol{x})$是$\mu$-strongly convex, 当且仅当$f(\boldsymbol{x}) - \dfrac{\mu}{2}\|\boldsymbol{x}\|^2$是凸的.

### 1.3. 凸函数的拓展值延伸
如果$f$是凸的, 我们定义其拓展值延伸$\tilde{f}: \mathbb{R}^n\to \mathbb{R}\cup \{\infty\}$为
$$
\tilde{f}(\boldsymbol{x}) = \begin{cases}  f(\boldsymbol{x}), \quad & \boldsymbol{x}\in \mathrm{dom}f \\ \infty, &\boldsymbol{x}\notin \mathrm{dom} f \end{cases}
$$
延伸函数$\tilde{f}$是定义在全空间$\mathbb{R}^n$上的, 取值集合为$\mathbb{R}\cup \{\infty\}$. 

### 1.4. 一阶条件
假设$f$可微(即其梯度$\nabla f$在开集$\mathrm{dom} f$内处处存在), 则函数$f$是凸函数的充分必要条件是$\mathrm{dom} f$是凸集并且对于任意的$\boldsymbol{x}, \boldsymbol{y}\in \mathrm{dom} f$, 有
$$
f(\boldsymbol{y}) \ge f(\boldsymbol{x}) + \nabla f^{\top}(\boldsymbol{x})(\boldsymbol{y} - \boldsymbol{x})
$$
一阶条件说明从一个凸函数的局部信息可以得到一些全局信息. 
___
##### Proof: 
If $f$ is convex, then 
$$
f((1-\alpha)\boldsymbol{x} +\alpha \boldsymbol{y}) \le (1-\alpha) f(\boldsymbol{x}) + \alpha f(\boldsymbol{y})
$$
which can be rewritten as 
$$
f(\boldsymbol{y}) \geq f(\boldsymbol{x})+\frac{f(\boldsymbol{x}+\alpha(\boldsymbol{y}-\boldsymbol{x}))-f(\boldsymbol{x})}{\alpha}
$$
Letting $\alpha \to 0^+$, we have 
$$
f(\boldsymbol{y}) \geq f(\boldsymbol{x})+\langle\nabla f(\boldsymbol{x}), \boldsymbol{y}-\boldsymbol{x}\rangle
$$
If the following inequality holds 
$$
f(\boldsymbol{y}) \geq f(\boldsymbol{x})+\langle\nabla f(\boldsymbol{x}), \boldsymbol{y}-\boldsymbol{x}\rangle
$$
we have 
$$
\begin{aligned}
& f(\alpha \boldsymbol{x}+(1-\alpha) \boldsymbol{y}) \leq f(\boldsymbol{x})-(1-\alpha)\langle\nabla f(\alpha \boldsymbol{x}+(1-\alpha) \boldsymbol{y}), \boldsymbol{x}-\boldsymbol{y}\rangle, \\
& f(\alpha \boldsymbol{x}+(1-\alpha) \boldsymbol{y}) \leq f(\boldsymbol{y})+\alpha\langle\nabla f(\alpha \boldsymbol{x}+(1-\alpha) \boldsymbol{y}), \boldsymbol{x}-\boldsymbol{y}\rangle .
\end{aligned}
$$
By combining the two inequalities, we have
$$
f(\alpha \boldsymbol{x}+(1-\alpha) \boldsymbol{y}) \leq \alpha f(\boldsymbol{x})+(1-\alpha) f(\boldsymbol{y})
$$
#####
___
### 1.5. 二阶条件
假设函数$f$二阶可微, 即对于开集$\mathrm{dom}f$的任意一点, 它的Hessian矩阵或者二阶导数$\nabla^2 f$存在, 则函数$f$是凸函数当且仅当$\mathrm{dom}f$是凸集, 并且其Hessian矩阵是半正定阵, 即
$$
\nabla^2 f(\boldsymbol{x}) \succeq 0
$$

### 1.6. 下水平集(Sublevels Sets)
函数$f: \mathbb{R}^n\to \mathbb{R}$的$\alpha$下水平集定义为
$$
C_{\alpha} = \{\boldsymbol{x}\in \mathrm{dom}f \mid f(\boldsymbol{x})\le \alpha\}
$$
对于任意的$\alpha$值, 凸函数的下水平集仍然是凸集. 但逆命题不成立. 例如, 函数$f(x) = - e^{x}$在$\mathbb{R}$上不是凸函数, 但是其所有下水平集都是凸集.

### 1.7. Epigraph
函数$f: \mathbb{R}^n\to \mathbb{R}$的epigraph定义为
$$
\text { epi } f=\{(\boldsymbol{x}, t) \mid \boldsymbol{x} \in \operatorname{dom} f, f(\boldsymbol{x}) \leq t\}
$$
是$\mathbb{R}^{n+1}$中的子集. 函数$f$是凸函数当且仅当其epigraph是凸集.

![image-20230620205959955](Lecture%203.%20凸函数.assets/image-20230620205959955.png)

### 1.8. 凸函数的可导性条件(Rademacher's Theorem)

设$f$是一个凸函数, 则其在$\mathrm{dom}f$的相对内部(relatively interior)上几乎处处可导.

## 2. 保凸运算
### 2.1. 非负加权求和
凸函数的非负加权求和仍然是凸函数, 即函数
$$
f = w_1f_1 + \cdots + w_mf_m
$$
是凸函数. 

如果固定任意的$\boldsymbol{y}\in \mathcal{A}$, 函数$f(\boldsymbol{x}, \boldsymbol{y})$关于$\boldsymbol{x}$是凸函数, 且对于任意的$y\in \mathcal{A}$, 有$w(\boldsymbol{y})\ge 0$. 则函数$g$
$$
g(\boldsymbol{x}) = \int_{\mathcal{A}} w(\boldsymbol{y})f(\boldsymbol{x}, \boldsymbol{y})\mathrm{d}\boldsymbol{y}
$$
关于$\boldsymbol{x}$是凸函数(若此积分存在).

### 2.2. 复合仿射映射
假设函数$f: \mathbb{R}^n\to \mathbb{R}, A\in \mathbb{R}^{n\times m}$, 以及$b\in \mathbb{R}^n$, 定义$g: \mathbb{R}^m\to \mathbb{R}$为
$$
g(\boldsymbol{x}) = f(A\boldsymbol{x}+\boldsymbol{b})
$$
其中$\mathrm{dom} g = \{\boldsymbol{x}\mid A\boldsymbol{x}+\boldsymbol{b}\in \mathrm{dom} f\}$. 如果函数$f$是凸函数, 则函数$g$也是凸函数.

### 2.3. 逐点最大和逐点上确界
如果函数$f_1, f_2, \cdots , f_m$均为凸函数, 则二者的逐点最大函数$f$
$$
f(\boldsymbol{x}) = \max\{f_1(\boldsymbol{x}), f_2(\boldsymbol{x}), \cdots, f_m(\boldsymbol{x})\}
$$
仍然是凸函数. 其定义域为$\mathrm{dom} f =\mathrm{dom}f_1\cap \mathrm{dom}f_2\cap\cdots \cap \mathrm{dom}f_m$

逐点最大的性质可以拓展到无限个凸函数的逐点上确界, 如果对于任意$\boldsymbol{y}\in \mathcal{A}$, 函数$f(\boldsymbol{x}, \boldsymbol{y})$关于$\boldsymbol{x}$都是凸的, 则函数$g$
$$
g(\boldsymbol{x}) = \sup_{\boldsymbol{y}\in \mathcal{A}} f(\boldsymbol{x}, \boldsymbol{y})
$$
关于$\boldsymbol{x}$也是凸的. 

### 2.4. 最小化
如果函数$f$关于$(\boldsymbol{x}, \boldsymbol{y})$是凸函数, 集合$C$是非空凸集, 定义函数
$$
g(\boldsymbol{x}) = \inf\limits_{\boldsymbol{y}\in C} f(\boldsymbol{x}, \boldsymbol{y})
$$
若存在某个$\boldsymbol{x}$使得$g(\boldsymbol{x})> -\infty$, 则函数$g$关于$\boldsymbol{x}$是凸函数. 

### 2.5. 透视函数
给定函数$f: \mathbb{R}^{n}\to \mathbb{R}$, 则$f$的透视函数$g: \mathbb{R}^{n+1}\to\mathbb{R}$, 定义为
$$
g(\boldsymbol{x}, t) = t f\left(\frac{\boldsymbol{x}}{t}\right)
$$
其定义域为
$$
\mathrm{dom} g  = \{(\boldsymbol{x}, t)\mid \dfrac{\boldsymbol{x}}{t}\in \mathrm{dom}f. t>0\}
$$
透视运算是保凸运算, 如果函数$f$是凸函数, 则其透视函数$g$也是凸函数. 

## 3. 共轭函数
### 3.1. 共轭函数的定义
设函数$f:\mathbb{R}^n\to \mathbb{R}$, 定义函数$f^*: \mathbb{R}^n\to \mathbb{R}$为
$$
f^*(\boldsymbol{y}) = \sup\limits_{\boldsymbol{x}\in \mathrm{dom}f} \left(\boldsymbol{y}^{\top}\boldsymbol{x} - f(\boldsymbol{x})\right)
$$
此函数称为函数$f$的共轭函数(conjugate function). 显然, 共轭函数$f^*$是凸函数, 这是因为它是一系列$\boldsymbol{y}$的凸函数的逐点上确界.

### 3.3. Fenchel不等式
从共轭函数的定义可以得到, 对任意的$\boldsymbol{x}$和$\boldsymbol{y}$, 如下的不等式成立
$$
f(\boldsymbol{x}) + f^*(\boldsymbol{y}) \ge \boldsymbol{x}^{\top}\boldsymbol{y}
$$
上述不等式即为Fenchel不等式, 当$f$可微时也被称为Young不等式.

### 3.4. 


## 4. 拟凸函数(quasi-convex function)

## 2. Subgradient
### 2.1. Definition
$$
\partial f(\boldsymbol{x})=\{\boldsymbol{g} \mid f(\boldsymbol{y}) \geq f(\boldsymbol{x})+\langle\boldsymbol{g}, \boldsymbol{y}-\boldsymbol{x}\rangle, \forall \boldsymbol{y} \in \operatorname{dom} f\}
$$
Subgradient can be identified with a non-vertical supporting hyperplane to the epigraph of $f$ at $(\boldsymbol{x}, f(\boldsymbol{x}))$.

### 2.2. Topological Property
Let $f: \mathbb{R}^n \rightarrow \mathbb{R}$ be a proper convex function. The subgradient set $\partial f(\boldsymbol{x})$ is nonempty, convex, and compact for all $\boldsymbol{x} \in(\operatorname{dom} f)^{\circ}$.
___
**Note**: $\partial f(\boldsymbol{x})$ may be empty when $\boldsymbol{x}\in \partial (\mathrm{dom} f)$. For example, 
$$
f(x) = \begin{cases}  x^2,\quad &0\le x< 2 \\ 4, \quad &x=2 \end{cases}
$$

2. **Derivative and Subgradient**: Let $f: \mathbb{R}^n \rightarrow \mathbb{R}$ be a convex function. For every $\boldsymbol{x} \in \mathbb{R}^n$, we have
    $$
    f^{\prime}(\boldsymbol{x} ; \boldsymbol{y})=\max _{\boldsymbol{g} \in \partial f(\boldsymbol{x})}\langle\boldsymbol{y}, \boldsymbol{g}\rangle, \quad \forall \boldsymbol{y} \in \mathbb{R}^n .
    $$
    In particular, $f$ is differentiable at $\boldsymbol{x}$ with gradient $\nabla f(\boldsymbol{x})$ if and only if it has $\nabla f(\boldsymbol{x})$ as its unique subgradient at $\boldsymbol{x}$.
3. **Bounded Subgradient**: Let $f: \mathbb{R}^n\to \mathbb{R}$ be a convex function. Then if $\mathcal{X}$ is a bounded set, then the set $\bigcup\limits_{\boldsymbol{x}\in\mathcal{X}}\partial f(\boldsymbol{x})$ is bounded 
4. **Convergence of Subgradient**: Let $f: \mathbb{R}^n \rightarrow \mathbb{R}$ be a convex function. If a sequence $\{\boldsymbol{x}_k\}$ converges to a vector $\boldsymbol{x}\in \mathbb{R}^n$ and $\boldsymbol{g}_k \in \partial f(\boldsymbol{x}_k)$ for all $k$, then the sequence $\{\boldsymbol{g}_k\}$ is bounded and each of its accumulation points is a subgradient of $f$ at $\boldsymbol{x}$.

### 2.3. Properties of Subgradient
1. **Decomposition of Subgradient**: Let $f_j: \mathbb{R}^n \rightarrow \mathbb{R}, j=1, \cdots, m$, be convex functions and let $f=$ $f_1+\cdots+f_m$. Then
$$
\partial f(\boldsymbol{x})=\partial f_1(\boldsymbol{x})+\cdots+\partial f_m(\boldsymbol{x})
$$
2. **Chain Rule 1**:  Let $f: \mathbb{R}^m \rightarrow \mathbb{R}$ be a convex function, and let $A$ be an $m \times n$ matrix. Then the subdifferential of the function $F$, defined by $F(\boldsymbol{x})=$ $f(A \boldsymbol{x})$, is given by
$$
\partial F(\boldsymbol{x})=A^{\top} \partial f(A\boldsymbol{x}) .
$$
3. **Chain Rule 2**: Let $f: \mathbb{R}^n \rightarrow \mathbb{R}$ be a convex function and let $h: \mathbb{R} \rightarrow \mathbb{R}$ be a differentiable scalar function. Then the function $F$, defined by $F(\boldsymbol{x})=h(f(\boldsymbol{x}))$, is directionally differentiable at all $\boldsymbol{x}$, given by
    $$
    F^{\prime}(\boldsymbol{x})=h^{\prime}(f(\boldsymbol{x})) f^{\prime}(\boldsymbol{x}), \quad \forall \boldsymbol{x}, \boldsymbol{y} \in \mathbb{R}^n .
    $$
    Furthermore, if $h$ is convex and monotonically nondecreasing, then $F$ is convex and its subdifferential is given by
    $$
    \partial F(\boldsymbol{x})=\partial h(f(\boldsymbol{x})) \partial f(\boldsymbol{x})=\{g \boldsymbol{g} \mid g \in \partial h(f(\boldsymbol{x})), \boldsymbol{g} \in \partial f(\boldsymbol{x})\}, \quad \forall \boldsymbol{x} \in \mathbb{R}^n .
    $$

### 2.4. Subdifferential of Norms
Let $\mathcal{H}$ be a real Hilbert space endowed with an inner product $\langle\cdot, \cdot\rangle$ and a norm $\|\cdot\|$. Then 
$$
\partial\|\boldsymbol{x}\|=\left\{\boldsymbol{y} \mid\langle\boldsymbol{y}, \boldsymbol{x}\rangle=\|\boldsymbol{x}\| \text { and }\|\boldsymbol{y}\|^* \leq 1\right\},
$$
where $\|\cdot\|^*$ is the dual norm of $\|\cdot\|$.
___
##### Proof: 
Let $S = \{\boldsymbol{y}\mid \langle \boldsymbol{y}, \boldsymbol{x}\rangle = \|\boldsymbol{x}\| \text{ and } \|\boldsymbol{y}\|^{*}\le 1\}$

## 3. 函数的closedness
### 3.1. 函数闭的定义
A function $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is said to be closed if, for each $\alpha \in \mathbb{R}$, the sublevel set
$$
\{\boldsymbol{x} \in \operatorname{dom} f \mid f(\boldsymbol{x}) \leq \alpha\}
$$
is closed. This is equivalent to the condition that the epigraph of $f$
$$
\text { epi } f=\left\{(\boldsymbol{x}, t) \in \mathbb{R}^{n+1} \mid \boldsymbol{x} \in \operatorname{dom} f, f(\boldsymbol{x}) \leq t\right\}
$$
is closed.

### 3.2. 函数闭的判定
1. If $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is continuous, and $\operatorname{dom} f$ is closed, then $f$ is closed.

2. If $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is continuous, with $\operatorname{dom} f$ open, then $f$ is closed iff $f$ converges to $\infty$ along every sequence converging to a boundary point of $\operatorname{dom} f$. In other words
   $$
   \lim _{n \rightarrow \infty} \boldsymbol{x}_n=\boldsymbol{x} \in \partial(\operatorname{dom} f), \quad \boldsymbol{x}_n \in \operatorname{dom} f
   $$
   Then
   $$
   \lim _{n \rightarrow \infty} f\left(\boldsymbol{x}_n\right)=\infty
   $$