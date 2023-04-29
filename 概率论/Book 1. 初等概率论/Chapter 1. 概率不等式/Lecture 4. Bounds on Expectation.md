## 1. Exponential Bounds on Probability
___
**Theorem**: Suppose that $X_n \geq 0$ and
$$
\mathbb{P}\left(X_n>\varepsilon\right) \leq c_1 e^{-c_2 n \varepsilon^2}, \quad \forall \varepsilon>0
$$
for some $c_2>0$ and $c_1>\dfrac{1}{e}$. Then,
$$
\mathbb{E} X_n \leq \sqrt{\frac{C}{n}}, \quad \text { where } C=\frac{1+\log \left(c_1\right)}{c_2}
$$
___
##### Proof: 
Recall that for any nonnegative random variable $Y$, we have
$$
\mathbb{E} Y=\int_0^{\infty} \mathbb{P}(Y \geq t) \mathrm{d} t
$$
Hence, for any $a>0$
$$
\mathbb{E} X_n^2=\int_0^{\infty} \mathbb{P}\left(X_n^2 \geq t\right) \mathrm{d} t \leq a+\int_a^{\infty} \mathbb{P}\left(X_n^2 \geq t\right) \mathrm{d} t
$$
From the condition, we know that
$$
\mathbb{P}\left(X_n>\sqrt{t}\right) \leq c_1 e^{-c_2 n t}
$$
Hence,
$$
\mathbb{E} X_n^2 \leq a+\int_a^{\infty} \mathbb{P}\left(X_n^2 \geq t\right) \mathrm{d} t \leq a+\int_a^{\infty} \mathbb{P}\left(X_n \geq \sqrt{t}\right) \mathrm{d} t \leq a+c_1 \int_a^{\infty} e^{-c_2 n t} \mathrm{~d} t=a+\frac{c_1 e^{-c_2 n a}}{c_2 n}
$$
Set
$$
\begin{gathered}
a=\frac{\log \left(c_1\right)}{n c_2} \\
\mathbb{E}\left(X_n^2\right) \leq \frac{\log \left(c_1\right)}{n c_2}+\frac{1}{n c_2}=\frac{1+\log \left(c_1\right)}{n c_2}
\end{gathered}
$$
Finally, we have
$$
\mathbb{E} X_n \leq \sqrt{\mathbb{E} X_n^2} \leq \sqrt{\frac{1+\log \left(c_1\right)}{n c_2}}
$$

## 2. Maximal Inequality (Bounded MGF)
___
**Theorem**: Let $X_1, \cdots, X_n$ be centered random variables such that
$$
\mathbb{E} e^{\lambda X_i} \leq e^{\psi(\lambda)}
$$
for some convex function $\psi(\cdot)$ and for all $\lambda$ satisfies $|\lambda|<\frac{1}{b}, b \geq 0$. Then
$$
\mathbb{E}\left(\max _{1 \leq i \leq n} X_i\right) \leq \inf _{\lambda \in\left(0, \frac{1}{b}\right)} \frac{\log n+\psi(\lambda)}{\lambda}
$$
___
##### Proof: 
By Jensen's inequality, we have
$$
\begin{aligned}
\exp \left\{t \mathbb{E}\left(\max _{1 \leq j \leq n} X_j\right)\right\} & \leq \mathbb{E}\left(\exp \left\{t \max _{1 \leq j \leq n} X_j\right\}\right) \\
& =\mathbb{E}\left(\max _{1 \leq j \leq n} \exp \left\{t X_j\right\}\right) \\
& \leq \sum_{i=1}^n \mathbb{E} e^{t X_j} \\
& \leq n e^{\psi(t)}
\end{aligned}
$$
Hence,
$$
t \mathbb{E}\left(\max _{1 \leq j \leq n} X_j\right) \leq \log n+\psi(t)
$$
___
#### Sub-Gaussian Case
When $X_i$ is sub-Gaussian, which means there exists $\sigma$ such that
$$
e^{t X_i} \leq e^{\sigma^2 t^2 / 2}, \quad \forall t \in \mathbb{R}
$$
Then we have
$$
\mathbb{E}\left(\max _{1 \leq i \leq n} X_i\right) \leq \sigma \sqrt{2 \log n}
$$

## 3. Maximal Inequality (Bound Mapping)
___
**Theorem:**  Let $X_1, \cdots, X_n$ be independent random variables on $\mathcal{X}$ and $f_1, f_2, \cdots, f_p$ be real-valued functions on $\mathcal{X}$ which satisfies for all $j=$ $1,2, \cdots, p$ and $i=1,2, \cdots, n$
$$
\mathbb{E} f_j\left(X_i\right)=0, \quad\left|f_j\left(X_i\right)\right| \leq a_{i j}
$$
Then
$$
\mathbb{E}\left(\max _{1 \leq j \leq p}\left|\sum_{i=1}^n f_j\left(X_i\right)\right|\right) \leq \sqrt{2 \log (2 p)} \max _{1 \leq j \leq p} \sqrt{\sum_{i=1}^n a_{i j}^2}
$$
___
##### Proof: 
Let
$$
\varphi_j\left(X_1, \cdots, X_n\right)=\left|\sum_{i=1}^n f_j\left(X_i\right)\right|
$$
By Jensen's inequality
$$
\begin{aligned}
\exp \left\{t \mathbb{E}\left(\max _{1 \leq j \leq p} \varphi_j\right)\right\} & \leq \mathbb{E}\left(\exp \left\{t \max _{1 \leq j \leq p} \varphi_j\right\}\right) =\mathbb{E}\left(\max _{1 \leq j \leq p} \exp \left\{t \varphi_j\right\}\right)
\end{aligned}
$$
From the condition, we have
$$
\varphi_j \leq \max _{1 \leq j \leq p} \sum_{i=1}^n a_{i j}
$$
Thus
$$
\mathbb{E}\left(\max _{1 \leq j \leq p} \exp \left\{t \varphi_j\right\}\right) \leq \exp \left\{t \max _{1 \leq j \leq p} \sum_{i=1}^n a_{i j}\right\}
$$
