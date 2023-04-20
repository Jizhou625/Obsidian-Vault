如不另加说明, 以下关于Topology的定义和结论都是建立在$\mathbb{R}^n$上
### 1. Open Set
**Definition**: A subset $\mathcal{C}$ of $\mathbb{R}^n$ is called open, if for every $x \in \mathcal{C}$ there exists $\varepsilon>0$ such that the ball
$$
B_{\varepsilon}(\boldsymbol{x})=\left\{\boldsymbol{y} \mid\|\boldsymbol{y}-\boldsymbol{x}\|_2 \leq \varepsilon\right\}
$$
is included in $\mathcal{C}$.
**Examples**:
$$\{x \mid a<x<b\},\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\},\{\boldsymbol{x} \mid \boldsymbol{x}>\mathbf{0}\}, \mathbb{S}_{++}^n=\{X \mid X \succ \mathbf{0}\}$$


### 2. Closed Set
**Definition**: A subset $\mathcal{C}$ of $\mathbb{R}^n$ is called closed, if its complement $\mathcal{C}^c=\mathbb{R}^n \backslash \mathcal{C}$ is open.
**Examples**:
$$
\{x \mid a \leq x \leq b\},\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\},\{\boldsymbol{x} \mid \boldsymbol{x} \geq \mathbf{0}\}, \mathbb{S}_{+}^n=\{X \mid X \succeq \mathbf{0}\}
$$


### 3. Bounded Set
**Definition**: A subset $\mathcal{C}$ of $\mathbb{R}^n$ is called bounded, if $\exists R>0$ such that $\|x\|<R,\ \forall x \in \mathcal{C}$.
**Examples**: 
$$
\{x \mid a \leq x<b\},\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\},\{\boldsymbol{x} \mid \mathbf{1}>\boldsymbol{x} \geq \mathbf{0}\},\{X \mid I \succeq X \succ 0\}
$$


### 4. Compact Set
**Definition**: A subset $\mathcal{C}$ of $\mathbb{R}^n$ is called compact, if it is both bounded and closed.
**Examples**:
$$
\{x \mid a \leq x \leq b\},\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\},\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x} \geq \mathbf{0}\}, \mathbb{S}_{+}^n=\{X \mid I \succeq X \succeq \mathbf{0}\}
$$


### 5. Interior
**Definition**: The interior of $\mathcal{C} \subseteq \mathbb{R}^n$ is defined as $\mathcal{C}^{\circ}=\left\{\boldsymbol{y} \mid \exists \varepsilon>0\right.$ such that $\left.\mathcal{B}_{\varepsilon}(\boldsymbol{y}) \subset \mathcal{C}\right\}$
**Examples**: 
$$
\begin{gathered}
(\{x \mid a \leq x \leq b\})^{\circ}=\{x \mid a<x<b\} \\
(\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\})^{\circ}=\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\} \\
(\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x} \geq \mathbf{0}\})^{\circ}=\{\boldsymbol{x} \mid \mathbf{1}>\boldsymbol{x}>\mathbf{0}\} \\
(\{X \mid I \succeq X \succeq 0\})^{\circ}=\{X \mid I \succ X \succ 0\}
\end{gathered}
$$


### 6. Closure
**Definition**: The closure of $\mathcal{C} \subset \mathbb{R}^n$ is defined as
$$
\overline{\mathcal{C}}=\mathbb{R}^n \backslash\left(\mathbb{R}^n \backslash \mathcal{C}\right)^{\circ}=\left(\left(\mathcal{C}^c\right)^{\circ}\right)^c
$$
**Examples**: 
$$
\begin{gathered}
\overline{\{x \mid a \leq x<b\}}=\{x \mid a \leq x \leq b\} \\
\overline{\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\}}=\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\| \leq 1\} \\
\overline{\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x}>\mathbf{0}\}}=\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x} \geq \mathbf{0}\} \\
\overline{\{X \mid I \succ X \succ 0\}}=\{X \mid I \succeq X \succeq 0\}
\end{gathered}
$$


### 7. Boundary
**Definition**: The boundary of $\mathcal{C} \subseteq \mathbb{R}^n$ is defined as $\partial \mathcal{C}=\overline{\mathcal{C}} \backslash \mathcal{C}^{\circ}$.
**Examples**: 
$$
\begin{gathered}
\partial(\{x \mid a \leq x<b\})=\{a, b\} \\
\partial(\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|<1\})=\{\boldsymbol{x} \mid\|\boldsymbol{x}-\boldsymbol{a}\|=1\}\\
\partial(\{\boldsymbol{x} \mid \mathbf{1} \geq \boldsymbol{x}>\mathbf{0}\})=\left\{\boldsymbol{x} \mid 0 \leq x_i \leq 1 . \forall i, \text { and } \exists j \text { such that } x_j=0 \text { or } 1\right\} \\ 
\partial(\{X \mid I \succ X \succ 0\})=\left\{X \mid 0 \leq \lambda_i(X) \leq 1, \forall i \text { and } \exists j \text { such that } \lambda_j(X)=0 \text { or } 1\right\}
\end{gathered}
$$

### 8. Closedness for function
**Definition**: A function $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is said to be closed if, for each $\alpha \in \mathbb{R}$, the sublevel set
$$
\{\boldsymbol{x} \in \operatorname{dom} f \mid f(\boldsymbol{x}) \leq \alpha\}
$$
is closed. This is equivalent to the condition that the epigraph of $f$
$$
\text { epi } f=\left\{(\boldsymbol{x}, t) \in \mathbb{R}^{n+1} \mid \boldsymbol{x} \in \operatorname{dom} f, f(\boldsymbol{x}) \leq t\right\}
$$
is closed.
**Properties**: 
1. If $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is continuous, and $\operatorname{dom} f$ is closed, then $f$ is closed.

2. If $f: \mathbb{R}^n \rightarrow \mathbb{R}$ is continuous, with dom $f$ open, then $f$ is closed iff $f$ converges to $\infty$ along every sequence converging to a boundary point of $\operatorname{dom} f$. In other words, if
   $$
   \lim _{i \rightarrow \infty} \boldsymbol{x}_i=\boldsymbol{x} \in \partial(\operatorname{dom} f), \quad \boldsymbol{x}_i \in \operatorname{dom} f
   $$
   Then
   $$
   \lim _{i \rightarrow \infty} f\left(\boldsymbol{x}_i\right)=\infty
   $$
   

