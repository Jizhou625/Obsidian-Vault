## 1. Convex Sets

### 1.1. Definition
A set $C$ is convex if the line segment between any two points in $C$ lies in $C$, i.e. if for any $\boldsymbol{x}_1, \boldsymbol{x}_2\in C$ and any $\theta$ with $0\le \theta\le 1$, we have
$$
\theta \boldsymbol{x}_1 + (1-\theta)\boldsymbol{x}_2\in C
$$

### 1.2. Convex Hull
The convex hull of a set $C$, denoted as $\mathrm{conv}C$, is the set of all convex combinations of points in $C$:
$$
\mathrm{conv}C = \{\theta_1\boldsymbol{x}_1+\cdots+\theta_k\boldsymbol{x}_k\mid \boldsymbol{x}_i\in C, \theta_i\ge 0, i=1,2,\cdots,k, \theta_1+\theta_2+\cdots+\theta_k=1\}
$$
$\mathrm{conv}C$ is always convex. It is the smallest convex set that contains $C$

### 1.3. General convex combination

Suppose $\theta_1, \theta_2,\cdots$ satisfy
$$
\theta_i\ge 0, \quad i=1,2,\cdots,\quad \sum\limits_{i=1}^{\infty}\theta_i = 1
$$
and $\boldsymbol{x}_1, \boldsymbol{x}_2, \cdots\in C$, where $C\subseteq \mathbb{R}^n$ is convex. Then 
$$
\sum\limits_{i=1}^{\infty}\theta_i\boldsymbol{x}_i \in C \quad \text{ If the series converges. }
$$
More generally, suppose $p: \mathbb{R}^n\to \mathbb{R}$ satisfies $p(\boldsymbol{x})\ge 0$ for all $\boldsymbol{x}\in C$ and $\int p(\boldsymbol{x}) \, \mathrm{d}\boldsymbol{x}=1$, where $C\subset \mathbb{R}^n$ is convex.  Then
$$
\int \boldsymbol{x}p(\boldsymbol{x}) \, \mathrm{d}\boldsymbol{x} \in C\implies \mathbb{E}\boldsymbol{x}\in C,\quad \text{If the integral exists. }
$$

### 1.4. Examples
1. **Empty Set**: $\varnothing$
2. **Norm Ball**: $\{\boldsymbol{x}\mid \|\boldsymbol{x}\|\le r\}$
3. **Hyperplane**: $\{\boldsymbol{x}\mid \boldsymbol{a}^{\top}\boldsymbol{x} = b\}$
4. **Halfspace**: $\{\boldsymbol{x} \mid \boldsymbol{a}^{\top}\boldsymbol{x}\le b\}$
5. **Affine Space**: $\{\boldsymbol{x}\mid \mathcal{A}(\boldsymbol{x}) = \boldsymbol{b}\}$
6. **Polyhedron**: $\{\boldsymbol{x}\mid A\boldsymbol{x}\le \boldsymbol{b}\}$


## 2. Cones

### 2.1 Definition 

A set $C$ is called a cone if for every $\boldsymbol{x}\in C$ and $\theta>0$, we have $\theta \boldsymbol{x}\in C$. A set $C$ is a convex cone if it is convex and a cone, which means that for any $\boldsymbol{x}_1, \boldsymbol{x}_2\in C$ and $\theta_1, \theta_2>0$, we have 
$$
\theta_1 \boldsymbol{x}_1 + \theta_2\boldsymbol{x}_2\in C
$$


### 2.2. Conic Hull
The conic hull of a set $C$ is the set of all conic combinations of points in $C$
$$
\{\theta_1\boldsymbol{x}_1 + \cdots+ \theta_k\boldsymbol{x}_k\mid \boldsymbol{x}_i\in C, \theta_i\ge0, i=1,2,\cdots,k\}
$$
It is the smallest convex cone that contains $C$

