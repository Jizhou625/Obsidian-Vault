## 1. Hoeffding Lemma with Variance 
___
**Theorem:** Suppose that $|X| \leq c$ and $\mathbb{E} X=0$. For any $t>0$
$$
\mathbb{E} \mathrm{e}^{t X} \leq \exp \left(\frac{\mathrm{e}^{t c}-1-t c}{c^2} \sigma^2\right)
$$
where $\sigma^2=\operatorname{Var}(X)$

___
##### Proof: 
Using Taylor expansion, we have
$$
\mathbb{E} \mathrm{e}^{t X}=1+t^2 \sigma^2 \sum_{r=2}^{\infty} \frac{t^{r-2} \mathbb{E} X^r}{r ! \sigma^2}
$$
Let
$$
F=\sum_{r=2}^{\infty} \frac{t^{r-2} \mathbb{E} X^r}{r ! \sigma^2}
$$
we can get that
$$
\mathbb{E} \mathrm{e}^{t X} \leq 1+t^2 \sigma^2 F \leq \mathrm{e}^{t^2 \sigma^2 F}
$$
For $r \geq 2$, we have
$$
\mathbb{E} X^r=\mathbb{E} X^2 X^{r-2} \leq c^{r-2} \sigma^2
$$
Then, we can know that
$$
F \leq \frac{\mathrm{e}^{t c}-1-t c}{(t c)^2}
$$
Hence,
$$
\mathbb{E} \mathrm{e}^{t X} \leq \exp \left(\frac{\mathrm{e}^{t c}-1-t c}{c^2} \sigma^2\right)
$$
#####
___
##### 和Hoeffding Lemma的对比
和Hoeffding Lemma相比, 当 $t$ 非常小的时候
$$
\exp \left(\frac{\mathrm{e}^{t c}-1-t c}{c^2} \sigma^2\right) \approx \exp \left(\frac{t^2 \sigma^2}{2}\right)<\exp \left(\frac{t^2 c^2}{2}\right)
$$
当 $t$ 值比较大时, 该上界不如Hoeffding Lemma给出的上界
#####
___

