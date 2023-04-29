## 1. 生长函数
### 1.1. 生长函数的定义
假设集$\mathcal{H}$的生长函数$\Pi_\mathcal{H}: \mathbb{N}\to \mathbb{N}$, 定义为
$$
\forall m \in \mathbb{N}, \Pi_\mathcal{H}(m) = \max\limits_{\{x_1, x_2, \cdots, x_m\}\subset X} |\{(h(x_1), h(x_2), \cdots, h(x_m)): h\in \mathcal{H} \}|
$$
这一度量并不依赖于样本分布, 这是一个纯粹的组合测量概念. 



### 1.2. Rademacher复杂度的生长函数界
令$\mathcal{G}$为取值为$\{-1, +1\}$的某一函数族, 则下式成立
$$
\mathfrak{R}_m(\mathcal{G}) \le \sqrt{\dfrac{2\log \Pi_\mathcal{G}(m)}{m}}
$$
___
##### Proof: 
对于一个固定的样本集, 我们用$\mathcal{G}_s = \left\{(g(x_1), \cdots, g(x_m))^{\top}\mid g\in \mathcal{G}\right\}$表示定义在该样本集上的函数值向量的集合. 利用[[Lecture 2.1. VC Theory(Rademacher复杂度)#3.1. Massart引理]], 我们有
$$
\mathfrak{R}_m(\mathcal{G}) = \operatorname*{\mathbb{E}}\limits_s\left[\operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}}\left[\sup\limits_{\boldsymbol{u}\in \mathcal{G}_s} \dfrac{1}{m} \sum\limits_{i=1}^{m}  \sigma_i u_i \right]\right] \le \operatorname*{\mathbb{E}}\limits_s\left[\dfrac{\sqrt{m}\sqrt{2\log |\mathcal{G}_s|}}{m}\right]
$$
根据定义可以得到
$$
\mathfrak{R}_m(\mathcal{G}) \le \sqrt{\dfrac{2\log \Pi_\mathcal{G}(m)}{m}}
$$

