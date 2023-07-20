[No free lunch theorems for optimization](zotero://select/library/items/YXZZHSFB)
### 1. Notations:

**Hypothesis**:
An optimization problem $f$ is represented as a mapping
$$
f: \mathcal{X} \mapsto \mathcal{Y}, \quad|\mathcal{Y}|^{|\mathcal{X}|} \text { is a large but finite number }
$$

**Samples**:
$$
\left(d_m^x(1), d_m^y(1)\right),\left(d_m^x(2), d_m^y(2)\right), \cdots,\left(d_m^x(m), d_m^y(m)\right)
$$
Here, $m$ is the iteration times

**Algorithm**:
$$
a: d \in \mathcal{D} \mapsto\left\{x \mid x \notin d^x\right\}
$$
也就是说, 算法中不存在revisit

**Prior Distribution**:
$$
\mathbb{P}(f)=\mathbb{P}\left(f\left(x_1\right), \cdots, f\left(x_{|\mathcal{X}|}\right)\right)
$$
是优化目标函数 $f$ 的先验分布

**Measurement of Algorithm**:
The performance of an algorithm $a$ iterated $m$ times on a cost function $f$ is measured with
$$
\mathbb{P}\left(\boldsymbol{d}_m^y \mid f, m, a\right)
$$
这是得到一-个特定的 sample $\boldsymbol{d}_m^y$ 的条件概率.

### 2. NFL Theorem
---
**Theorem**: For any pair of algorithms $a_1$ and $a_2$
$$
\sum_f \mathbb{P}\left(\boldsymbol{d}_m^y \mid f, m, a_1\right)=\sum_f \mathbb{P}\left(\boldsymbol{d}_m^y \mid f, m, a_2\right)
$$
which indicates
$$
\mathbb{P}\left(\Phi\left(\boldsymbol{d}_m^y\right) \mid f, m, a\right) \text { is independent of } a
$$
---

##### Proof
We prove the result by induction. For $m=1$, it's easy to show that
$$
\sum_f \mathbb{P}\left(d_1^y \mid f, m=1, a\right)=\sum_f \delta\left(d_1^y, f\left(d_1^x\right)\right)=|\mathcal{Y}|^{|\mathcal{X}|-1}
$$
which is independent of $a$
If
$$
\sum_f \mathbb{P}\left(\boldsymbol{d}_m^y \mid f, m, a\right) \text { is independent of } a, \quad \forall \boldsymbol{d}_m^y
$$
Then we have
$$
\begin{aligned}
\mathbb{P}\left(d_{m+1}^y \mid f, m+1, a\right) & =\mathbb{P}\left(\left\{d_{m+1}^y(1), \cdots, d_{m+1}^y(m)\right\} \cdot d_{m+1}^y(m+1) \mid f, m+1, a\right) \\
& =\mathbb{P}\left(\boldsymbol{d}_m^y, d_{m+1}^y(m+1) \mid f, m+1, a\right) \\
& =\mathbb{P}\left(d_{m+1}^y(m+1) \mid \boldsymbol{d}_m^y, f, m+1, a\right) \cdot \mathbb{P}\left(\boldsymbol{d}_m^y \mid f, m+1, a\right)
\end{aligned}
$$
Take summation for $f$ on both sides
$$
\begin{aligned}
\sum_f \mathbb{P}\left(d_{m+1}^y \mid f, m+1, a\right) & =\sum_{f, x} \mathbb{P}\left(d_{m+1}^y(m+1) \mid f, x\right) \cdot \mathbb{P}\left(x \mid \boldsymbol{d}_m^y, f, m+1, a\right) \cdot \mathbb{P}\left(\boldsymbol{d}_m^y \mid f, m+1, a\right) \\
& =\sum_{f, x} \delta\left(d_{m+1}^y(m+1), f(x)\right) \cdot \mathbb{P}\left(x \mid \boldsymbol{d}_m^y, f, m+1, a\right) \cdot \mathbb{P}\left(\boldsymbol{d}_m^y \mid f, m+1, a\right) \\
& =\sum_{f, x, d_m^e} \delta\left(d_{m+1}^y(m+1), f(x)\right) \cdot \delta\left(x, a\left(\boldsymbol{d}_m\right)\right) \cdot \mathbb{P}\left(\boldsymbol{d}_m^x \mid \boldsymbol{d}_m^y, f, m+1, a\right) \cdot \mathbb{P}\left(\boldsymbol{d}_m^y \mid f, m+1, a\right) \\
& =\sum_{f, d_m^x} \delta\left(d_{m+1}^y(m+1), f\left(a\left(\boldsymbol{d}_m\right)\right)\right) \cdot \mathbb{P}\left(\boldsymbol{d}_m \mid f, m, a\right)
\end{aligned}
$$
Since the second term only depends on the $f$ values defined over points inside $\boldsymbol{d}_m^x$, while $\delta\left(d_{m+1}^y(m+1), f\left(a\left(\boldsymbol{d}_m\right)\right)\right)$ only depends on the $f$ values defined over points outside $\boldsymbol{d}_m^x$, we know
$$
\begin{aligned}
& \sum_f \mathbb{P}\left(d_{m+1}^y \mid f, m+1, a\right)=\sum_{d_m^s} \sum_{f\left(x \in d_m^z\right)} \mathbb{P}\left(\boldsymbol{d}_m \mid f, m, a\right) \sum_{f\left(x \notin d_m^{\star}\right)} \delta\left(d_{m+1}^y(m+1), f\left(a\left(\boldsymbol{d}_m\right)\right)\right) \\
& =|\mathcal{Y}|^{|\mathcal{X}|-m-1} \sum_{f\left(x \in \boldsymbol{d}_m^{\ddagger}\right), d_m^z} \mathbb{P}\left(\boldsymbol{d}_m \mid f, m, a\right) \\
& =\frac{1}{|\mathcal{Y}|} \sum_f \mathbb{P}\left(\boldsymbol{d}_m^y \mid f, m, a\right) \\
&
\end{aligned}
$$
By hypothesis, the right-hand side of the equation is independent of $a$

---
**Note:** NFL theorem tells us when the prior distribution $\mathbb{P}(f)$ is uniformly distributed, then all the algorithms are undistinguishable on average. But in practice, the prior distribution $\mathbb{P}(f)$ is not always uniformly distributed, which means we can design better algorithm.