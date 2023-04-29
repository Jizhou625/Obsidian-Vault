
## 1. Hoeffding Lemma
___
**Theorem**: Let $X$ be any real-valued random variable such that $a\le X \le b$ almost surely. Without loss of generality, assume $\mathbb{E}X = 0$.  Then, for all $\lambda \in \mathbb{R}$  
$$
\mathbb{E}\mathrm{e}^{\lambda X}\le\exp\left(\dfrac{\lambda^2(b-a)^2}{8}\right) 
$$
___
***Proof:*** Without loss of generality, by replacing $X$ by $X-\mathbb{E} X$, we can assume $\mathbb{E} X=0$, so that $a \leq 0 \leq b$. Since $\mathrm{e}^{\lambda x}$ is a convex function of $x$, we have that for all $x \in[a, b]$
$$
\mathrm{e}^{\lambda x} \leq \frac{b-x}{b-a} \mathrm{e}^{\lambda a}+\frac{x-a}{b-a} \mathrm{e}^{\lambda b}
$$
As a result
$$
\begin{aligned}
\mathbb{E} \mathrm{e}^{\lambda X} & \leq \mathbb{E}\left(\frac{b-X}{b-a} \mathrm{e}^{\lambda a}+\frac{X-a}{b-a} \mathrm{e}^{\lambda b}\right) \\
& \leq \frac{b-\mathbb{E}[X]}{b-a} \mathrm{e}^{\lambda a}+\frac{\mathbb{E}[X]-a}{b-a} \mathrm{e}^{\lambda b} \\
& =\frac{b}{b-a} \mathrm{e}^{\lambda a}-\frac{a}{b-a} \mathrm{e}^{\lambda b}
\end{aligned}
$$
Let
$$
L(h)=\frac{h a}{b-a}+\ln \left(1+\frac{a-\mathrm{e}^h a}{b-a}\right)
$$
we can write that
$$
\frac{b}{b-a} \mathrm{e}^{\lambda a}-\frac{a}{b-a} \mathrm{e}^{\lambda b}=\mathrm{e}^{L(\lambda(b-a))}
$$
By computing derivatives, we can find that
$$
L(0)=L^{\prime}(0)=0, \quad L^{\prime \prime}(h)=-\frac{a b \mathrm{e}^h}{\left(b-a \mathrm{e}^h\right)^2} \leq \frac{1}{4}
$$
Then, from Taylor's expansion, we have that
$$
L(h)=L(0)+h L^{\prime}(0)+\frac{1}{2} h^2 L^{\prime \prime}(h \theta) \leq \frac{1}{8} h^2
$$
Thus, we have proved that
$$
\mathbb{E} \mathrm{e}^{\lambda(X-\mathbb{E} X)} \leq \exp \left(\frac{\lambda^2(b-a)^2}{8}\right)
$$
## 2. Hoeffding Inequality
___
Theorem: Suppose $X_i$ are bounded independent random variables with bound $\left[a_i, b_i\right]$. Let $S_n=\sum\limits_{i=1}^n X_i$, we have
$$
\mathbb{P}\left(\left|S_n-\mathbb{E} S_n\right| \geq t\right) \leq 2 \exp \left(-\frac{2 t^2}{\sum\limits_{i=1}^n\left(b_i-a_i\right)^2}\right)
$$
___
***Proof:*** Using Chernoff Bound lemma, we know that
$$
\begin{aligned}
\mathbb{P}\left(S_n-\mathbb{E} S_n \geq t\right) & \leq \exp \left\{s\left(S_n-\mathbb{E} S_n\right)-s t\right\} \\
& =\mathrm{e}^{-s t} \exp \left\{s\left(S_n-\mathbb{E} S_n\right)\right\} \\
& =\mathrm{e}^{-s t} \prod_{i=1}^n \mathrm{e}^{s\left(X_i-\mathbb{E} X_i\right)} \\
& \leq \mathrm{e}^{-s t} \prod_{i=1}^n \exp \left(\frac{s^2\left(b_i-a_i\right)^2}{8}\right) \\
& =\exp \left(-s t+\frac{1}{8} s^2 \sum_{i=1}^n\left(b_i-a_i\right)^2\right)
\end{aligned}
$$
The upper bound is the best for the value of $s$ minimizing the value of the right hand side, which means
$$
s=\frac{4 t}{\sum\limits_{i=1}^n\left(b_i-a_i\right)^2}
$$
Then we can get that
$$
\mathbb{E}\left(S_n-\mathbb{E} S_n \geq t\right) \leq \exp \left(-\frac{2 t^2}{\sum\limits_{i=1}^n\left(b_i-a_i\right)^2}\right)
$$
According to symmetry, we get the whole inequality