### 2.3. Dual Cones
Let $K$ be a cone. The set
$$
K^*=\{\boldsymbol{y}\mid \boldsymbol{x}^{\top} \boldsymbol{y}\ge0 \text{ for all }\boldsymbol{x}\in K\}
$$
is called the dual cone of $K$. 
**Properties**:
1. $K^*$ is a cone, and is always convex
2. $K_1 \subseteq K_2 \implies K_2^* \subseteq K_1^*$
3. $K^{**}$ is the closure of the convex hull of $K$
### 2.4. Examples:
1. **Half Spaces**: $\{\boldsymbol{x} \mid \boldsymbol{a}^{\top}\boldsymbol{x}\le b\}$
2. **Norm Cone**: $\{(\boldsymbol{x}, t)\mid \|\boldsymbol{x}\|\le t\}$, when we use second-order norm $\|\cdot\|_2$, we get the second-order cone. 

	![image-20230319153718348](Lecture%201.%20Convex%20Sets.assets/image-20230319153718348.png)
3. **Normal Cone**: Given any convex set $C\subset \mathbb{R}^n$ and $\boldsymbol{x}\in C$, $N(\boldsymbol{x}, C) = \{\boldsymbol{g} \in \mathbb{R}^n\mid \boldsymbol{g}^{\top}\boldsymbol{x}\ge \boldsymbol{g}^{\top}\boldsymbol{y}, \forall \boldsymbol{y}\in C\}$.  When $\boldsymbol{x}$ is interior point, we have $N(\boldsymbol{x}, C) = \{\boldsymbol{0}\}$

## 3. Affine Sets

### 3.1. Affine subspace
A set is called an affine subspace if and only if it contains all the lines passing through any two points. 
$$
\boldsymbol{y}=\theta_1\boldsymbol{x}_1+(1-\theta)\boldsymbol{x}_2
$$
If $C$ is an affine subspace and $\boldsymbol{x}_0\in C$, then the set
$$
V = C - \boldsymbol{x}_0= \{\boldsymbol{x}-\boldsymbol{x}_0\mid \boldsymbol{x}\in C\}
$$
is a linear subspace. We define $\mathrm{dim}C = \mathrm{dim}V$

### 3.2. Affine Hull
The set of all affine combinations of points in some set $C$ is called affine hull of $C$, and denoted $\mathrm{aff} C$
$$
\mathrm{aff}C = \{\theta_1\boldsymbol{x}_1+\cdots+\theta_k\boldsymbol{x}_k\mid \boldsymbol{x}_1,\cdots, \boldsymbol{x}_k\in C, \theta_1+ \cdots+\theta_k=1\}
$$
The affine hull is the smallest affine set that contains $C$. We define the affine dimension of a set $C$ as the dimension of its affine hull. 

### 3.3. Relative Interior
If $\mathrm{aff}C$ is not the whole space, we define the relative interior of the set $C$, denoted $\mathrm{ri}C$, as its interior relative to $\mathrm{aff}C$
$$
\operatorname{ri} C=\{\boldsymbol{x} \in C \mid \mathcal{B}(\boldsymbol{x}, r) \cap \operatorname{aff} C \subseteq C \text { for some } r>0\}
$$
We can then define the relative boundary of a set $C$ as $\bar{C}\backslash \mathrm{ri}C$





## 4. Operations that Preserve Convex
### 4.1. Intersection
If $S_\alpha$ is convex for every $\alpha \in \mathcal{A}$, then 
$$
\bigcap_{\alpha \in \mathcal{A}} S_\alpha \text{ is convex.}
$$
**Examples:**
1. Consider the set
   $$
   S=\left\{\boldsymbol{x} \in \mathbb{R}^m\mid |p(t)|\leq 1 \text { for }|t| \leq \pi / 3\right\}
   $$
   where $p(t)=\sum\limits_{k=1}^m x_k \cos k t$. The set $S$ can be expressed as the intersection of an infinite number of slabs: $S=\bigcap\limits_{|t| \leq \pi / 3} S_t$, where
   $$
   S_t=\left\{\boldsymbol{x} \mid-1 \leq(\cos t, \ldots, \cos m t)^{\top} \boldsymbol{x} \leq 1\right\}
   $$
   and so is convex.

2. A closed convex set $S$ is the intersection of all halfspaces that contain it:
   $$
   S=\bigcap\{\mathcal{H} \mid \mathcal{H} \text { halfspace, } S \subseteq \mathcal{H}\}
   $$
   
### 4.2. Affine Function