## 2. 生长函数的泛化界
### 2.1. 二分类问题关于生长函数的泛化界
设$\mathcal{H}$是取值为$\{-1, +1\}$的假设集, 则对于任意的$\delta>0$, 至少以$1-\delta$的概率, 满足
$$
R(h) \le \widehat{R}(h) + \sqrt{\dfrac{2\log \Pi_{\mathcal{H}}(m)}{m}} + \sqrt{\dfrac{\log \dfrac{1}{\delta}}{2m}}
$$
生长函数的界也可以直接获得
$$
\mathbb{P}\left[\left|R(h)-\widehat{R}_S(h)\right|>\varepsilon\right] \leq 8 \Pi_{\mathcal{H}}(2 m) \exp \left(-\frac{m \varepsilon^2}{8}\right)
$$
___
##### Proof: 
我们使用Double sample trick. 定义$\phi_f(\mathcal{Z}) = \begin{cases}+1,\quad & y=f(x)  \\ -1,  &y\neq f(x)\end{cases}$, 这里$\mathcal{Z} = (x, y)$. 则
$$
\begin{aligned}
\mathbb{P}\left(\sup\limits_{f\in \mathcal{F}}\dfrac{1}{n}\sum\limits_{i=1}^{n} \phi(\mathcal{Z}_i) -\mathbb{E}\phi(\mathcal{Z}) \ge \varepsilon  \right) &\le 2\mathbb{P}\left(\sup\limits_{\phi}\left|\dfrac{1}{n}\sum\limits_{i=1}^{n} \phi(\mathcal{Z}_i) - \dfrac{1}{n}\sum\limits_{i=n+1}^{2n} \phi(\mathcal{Z}_i)\right|\ge {\varepsilon}  \right)\\
& = 2\operatorname*{\mathbb{E}}\limits_{\{z_1, \cdots, z_{2n}\}} \operatorname*{\mathbb{P}}\limits_{\sigma \in S_{2n}}\left(\sup\limits_{\phi}\left|\dfrac{1}{n}\sum\limits_{i=1}^{n} \phi(\mathcal{Z}_{\sigma_i}) - \dfrac{1}{n}\sum\limits_{i=n+1}^{2n} \phi(\mathcal{Z}_{\sigma_i})\right|\ge {\varepsilon}  \right) \\ 
& \le 2\operatorname*{\mathbb{E}}\limits_{\{z_1, \cdots, z_{2n}\}} \Pi_{\Phi}(2n) \operatorname*{\mathbb{P}}\limits_{\sigma \in S_{2n}}\left(\left|\dfrac{1}{n}\sum\limits_{i=1}^{n} \phi(\mathcal{Z}_{\sigma_i}) - \dfrac{1}{n}\sum\limits_{i=n+1}^{2n} \phi(\mathcal{Z}_{\sigma_i})\right|\ge {\varepsilon} \right) \\
& \le 4\operatorname*{\mathbb{E}}\limits_{\{z_1, \cdots, z_{2n}\}} \Pi_{\Phi}(2n) \operatorname*{\mathbb{P}}\limits_{\sigma \in S_{2n}}\left(\left|\dfrac{1}{n}\sum\limits_{i=1}^{n} \phi(\mathcal{Z}_{\sigma_i}) - \mathbb{E}\phi(\mathcal{Z})\right|\ge \dfrac{\varepsilon}{2} \right)\\
& \le 8\Pi_{\Phi}(2n) \mathrm{e}^{-\frac{1}{8}n\varepsilon^2} , \quad n\ge \dfrac{\ln 2}{\varepsilon^2}
\end{aligned}
$$
其中, 第一行的不等式和第四行的不等式可以由下面的引理[[#2.2 Double Sample Trick]]给出, 随着$n$的增大, 常数可以改进为$4$.

### 2.2 Double Sample Trick
Let $x_1, x_2, \cdots, x_{2n}$ be i.i.d. samples from $\mathcal{X}$. Let $\nu_1 = \dfrac{1}{n}\sum\limits_{i=1}^{n}x_i$ , $\nu_2 = \dfrac{1}{n} \sum\limits_{i=n+1}^{2n} x_i$ and $p = \mathbb{E}X$. Then, when $n \ge \dfrac{\ln 2 }{\varepsilon^2}$
$$
\dfrac{1}{2}\mathbb{P}(|\nu_1 - p|\ge 2\varepsilon) \le \mathbb{P}(|\nu_1 - \nu_2|\ge \varepsilon) \le 2\mathbb{P}(|\nu_1 - p|\ge \dfrac{1}{2}\varepsilon)
$$
___
##### Proof: 
因为$|\nu_1-\nu_2|\ge\varepsilon \Longrightarrow |\nu_1 - p|\ge \dfrac{\varepsilon}{2} \cup |\nu_2 - p|\ge \dfrac{\varepsilon}{2}$. 所以
$$
\mathbb{P}(|\nu_1 - \nu_2|\ge \varepsilon) \le \mathbb{P}\left(|\nu_1 - p|\ge \dfrac{1}{2}\varepsilon\right) + \mathbb{P}\left(|\nu_2 - p|\ge \dfrac{1}{2}\varepsilon\right) = 2\mathbb{P}\left(|\nu_1 - p|\ge \dfrac{1}{2}\varepsilon\right)
$$ 
因为$|\nu_1 - p|\ge 2\varepsilon \cap |\nu_2 - p|\le\varepsilon \Longrightarrow |\nu_1 - \nu_2|\ge \varepsilon$
$$
\mathbb{P}(|\nu_1 - p|\ge 2\varepsilon) \cdot \mathbb{P}(|\nu_2-p|\le \varepsilon) \le  \mathbb{P}(|\nu_1-\nu_2|\ge \varepsilon)
$$
由于$n\ge \dfrac{\ln 2}{\varepsilon^2}$, 所以 $\mathbb{P}(|\nu_2-p|\le \varepsilon) \ge \dfrac{1}{2}$. 因此我们有
$$
\dfrac{1}{2}\mathbb{P}(|\nu_1 - p|\ge 2\varepsilon) \le \mathbb{P}(|\nu_1 - \nu_2|\ge 2\varepsilon) \le 2\mathbb{P}(|\nu_1 - p|\ge \dfrac{1}{2}\varepsilon)
$$