## 3. McDiarmid's Inequality
___
Let $A$ be a measurable set. Assume $\varphi: A^N\to \mathbb{R}$ is a multivariate measurable function with bounded differences conditions
$$
\sup\limits_{z_1,\cdots, z_n, z_i^{\prime} \in A}|\varphi(z_1, z_2,\cdots, z_n)-\varphi(z_1, \cdots, z_{i-1}, z_i^{\prime}, z_{i+1}, \cdots, z_n)|\le c_i
$$

Let $Z_1, Z_2, \cdots, Z_n$ be independent random variables with values in the set $A$, then for all $t>0$, we have
$$
\mathbb{P}\left(|\varphi(Z_1, Z_2,\cdots, Z_n) - \mathbb{E}\varphi(Z_1, Z_2, \cdots, Z_n)|\ge t\right) \le 2\exp\left(-\dfrac{2t^2}{\sum\limits_{i=1}^n c_i^2}\right)
$$
___
##### Proof: 
First, it's easy to see that $\varphi$ is bounded by $\sum\limits_{i=1}^n c_i$. Define the Doob martingale $\left\{Z_i\right\}$ as
$$
\begin{gathered}
Z_i:=\mathbb{E}\left[\varphi\left(X_1, X_2, \cdots, X_n\right) \mid \mathcal{F}_i\right] \\
Z_0=\mathbb{E} \varphi\left(X_1, X_2, \cdots, X_n\right), \quad Z_n=\varphi\left(X_1, X_2, \cdots, X_n\right)
\end{gathered}
$$
Now we define the random variables for each $i$
$$
\begin{aligned}
U_i & :=\sup _{x \in \mathcal{X}_i} \mathbb{E}\left(Z_i \mid X_i=x\right)-Z_{i-1} \\
L_i & :=\inf _{x \in \mathcal{X}_i} \mathbb{E}\left(Z_i \mid X_i=x\right)-Z_{i-1}
\end{aligned}
$$
Since $X_1, X_2, \cdots, X_n$ are independent of each other. We know that
$$
\begin{aligned}
U_i-L_i & =\sup _{u \in \mathcal{X}_i} \mathbb{E}\left(Z_i \mid X_i=u\right)-\inf _{\ell \in \mathcal{X}_i} \mathbb{E}\left(Z_i \mid X_i=\ell\right) \\
& =\sup _{u \in \mathcal{X}_i, \ell \in \mathcal{X}_i} \mathbb{E}\left[\varphi\left(X_1, \cdots, u, \cdots, X_n\right)-\varphi\left(X_1, \cdots, l, \cdots, X_n\right) \mid X_1, \cdots, X_{i-1}\right] \\
& \leq \sup _{u \in \mathcal{X}_i, \ell \in \mathcal{X}_i} \mathbb{E}\left[c_i \mid X_1, \cdots, X_{i-1}\right] \\
& \leq c_i
\end{aligned}
$$
It means $\left|Z_i-Z_{i-1}\right| \leq c_i$. Then we have
$$
\mathbb{P}\left(\left|\varphi\left(X_1, X_2, \cdots, X_n\right)-\mathbb{E} \varphi\left(X_1, X_2, \cdots, X_n\right)\right| \geq t\right)=\mathbb{P}\left(\left|Z_n-Z_0\right| \geq t\right) \leq 2 \exp \left(-\frac{2 t^2}{\sum\limits_{i=1}^n c_i^2}\right)
$$
___

#### Hoeffding Inequality is Specific Case of McDiarmid's Inequality
When
$$
\varphi\left(z_1, z_2, \cdots, z_n\right)=\varphi_1\left(z_1\right)+\varphi_2\left(z_2\right)+\cdots+\varphi_n\left(z_n\right)
$$
Since $\left|\varphi_i\left(z_i\right)-\varphi_j\left(z_j\right)\right| \leq c_i$, we get Hoeffding Inequality.