Suppose $S \subseteq \mathbb{R}^n$ is convex and $f: \mathbb{R}^n\to \mathbb{R}^m$ is an affine function: $f(\boldsymbol{x}) = A\boldsymbol{x}+\boldsymbol{b}$. Then the image of $S$ under $f$
$$
f(S)=\{f(\boldsymbol{x})\mid  \boldsymbol{x}\in S\}
$$
is convex. Similarly, if $f: \mathbb{R}^k \to \mathbb{R}^n$ is an affine function, the inverse image of $S$ under $f$
$$
f^{-1}(S) = \{\boldsymbol{x}\mid f(\boldsymbol{x})\in S\}
$$
is convex. 
### 4.3. Sum and Cartesian Product
If $S_1$ and $S_2$ are convex, then their sum $S_1+S_2 = \{\boldsymbol{x}+\boldsymbol{y}\mid \boldsymbol{x}\in S_1, \boldsymbol{y}\in S_2\}$ is convex, so is their Cartesian product $S_1\times S_2 = \{(\boldsymbol{x}_1, \boldsymbol{x}_2)\mid \boldsymbol{x}_1\in S_1, \boldsymbol{x}_2\in S_2\}$
___
**Examples**:
1. The polyhedron $\{\boldsymbol{x}\mid A\boldsymbol{x}\preceq \boldsymbol{b}, C\boldsymbol{x}=\boldsymbol{d}\}$ can be expressed as the inverse image of the Cartesian product of the nonnegative orthant and the origin under the affine function $f(\boldsymbol{x}) = (\boldsymbol{b} - A\boldsymbol{x}, \boldsymbol{d}-C\boldsymbol{x})$ 
   $$
   \{\boldsymbol{x}\mid A\boldsymbol{x}\preceq \boldsymbol{b}, C\boldsymbol{x}=\boldsymbol{d}\} = \{\boldsymbol{x}\mid f(\boldsymbol{x})\in \mathbb{R}_+^m\times \{\boldsymbol{0}\}\}
   $$
   Thus, the polyhedron $\{\boldsymbol{x}\mid A\boldsymbol{x}\preceq \boldsymbol{b}, C\boldsymbol{x}=\boldsymbol{d}\}$ is convex
2. The condition $A(\boldsymbol{x}) = x_1A_1+\cdots+x_nA_n \preceq B$ where $B, A_i\in \mathbb{S}^m$, is called a linear matrix inequality in $\boldsymbol{x}$. The solution set of a linear matrix inequality, $\{\boldsymbol{x} \mid A(\boldsymbol{x} ) \preceq B\}$, is convex. Indeed, it is the inverse image of the positive semidefinite cone under the affine function $f: \mathbb{R}^n \rightarrow \mathbb{S}^m$ given by $f(\boldsymbol{x})=B-A(\boldsymbol{x})$.
3. The set 
   $$
   \{\boldsymbol{x}\mid \boldsymbol{x}^{\top} P\boldsymbol{x}\le (\boldsymbol{c}^{\top} \boldsymbol{x})^2, \quad \boldsymbol{c}^{\top} \boldsymbol{x}\ge 0 \}
   $$ 
   where $P\in \mathbb{S}_+^n$ and $\boldsymbol{c}\in \mathbb{R}^n$ is convex, since it is the inverse image of the second-order cone 
   $$
   \{(\boldsymbol{z}, t)\mid \boldsymbol{z}^{\top} \boldsymbol{z}\le t^2, t\ge 0\}$$ 
   under the affine function $f(\boldsymbol{x}) = (P^{\frac{1}{2}}\boldsymbol{x}, \boldsymbol{c}^{\top}\boldsymbol{x})$. 
4. The ellipsoid 
   $$
   \varepsilon=\left\{\boldsymbol{x} \mid\left(\boldsymbol{x}-\boldsymbol{x}_c\right)^{\top}  P^{-1}\left(\boldsymbol{x}-\boldsymbol{x}_c\right) \leq 1\right\},\quad P\in \mathbb{S}_{++}^n
   $$
   is the image of the unit Euclidean ball $\left\{\boldsymbol{u}\mid\|\boldsymbol{u}\|_2 \leq 1\right\}$ under the affine mapping $f(\boldsymbol{u})=P^{1 / 2}\boldsymbol{u}+\boldsymbol{x}_c$.  It is also the inverse image of the unit ball under the affine mapping $g(\boldsymbol{x})=P^{-1 / 2}\left(\boldsymbol{x}-\boldsymbol{x}_c\right)$