## 2. Bernstein's Inequality
___
**Theorem:** Let $Z_1, \cdots, Z_n$ be centered independent random variables with values in space $\mathbb{R}$ satisfying for a positive constant $\kappa$,
$$
\sum_{i=1}^n \mathbb{E}\left|Z_i\right|^m \leq \frac{m !}{2} \nu_n^2 \kappa^{m-2}, \quad m=2,3, \cdots
$$
For arbitrary $t>0$, the following inequality (where $r>0$ ) is valid for the sum $H_n=Z_1+Z_2+\cdots+$ $Z_n$
$$
\mathbb{P}\left(\left|H_n\right| \geq r\right) \leq 2 \exp \left(-\frac{r^2}{2 \nu_n^2+2 \kappa r}\right)
$$
___
***Proof:*** According to symmetry, we only need to prove
$$
\mathbb{P}\left(H_n \geq r\right) \leq \exp \left(-\frac{r^2}{2 \nu_n^2+2 \kappa r}\right)
$$
Using [[Lecture 1. Basic Probability Inequalities#3. Chernoff Bound]], we have
$$
\mathbb{P}\left(H_n \geq r\right)\leq  \inf\limits_{t\ge 0}  \mathrm{e}^{-t r} \mathbb{E} \mathrm{e}^{t H_n}=\inf\limits_{t\ge 0} \mathrm{e}^{-t r} \prod_{i=1}^n \mathbb{E} \mathrm{e}^{t Z_i}
$$
Using Taylor expansion, we know that
$$
\mathbb{E} \mathrm{e}^{t Z_i}=1+t^2 \sum_{m=2}^{\infty} \frac{t^{m-2} \mathbb{E} Z_i^m}{m !} \le \exp\left\{t^2\sum_{m=2}^{\infty} \frac{t^{m-2} \mathbb{E} Z_i^m}{m !}\right\}
$$
Hence, we can get that
$$
\begin{aligned}
\mathrm{e}^{-t r} \prod_{i=1}^n \mathbb{E} \mathrm{e}^{t X_i} & \le \mathrm{e}^{-t r} \prod_{i=1}^n\exp\left\{t^2\sum_{m=2}^{\infty} \frac{t^{m-2} \mathbb{E} Z_i^m}{m !}\right\}\\
& = \mathrm{e}^{-t r} \exp\left\{t^2\sum_{m=2}^{\infty}  \frac{t^{m-2} }{m !}\sum\limits_{i=1}^{n}\mathbb{E} Z_i^m\right\} \\ 
&\le \mathrm{e}^{-t r} \exp\left\{t^2\sum_{m=2}^{\infty}  \frac{t^{m-2} }{m !}\frac{m !}{2} \nu_n^2 \kappa^{m-2}\right\}   \\ 
& = \exp \left(\frac{1}{2} t^2 \nu_n^2 \frac{1}{1-t \kappa}-t r\right)
\end{aligned}
$$
Let $t=\dfrac{r}{v_n^2+\kappa r}$. Then we know that
$$
\frac{1}{2} t^2 \nu_n^2 \frac{1}{1-t \kappa}-t r=\frac{1}{2} t^2 \nu_n^2 \frac{\nu_n^2+\kappa r}{\nu_n^2}-t r=-\frac{r^2}{2 \nu_n^2+2 \kappa r}
$$
As a result, we proved that
$$
\mathbb{P}\left(H_n \geq r\right) \leq \exp \left(-\frac{r^2}{2 \nu_n^2+2 \kappa r}\right)
$$
## 3. Bernstein's Inequality (Variance Version)
___
**Theorem:** If $\mathbb{P}\left(\left|X_i\right| \leq c\right)=1$ and $\mathbb{E} X_i=\mu$. Then, for any $\varepsilon>0$, we have
$$
\mathbb{P}\left(\left|\bar{X}_n-\mu\right|>\varepsilon\right) \leq 2 \exp \left(-\frac{n \varepsilon^2}{2 \sigma^2+\frac{2 c \varepsilon}{3}}\right)
$$
where $\sigma^2=\dfrac{1}{n} \sum\limits_{i=1}^n \operatorname{Var}\left(X_i\right)$
___
##### Proof:
Let $v_n^2=n \sigma^2$ and $\kappa=\dfrac{1}{3} c$. We can prove that
$$
\sum_{i=1}^n \mathbb{E}\left|X_i\right|^m \leq \frac{m !}{2} \nu_n^2 \kappa^{m-2}, \quad m=2,3, \cdots
$$
Then we can use Bernstein's Inequality to get that
$$
\mathbb{P}\left(n\left|\bar{X}_n - \mu\right| \geq r\right) \leq 2 \exp \left(-\frac{r^2}{2 \nu_n^2+2 \kappa r}\right)
$$
Let $\varepsilon=\dfrac{r}{n}$, we know that
$$
\mathbb{P}\left(\left|\bar{X}_n-\mu\right|>\varepsilon\right) \leq 2 \exp \left(-\frac{n^2 \varepsilon^2}{2 n \sigma^2+2 \frac{1}{3} c n \varepsilon}\right)=2 \exp \left(-\frac{n \varepsilon^2}{2 \sigma^2+\frac{2 c \varepsilon}{3}}\right)
$$
#####
___
## 4. Bennett's Inequality
**Theorem**: If $\mathbb{P}(|X_i|\le c) = 1$ and $\mathbb{E}X_i =\mu_i$. Let $\mu = \dfrac{1}{n}\sum\limits_{i=1}^{n}\mu_i$. Then, for any $\varepsilon>0$, we have
$$
\mathbb{P}\left(\left|\bar{X}_n-\mu\right|>\varepsilon\right) \leq 2 \exp \left(-\frac{n \sigma^2}{c^2}\theta\left(\dfrac{\varepsilon c}{\sigma^2}\right)\right)
$$
where $\sigma^2=\dfrac{1}{n} \sum\limits_{i=1}^n \operatorname{Var}\left(X_i\right)$ and $\theta(x) = (1+x)\log(1+x) - x$
___
##### Proof:
不失一般性, 我们假设 $c=1, \mu_i=0$. 否则可以进行scale和平移变换而不影响不等式成立的条件. 令$t = n\varepsilon, \nu = n\sigma^2$, 根据对称性, 我们只要证明
$$
\mathbb{P}\left(S_n>r\right) \leq  \exp \left( - \nu\theta\left(\dfrac{r}{\nu}\right)\right) = \exp \left\{r - (r+\nu)\log \dfrac{\nu+r}{\nu}\right\}
$$
使用 [[Lecture 1. Basic Probability Inequalities#3. Chernoff Bound]], 我们可以得到
$$
\mathbb{P}\left(S_n>r\right) \leq \inf\limits_{t\ge 0}  \mathrm{e}^{-t r} \mathbb{E} \mathrm{e}^{t S_n}
$$
考虑函数$\varphi(x) = \mathrm{e}^x - x - 1$, $g(x) = \dfrac{\varphi(x)}{x^2}$. 求导可得
$$
g^{\prime}(x) = \dfrac{(x-2)\mathrm{e}^x+x+2}{x^3} \ge 0
$$
于是我们有
$$
g(tX_i)\le g(t) \Longrightarrow \varphi(tX_i)\le X_i^2 \varphi(t), \quad t\ge 0
$$
因此我们有
$$
\mathbb{E}\left[\mathrm{e}^{tX_i} - tX_i - 1\right] \le (\mathrm{e}^{t} - t - 1)\mathbb{E}X_i^2 \Longrightarrow \mathbb{E}\mathrm{e}^{tX_i}\le \exp\left\{\varphi(t)\mathbb{E}X_i^2\right\}
$$
容易得到
$$
\mathbb{E} \mathrm{e}^{t S_n} \le \prod\limits_{i=1}^{n} \exp\left\{\varphi(t)\mathbb{E}X_i^2\right\}= \exp\left\{\varphi(t)\nu \right\}
$$
这意味着
$$
\mathbb{P}\left(S_n>t\right) \leq \inf\limits_{t\ge 0}  \exp\left\{\varphi(t)\nu - tr\right\}
$$
令$t = \log\dfrac{\nu+r}{\nu}$, 我们就得到了
$$
\mathbb{P}\left(S_n>t\right) \leq \exp \left\{r - (r+\nu)\log \dfrac{\nu+r}{\nu}\right\}
$$
#####
___