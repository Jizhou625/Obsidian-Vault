## 1. Slud 不等式(二项分布尾界)
设$\mathcal{B}(n, p)$为二项分布随机变量, $k$为整数, 且$p\le \dfrac{1}{4}, k\ge np$或$p\le  \dfrac{1}{2}, np\le k\le n(1-p)$, 则有如下不等式成立:
$$
\mathbb{P}\left(\mathcal{B}(n, p)\ge k\right) \ge \mathbb{P}\left(\mathcal{Z}\ge \dfrac{k-np}{\sqrt{np(1-p)}}\right)
$$
这里, $\mathcal{Z}$是标准正态分布. 
___
##### Proof: 
首先明确一些记号: 
$$
\begin{aligned}
b(k, n, p) &= \binom{n}{k}p^k(1-p)^{n-k} \\ 
B(k, n, p) &= \sum_{j=0}^k b(j, n, p) \\
\bar{B}(k, n, p) &= \sum_{j=k}^n b(j, n, p) \\
\end{aligned}
$$
于是我们只要证明
$$
\bar{B}(k, n, p) \ge 1 - \Phi\left(\dfrac{k-np}{\sqrt{np(1-p)}}\right)
$$
1. $p\le \dfrac{1}{4}, \ k\ge n(1-p)$. 对于固定的$n, k$, 
   $$
   \lim\limits_{p\to 0} \bar{B}(k, n, p) - 1 + \Phi\left(\dfrac{k-np}{\sqrt{np(1-p)}}\right)\to 0
   $$
   于是我们只要证明当$\dfrac{n-k}{n}\le p\le \dfrac{1}{4}$时, 其关于$p$的导数是非负的, 经过简单的计算, 我们只要证明 
   $$
   G(k, n, p) = \dfrac{b (k, n, p)}{1 - \dfrac{k-np}{2k(1-p)}} \dfrac{\sqrt{np(1-p)}
   }{\phi\left(\dfrac{k-np}{\sqrt{np(1-p)}}\right)} \ge 1
   $$


## 2. 正态分布的尾界
如果$\mathcal{Z}$为服从标准正态分布的随机变量, 则对于$u>0$, 有下式成立
$$
\mathbb{P}\left(\mathcal{Z}\ge u\right) \ge \dfrac{1}{2}\left(1 - \sqrt{1 - e^{-u^2}}\right)
$$
___
##### Proof: 
只要证明
$$
f(u) = \dfrac{1}{2}\sqrt{1 - e^{-u^2}} - \left(\Phi(u) - \dfrac{1}{2}\right) \ge 0
$$
求一阶导数可以得到
$$
f^{\prime}(u) = \dfrac{1}{2} \dfrac{ue^{-u^2}}{\sqrt{1-e^{-u^2}}} - \dfrac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}u^2} = \left(\dfrac{1}{2}\dfrac{u e^{-\frac{1}{2}u^2}}{\sqrt{1 - e^{-u^2}}} - \dfrac{1}{\sqrt{2\pi}}\right) e^{-\frac{1}{2}u^2}
$$
令$g(u) = \dfrac{ue^{-\frac{1}{2}u^2}}{\sqrt{1 - e^{-u^2}}}$, 求导可以得到
$$
\begin{aligned} 
g^{\prime}(u) &\sim (1-u^2)e^{-\frac{1}{2}u^2}\sqrt{1-e^{-u^2}} - \dfrac{ue^{-u^2}}{\sqrt{1 - e^{-u^2}}} u e^{-\frac{1}{2}u^2} \\ 
& \sim (1-u^2)(1 - e^{-u^2}) - u^2e^{-u^2} \\
& \sim (1 + \ln x)(1-x) + x\ln x , \quad x = e^{-u^2} \\ 
& = 1 - x + \ln x \\
& \le 0
\end{aligned}
$$
因此$f^{\prime}(u)$先大于0后小于0, 于是$f(u)$是先增再减的, 且$f(0) = 0, f(+\infty)=0$, 因此$f(u)\ge 0$. 这就证明了原来的结论. 
## Appendix
### Lemma 1
对任意的$0< k < n$, $\log G\left(k, n, \dfrac{k}{n}\right)\ge -\dfrac{1}{8\min \{k, n-k\}}$
___
##### Proof: 

$$
\log G\left(k, n, \dfrac{k}{n}\right) = \log \left[\binom{n}{k}\sqrt{2\pi}k^{k+\frac{1}{2}}(n-k)^{n-k+\frac{1}{2}}n^{-n-\frac{1}{2}}\right]
$$