### 4.4. Perspective Functions
The perspective function $P: \mathbb{R}^{n+1}\to \mathbb{R}^n$ with domain $\mathrm{dom} P = \mathbb{R}^n\times \mathbb{R}_{++}$, is defined as $P(\boldsymbol{z}, t) = \dfrac{\boldsymbol{z}}{t}$. 

![Pasted image 20230319151029](Lecture%201.%20Convex%20Sets.assets/Pasted%20image%2020230319151029.png)

The inverse image of a convex set under the perspective function is also convex: if $C\subset \mathbb{R}^n$ is convex, then
$$
P^{-1}(C) = \left\{(\boldsymbol{x},t)\in \mathbb{R}^{n+1}\mid \dfrac{\boldsymbol{x}}{t}\in C, t>0\right\}
$$

is convex. 

### 4.5. Linear-fractional Function

A linear-fractional function is formed by composing the perspective function with an affine function. Suppose $g: \mathbb{R}^n\to \mathbb{R}^{m+1}$ is affine, i.e. 
$$
g(\boldsymbol{x})=\left(\begin{array}{c}
 {A} \\
\boldsymbol{c}^{\top}
\end{array}\right) \boldsymbol{x}+\left(\begin{array}{l}
\boldsymbol{b} \\
d
\end{array}\right),
$$
where $A\in \mathbb{R}^{m\times n}, \boldsymbol{b}\in \mathbb{R}^m, \boldsymbol{c}\in \mathbb{R}^n$, and $d\in \mathbb{R}$. The function $f: \mathbb{R}^n\to \mathbb{R}^m$ given by $f = P\circ g$. i.e. 
$$
f(\boldsymbol{x}) = \dfrac{A\boldsymbol{x}+\boldsymbol{b}}{\boldsymbol{c}^{\top}\boldsymbol{x}+d},\quad \mathrm{dom} f = \{\boldsymbol{x}\mid \boldsymbol{c}^{\top}\boldsymbol{x}+d>0\}
$$
is called a linear-fractional function. 




## 5. Separating and Supporting Hyperplanes
### 5.1. Separating Hyperplanes Theorem
**Theorem**: Suppose $C$ and $D$ are two convex sets that do not intersect, i.e., $C \cap D=\varnothing$. Then there exist $\boldsymbol{a} \neq \boldsymbol{0}$ and $b$ such that $\boldsymbol{a}^{\top}\boldsymbol{x} \leq b$ for all $\boldsymbol{x} \in C$ and $\boldsymbol{a}^{\top} \boldsymbol{x} \geq b$ for all $\boldsymbol{x} \in D$. In other words, the affine function $\boldsymbol{a}^{\top} \boldsymbol{x}-b$ is nonpositive on $C$ and nonnegative on $D$.

The hyperplane $\left\{\boldsymbol{x} \mid \boldsymbol{a}^{\top} \boldsymbol{x}=b\right\}$ is called a separating hyperplane for the sets $C$ and $D$, or is said to separate the sets $C$ and $D$.
___

**Example:**
Suppose $C$ is convex and $D$ is affine, i.e., $D=\left\{F\boldsymbol{ u}+\boldsymbol{g} \mid \boldsymbol{u} \in \mathbb{R}^m\right\}$, where ${F} \in \mathbb{R}^{n \times m}$. Suppose $C$ and $D$ are disjoint, so by the separating hyperplane theorem there are $\boldsymbol{a} \neq 0$ and $b$ such that $\boldsymbol{a}^{\top} \boldsymbol{x} \leq b$ for all $\boldsymbol{x} \in C$ and $\boldsymbol{a}^{\top} \boldsymbol{x} \geq$ $b$ for all $\mathrm{x} \in D$.

Now $\boldsymbol{a}^{\top} \boldsymbol{x} \geq b$ for all $\boldsymbol{x} \in D$ means $\boldsymbol{a}^{\top} F\boldsymbol{u} \geq b-\boldsymbol{a}^{\top} \boldsymbol{g}$ for all $\boldsymbol{u} \in \mathbb{R}^m$. But a linear function is bounded below on $\mathbb{R}^m$ only when it is zero, so we conclude $\boldsymbol{a}^{\top} F=\boldsymbol{0}$ (and hence, $b \leq \boldsymbol{a}^{\top}  \boldsymbol{g}$ )

