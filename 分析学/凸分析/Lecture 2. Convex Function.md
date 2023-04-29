## 1. Convex Function
### 1.1. Definition
A function $f: \mathbb{R}^n\to \mathbb{R}$ is convex if $\mathrm{dom} f$ is a convex set and if for all $\boldsymbol{x}, \boldsymbol{y}\in \mathrm{dom} f$, and $\theta$ with $0\le \theta\le 1$, we have
$$
f(\theta\boldsymbol{x} +(1-\theta)\boldsymbol{y}) \le \theta f(\boldsymbol{x}) + (1-\theta) f(\boldsymbol{y})
$$

**Strictly Convex**: A function $f$ is strictly convex if strict inequality holds whenever $\boldsymbol{x}\neq \boldsymbol{y}$ and $0< \theta< 1$

**$\boldsymbol{\mu}$-strongly convex**: A function $f$ is $\boldsymbol{\mu}$-strongly convex if 
$$
f(\theta \boldsymbol{x}+(1-\theta) \boldsymbol{y}) \leq \theta f(\boldsymbol{x})+(1-\theta) f(\boldsymbol{y})-\frac{\theta(1-\theta) \mu}{2} \|\boldsymbol{y}-\boldsymbol{x} \|^2, \quad \forall \theta \in[0,1]
$$
$f(\boldsymbol{x})$ is $\mu$-strongly convex if and only if $f(\boldsymbol{x}) - \dfrac{\mu}{2}\|\boldsymbol{x}\|^2$ is convex. 

### 1.2. Rademacher's Theorem
A convex function is differentiable almost everywhere on the relative interior of its domain. 

### 1.3. Extended value extensions and proper function
**Extended value extensions**: If $f$ is convex, we define its extended-value extension $\tilde{f}: \mathbb{R}^n\to \mathbb{R}\cup \{\infty\}$ by
$$
\tilde{f}(\boldsymbol{x}) = \begin{cases}  f(\boldsymbol{x}), \quad & \boldsymbol{x}\in \mathrm{dom}f \\ \infty, &\boldsymbol{x}\notin \mathrm{dom} f \end{cases}
$$
**Proper function**: $f$ is called proper if $f(\boldsymbol{x})<\infty$ for at least one $\boldsymbol{x} \in \mathcal{X}$ and $f(\boldsymbol{x})>-\infty$ for all $\boldsymbol{x} \in \mathcal{X}$. In words, a function is proper if and only if its epigraph is nonempty and does not contain a vertical line.

### 1.4 First order conditions and Second order conditions
**First order condition**: Suppose $f$ is differentiable. Then $f$ is convex if and only if $\operatorname{dom} f$ is convex and
$$
f(\boldsymbol{y}) \geq f(\boldsymbol{x})+\langle\nabla f(\boldsymbol{x}), \boldsymbol{y}-\boldsymbol{x}\rangle
$$
holds for all $\boldsymbol{x}, \boldsymbol{y} \in \operatorname{dom} f$.

**Second order conditions**: Assume that $f$ is twice differentiable. Then $f$ is convex if and only if $\operatorname{dom} f$ is convex and its Hessian is positive semidefinite. For all $\boldsymbol{x} \in \mathrm{dom} f$, then 
$$
\nabla ^2 f(\boldsymbol{x})\succeq \boldsymbol{0}
$$
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

### 1.5. Reduce to one Dimension
$f(\boldsymbol{x}): \mathbb{R}^n \rightarrow \mathbb{R}$ is convex if and only if for all $\boldsymbol{x} \in$ $\mathrm{dom}f$ and $\boldsymbol{v} \in \mathbb{R}^n, g(t) = f(\boldsymbol{x}+t \boldsymbol{v})$ is convex on $\mathrm{dom} g=\{t \mid \boldsymbol{x} + t \boldsymbol{v} \in \operatorname{dom} f\}$.
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
**Example**: 
We can use this results to prove that $f(X) = \log \det X$ is concave on $\mathrm{dom} f = \mathbb{S}^n_{++}$. Calculate the Hessian is hard, but we can easily get that for all $X\succ 0$ and $V \in \mathbb{S}^n$, define $g(t) = -\log |X+tV|$, where $\mathrm{dom} g = \{t\mid X+ tV\succ 0\}$, and let $\lambda_i$ be the eigenvalues of $X^{-1/2}VX^{-1/2}$. Then
$$
g(t) = -\log \det X - \log \det (I + tX^{-1/2}VX^{-1/2}) = -\log\det X - \sum\limits_{i=1}^{n} \log (1+t\lambda_i) 
$$ 
Obviously, $g(t)$ is a convex function of $t$

### 1.6. Sublevels and Epigraph
**Sublevels**: The $\alpha$-sublevel set of a function $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is defined as
$$
C_\alpha=\{\boldsymbol{x} \in \operatorname{dom} f \mid f(\boldsymbol{x}) \leq \alpha\} .
$$
Sublevel sets of a convex function are convex, for any value of $\alpha$. The converse is not true. A function can have all its sublevel sets convex, but not be a convex function. Such functions are called quasi-convex functions. 

**Quasi Convex**: 
$$
f(\alpha \boldsymbol{x}+(1-\alpha) \boldsymbol{y}) \leq \max \{f(\boldsymbol{x}), f(\boldsymbol{y})\}, \quad \alpha \in[0,1]
$$

**Epigraph**: 
The epigraph of a function $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is defined as
$$
\text { epi } f=\{(\boldsymbol{x}, t) \mid \boldsymbol{x} \in \operatorname{dom} f, f(\boldsymbol{x}) \leq t\}
$$
which is a subset of $\mathbb{R}^{n+1}$. A function is convex if and only if its epigraph is a convex set.


### 1.7. Jensen's Inequality
Let $f$ be a convex function, then 
$$
f\left(\theta_1 \boldsymbol{x}_1+\cdots+\theta_k \boldsymbol{x}_k\right) \leq \theta_1 f\left(\boldsymbol{x}_1\right)+\cdots+\theta_k f\left(\boldsymbol{x}_k\right)
$$
$$
f\left(\int_S p(\boldsymbol{x}) \boldsymbol{x}\mathrm{d} \boldsymbol{x}\right) \leq \int_S f(\boldsymbol{x}) p(\boldsymbol{x}) \mathrm{d} \boldsymbol{x}
$$


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