## 4. Chernoff Bound on Tail Distribution
___
For $n$ independent random variables $X_1, X_2,\cdots, X_n$ with $X_i\in [0,1]$ and $\mathbb{E}X_i=p_i$, denote $p= \dfrac{1}{n}\sum\limits_{i=1}^{n}p_i$, then for $\forall \varepsilon>0$, we have
$$
\mathbb{P}\left(\frac{1}{n}\sum\limits_{i=1}^{n}X_i - p \ge \varepsilon\right) \le \exp\left[-n D_B^{(e)}(p+\varepsilon\| p)\right]
$$
Here, $D_B^{(e)}$ is the relative entropy of two Bernoulli random variables

___
##### Proof: 
Since exponent function is convex, by Jensen inequality, we have for $X\in [0,1]$
$$
\mathbb{E}\mathrm{e}^{tX} \le p \mathrm{e}^t+1-p
$$
Thus
$$
\mathbb{E}\left[\exp\left( t\sum\limits_{i=1}^{n} X_i  \right)\right]\le \prod\limits_{i=1}^{n}(1-p_i+p_i\mathrm{e}^t) 
$$
Since logarithmic function is concave, by Jensen inequality, we have
$$
\frac{1}{n}\sum\limits_{i=1}^{n}\ln(1-p_i+p_i\mathrm{e}^t) \le \ln(1-p+p\mathrm{e}^t) 
$$
Then we know that
$$
\mathbb{E}\left[\exp\left( t\sum\limits_{i=1}^{n} X_i  \right)\right]\le \prod\limits_{i=1}^{n}(1-p_i+p_i\mathrm{e}^t) \le (1-p+p\mathrm{e}^t)^n
$$
Using Chernoff Inequality, we know that
$$
\mathbb{P}\left(\frac{1}{n}\sum\limits_{i=1}^{n}X_i - p\ge \varepsilon \right)\le \inf_{t>0}\mathrm{e}^{-nt(p+\varepsilon)}(p\mathrm{e}^t+1-p)^n
$$
Minimize the right side, we can get when 
$$
\mathrm{e}^t = \dfrac{(p+\varepsilon)(1-p)}{(1-p-\varepsilon)p}
$$
The right side has minimum value
$$
\begin{aligned}
\mathrm{e}^{-nt(p+\varepsilon)}(p\mathrm{e}^t+1-p)^n &= \left[\dfrac{(1-p-\varepsilon)p}{(p+\varepsilon)(1-p)}\right]^{n(p+\varepsilon)}  \left[\dfrac{(p+\varepsilon)(1-p)}{(1-p-\varepsilon)}+1-p\right]^n \\ 
& = \exp\left[  n(1-p-\varepsilon)\log\left(\dfrac{1-p}{1-p-\varepsilon}\right) + n(p+\varepsilon) \log \left(\dfrac{p}{p+\varepsilon}\right)\right]\\
& = \exp\left[-n D_B^{(e)}(p+\varepsilon\| p)\right]
\end{aligned}
$$
Then we can get
$$
\mathbb{P}\left(\frac{1}{n}\sum\limits_{i=1}^{n}X_i - p \ge \varepsilon\right) \le \exp\left[-n D_B^{(e)}(p+\varepsilon\| p)\right]
$$
___
**Note**: 这个界要严格优于Hoeffding Inequality给出的界, 如果利用Hoeffding Inequality, 则
$$
\mathbb{P}\left(\frac{1}{n}\sum\limits_{i=1}^{n}X_i - p \ge \varepsilon\right)  \le \exp(-2n\varepsilon^2)
$$
可以证明
$$
2\varepsilon^2 \le D_B^{(e)}(p+\varepsilon\|p) \implies \exp(-2n\varepsilon^2) \geq \exp\left[-n D_B^{(e)}(p+\varepsilon\| p)\right]
$$
等号成立当且仅当$\varepsilon=0$. 这个界能严格优于Hoeffding Inequality的原因是其不仅利用了随机变量的有界性, 而且利用了随机变量的均值性质. 