Thus we conclude that there exists $\boldsymbol{a} \neq 0$ such that $F^{\top} \boldsymbol{a}=\boldsymbol{0}$ and $\boldsymbol{a}^{\top} \boldsymbol{x} \leq \boldsymbol{a}^{\top} \boldsymbol{g}$ for all $\boldsymbol{x} \in C$.

![image-20230319192022011](Lecture%201.%20Convex%20Sets.assets/image-20230319192022011.png)

### 5.2. Strict Separation:
If the separating hyperplane satisfies the stronger condition that $\boldsymbol{a}^{\top} \boldsymbol{x}<b$ for all $\boldsymbol{x} \in C$ and $\boldsymbol{a}^{\top} \boldsymbol{x}>b$ for all $\boldsymbol{x} \in D$, then the sets $C$ and $D$ are called strictly separated. Disjoint convex sets need not to be strictly separated by a hyperplane, even when the sets are closed. 

There are some examples of strict separation. 
1. a point and a closed convex set. 
2. a closed convex set is the intersection of all halfspaces that contain it. 

### 5.3. Converse Separating Hyperplanes Theorem
Any two convex sets $C$ and $D$, at least one of which is open, are disjoint if and only if there exists a separating hyperplane.

### 5.4. Theorem of the Alternative (Fakas' Lemma)
For $A\in\mathbb{R}^{m\times n}$ and $\boldsymbol{b}\in \mathbb{R}^m$, the following are strong alternatives:
1. $\exists \boldsymbol{x}\in \mathbb{R}^n_+$ such that $A\boldsymbol{x}=\boldsymbol{b}$
2. $\exists \boldsymbol{y} \in \mathbb{R}^m$ such that $A^{\top}\boldsymbol{y}\succeq 0$ and $\boldsymbol{b}^{\top}\boldsymbol{y}<0$
___
##### Proof: 
First, we prove that $1\Longrightarrow \neg 2$: For $\boldsymbol{x}\in \mathbb{R}^n_+$ with $A\boldsymbol{x}=\boldsymbol{b}$ and $\boldsymbol{y}\in \mathbb{R}^m$ with $A^{\top}\boldsymbol{y}\succeq 0$ we have $\boldsymbol{b}^{\top}\boldsymbol{y} =\boldsymbol{x}^{\top} A^{\top}\boldsymbol{y}\ge 0$. 

Then, we prove that $\neg 1\Longrightarrow 2$: Consider the closed convex cone $C = \mathrm{cone}(A)$. Here, $\mathrm{cone}(A)$ is the cone of the column space of $A$. $\neg 1$ means that $\boldsymbol{b}$ is not in  $\mathrm{cone}(A)$. By the separating hyperplane theorem we can get that there exist $\boldsymbol{y}\in \mathbb{R}^m$ and $\mu$ such that $\langle \boldsymbol{y}, \boldsymbol{z}\rangle \ge \mu > \langle \boldsymbol{y}, \boldsymbol{b}\rangle$ for all $\boldsymbol{z} \in C$. Then we can get that $\langle A^{\top}\boldsymbol{y}, \boldsymbol{x} \rangle \ge \mu, \forall \boldsymbol{x}\ge 0$, which implies $A^{\top}\boldsymbol{y}\ge 0$ and $\mu \le 0$.  

### 5.5. Supporting Hyperplanes Theorem
Suppose $C \subseteq \mathbb{R}^n$, and $\boldsymbol{x}_0$ is a point in its boundary $\partial C$. If $\boldsymbol{a} \neq \boldsymbol{0}$ satisfies $\boldsymbol{a}^{\top}  \boldsymbol{x} \leq \boldsymbol{a}^{\top}  \boldsymbol{x}_0$ for all $\boldsymbol{x} \in C$, then the hyperplane $\left\{\boldsymbol{x} \mid \boldsymbol{a}^{\top}  \boldsymbol{x}=\boldsymbol{a}^{\top}  \boldsymbol{x}_0\right\}$ is called a supporting hyperplane to $C$ at the point $\boldsymbol{x}_0$.

For any nonempty convex set $C$, and any $\boldsymbol{x}_0\in \partial C$, there exists a supporting hyperplane to $C$ at $\boldsymbol{x}_0$.