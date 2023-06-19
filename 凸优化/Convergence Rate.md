## 1. Convergence 
### 1.1. Definition
Assume $\boldsymbol{x}_k \rightarrow \boldsymbol{x}^*$. We define the sequence of errors to be
$$
\boldsymbol{e}_k=\boldsymbol{x}_k-\boldsymbol{x}^*
$$
We say that the sequence $\left\{\boldsymbol{x}_k\right\}$ converges to $\boldsymbol{x}^*$ with rate $r$ and rate constant $C$ if
$$
\lim _{k \rightarrow \infty} \frac{\left\|\boldsymbol{e}_{k+1}\right\|}{\left\|\boldsymbol{e}_k\right\|^r}=C, \quad(C<\infty) .
$$
Here, $r>1$ or $r=1, C<1$
### 1.2. Classification
1. **Linear**:  $r=1,0<C<1$, also named $Q$-linear, where $Q$ stands for Quotient
2. **Sublinear:** $\boldsymbol{e}_k \rightarrow 0$ and $r=1, C=1$
3. **Superlinear:** $r=1, C=0$
4. **Quadratic:** $r=2$
5. **Cubic:** $r=3$
### 1.3. Calculation of Convergence Rate 
From the definition, we know
$$
\log \left\|\boldsymbol{e}_{k+1}\right\| \approx r \log \left\|\boldsymbol{e}_k\right\|+\log C
$$
Estimating the order $r$
$$
r \approx \dfrac{\log \dfrac{\left\|\boldsymbol{x}_{k+1}-\boldsymbol{x}_k\right\|}{\left\|\boldsymbol{x}_k-\boldsymbol{x}_{k-1}\right\|}}{\log \dfrac{\left\|x_k-\boldsymbol{x}_{k-1}\right\|}{\left\|\boldsymbol{x}_{k-1}-\boldsymbol{x}_{k-2}\right\|}} .
$$
### 1.4. R-linear
Assume $\boldsymbol{x}_k \rightarrow \boldsymbol{x}^*$. We say that the sequence $\left\{\boldsymbol{x}_k\right\}$ converges to $\boldsymbol{x}^*$ R-linearly if
$$
\left\|\boldsymbol{x}_k-\boldsymbol{x}^*\right\| \leq \boldsymbol{e}_k
$$
and $\left\{\boldsymbol{e}_k\right\}$ converges to 0 Q-linearly. Here, $\mathrm{R}$ stands for root.