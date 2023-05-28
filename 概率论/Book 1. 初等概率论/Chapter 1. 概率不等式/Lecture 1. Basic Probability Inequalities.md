
## 1. Markov Inequality
___
**Theorem**: Let $\varphi(x): \mathbb{R} \rightarrow \mathbb{R}^{+}$be any non-decreasing positive function. For any real valued andom variable $X$,
$$
\mathbb{P}(X \geq a) \leq \mathbb{E}[\varphi(X)] \frac{1}{\varphi(a)}, \quad \forall a \in \mathbb{R}
$$
___
##### Proof:
For any random variable $X \geq 0$ We know that
$$
\mathbb{P}(X \geq a)=\mathbb{E} I(X \geq a) \leq \frac{1}{a} \mathbb{E} X \mathbb{I}(X \geq a) \leq \frac{\mathbb{E} X}{a}
$$
Then for any real valued random variable $X$, since $\varphi(X)$ is a random variable which is larger than $0$, we know the inequality holds
#####
___


## 2. Chebyshev Inequality

___
**Theorem**: Let $X$ be a random variable with finite expected value $\mu$ and finite non-zero variance $\sigma^2$. Then for any $t>0$, we have
$$
\mathbb{P}(|X-\mu|>t) \leq \frac{\sigma^2}{t^2}
$$
___


## 3. Chernoff Bound
___
**Theorem**: Let $X$ be a random variable
$$
\mathbb{P}(X \geq a) \leq \inf _{t>0} \mathbb{E} e^{t(X-a)}
$$
___










