## 4. 泛化误差的下界
### 4.1 可实现(一致)情形下的下界
令$\mathcal{H}$是一个假设集, 且它的VC维$d>1$. 那么对于任意的学习算法$\mathcal{A}$, 存在一个$\mathcal{X}$上的分布$\mathcal{\mathcal{D}}$和一个目标函数$f\in \mathcal{H}$, 使得
$$
\operatorname*{\mathbb{P}}\limits_{S\in \mathcal{\mathcal{D}}^m} \left(R_{\mathcal{\mathcal{D}}}(h_s, f)> \dfrac{d-1}{32m} \right) \ge \dfrac{1}{100}
$$
___
##### Proof: 
令$X = \{x_0, x_1, \cdots, x_{d-1}\}\subset \mathcal{X}$是一个能被$\mathcal{H}$完全打散的集合. 对于任意的$\varepsilon>0$, 我们考虑
$$
\operatorname*{\mathbb{P}}\limits_{\mathcal{\mathcal{D}}}(x_0) = 1 - 8\varepsilon,\quad  \forall i \in [1, d-1], \operatorname*{\mathbb{P}}\limits_{\mathcal{\mathcal{D}}}(x_i) = \dfrac{8\varepsilon}{d-1}
$$
不失一般性, 我们假设学习算法$\mathcal{A}$对于$x_0$不会犯错. 对于一个样本集$S$, 我们令定义样本集组成的集合$\mathcal{S}$为
$$
\mathcal{S} = \left\{S: |S| = m\ \Big|\  |\mathrm{set}(S)- \{x_0\}|\le \dfrac{d-1}{2}\right\}
$$ 
现在, 固定一个样本集$S\subset \mathcal{S}$, 如果所有可能的假设$f\mapsto \{0,1\}$服从均匀分布, 那么
$$
\begin{aligned}
\operatorname*{\mathbb{E}}\limits_{f\sim \mathcal{U}}\left[R_{\mathcal{\mathcal{D}}}(h_s,f )\right] & = \sum\limits_{f}\sum\limits_{x\in X} \mathbb{I}(h(x)\neq f(x)) \mathbb{P}(x)\mathbb{P}(f) \\ 
 &\ge \sum\limits_{f}\sum\limits_{x\notin \mathrm{set}(S)} \mathbb{I}(h(x)\neq f(x)) \mathbb{P}(x)\mathbb{P}(f) \\
 & = \dfrac{1}{2}\sum\limits_{x\notin  \mathrm{set}(S)}^{} \mathbb{P}(x) \\ 
 & \ge \dfrac{1}{2} \dfrac{d-1}{2} \dfrac{8\varepsilon}{d-1}\\
 & = 2\varepsilon
\end{aligned}
$$
于是我们可以得到
$$
\operatorname*{\mathbb{E}}\limits_{S\in\mathcal{S}}\left[\operatorname*{\mathbb{E}}\limits_{f\sim \mathcal{U}}R_{\mathcal{\mathcal{D}}}(h_s, f)\right] \ge 2\varepsilon \Longrightarrow \operatorname*{\mathbb{E}}\limits_{f\sim \mathcal{U}}\left[\operatorname*{\mathbb{E}}\limits_{S\in\mathcal{S}}R_{\mathcal{\mathcal{D}}}(h_s, f)\right] \ge 2\varepsilon
$$
这意味着, 存在$f_0\in \mathcal{H}$使得$\operatorname*{\mathbb{E}}\limits_{S\in \mathcal{S}}R_{\mathcal{\mathcal{D}}}(h_s, f)\ge 2\varepsilon$. 将期望分解为两部分
$$
\operatorname*{\mathbb{E}}\limits_{S\in \mathcal{S}}R_{\mathcal{\mathcal{D}}}(h_s, f_0) = \sum\limits_{S: R_{\mathcal{\mathcal{D}}}(h_s, f_0) \ge \varepsilon}^{} R_{\mathcal{\mathcal{D}}}(h_s, f_0) \mathbb{P}\left(R_{\mathcal{\mathcal{D}}}(h_s, f_0)\right) + \sum\limits_{S: R_{\mathcal{\mathcal{D}}}(h_s, f_0) < \varepsilon}^{} R_{\mathcal{\mathcal{D}}}(h_s, f_0) \mathbb{P}\left(R_{\mathcal{\mathcal{D}}}(h_s, f_0)\right)
$$
因为我们假设了学习算法$\mathcal{A}$对$x_0$不会犯错, 所以$R_{\mathcal{\mathcal{D}}}(h_s, f_0) \le 8\varepsilon$. 于是
$$
\operatorname*{\mathbb{E}}\limits_{S\in \mathcal{S}}R_{\mathcal{\mathcal{D}}}(h_s, f_0) \le 8\varepsilon \operatorname*{\mathbb{P}}\limits_{S\in \mathcal{S}}\left[R_{\mathcal{\mathcal{D}}}(h_s, f_0)\ge \varepsilon\right] + \varepsilon \operatorname*{\mathbb{P}}\limits_{S\in \mathcal{S}}\left[R_{\mathcal{\mathcal{D}}}(h_s, f_0)\le  \varepsilon\right]
$$
这样, 我们就得到了
$$
\operatorname*{\mathbb{P}}\limits_{S\in \mathcal{S}}\left[R_{\mathcal{\mathcal{D}}}(h_s, f_0)\ge \varepsilon\right] \ge \dfrac{1}{7}
$$
在所有的样本集$S$上的概率下界为
$$
\operatorname*{\mathbb{P}}\limits_{S}\left[R_{\mathcal{\mathcal{D}}}(h_s, f_0)\ge \varepsilon\right] \ge \operatorname*{\mathbb{P}}\limits_{S\in \mathcal{S}}\left[R_{\mathcal{\mathcal{D}}}(h_s, f_0)\ge \varepsilon\right] \mathbb{P}(\mathcal{S}) \ge \dfrac{1}{7} \mathbb{P}(\mathcal{S})
$$
下面对$\mathbb{P}(\mathcal{S})$进行估计: 简单起见, 我们估计$\{x_1, x_2, \cdots, x_{d-1}\}$出现的次数$C_m$. 设$p= 8\varepsilon$. 利用[[../../概率论/Book 1. 初等概率论/Chapter 1. 概率不等式/Lecture 3. Bernstein's Type Inequality#3. Bernstein's Inequality (Variance Version)]]
$$
\mathbb{P}\left(\dfrac{1}{m}C_m - p\ge \gamma p \right) \le \exp\left( - \dfrac{m\gamma^2 p^2}{2p(1-p) + \dfrac{2}{3}\gamma p}\right)
$$
令$\gamma = 1, p =\dfrac{d-1}{4m}$, 也即$\varepsilon = \dfrac{d-1}{32m}$, 我们有
$$
\mathbb{P}\left(C_m \ge \dfrac{d-1}{2} \right) \le \exp\left( - \dfrac{mp}{2(1-p) + \dfrac{2}{3}}\right) \le e^{- \frac{d-1}{12}} \le 1 - 7\times 0.01
$$
于是
$$
\mathbb{P}(\mathcal{S})\ge 0.07\Longrightarrow \operatorname*{\mathbb{P}}\limits_{S}\left[R_{\mathcal{\mathcal{D}}}(h_s, f_0)\ge \varepsilon\right]\ge 0.01
$$
于是我们证明了
$$
\operatorname*{\mathbb{P}}\limits_{S\in \mathcal{\mathcal{D}}^m} \left(R_{\mathcal{\mathcal{D}}}(h_s, f)> \dfrac{d-1}{32m} \right) \ge \dfrac{1}{100}
$$
#####
___
**Note**: 
1. 上面的结论说明了, 对于任意的学习算法$\mathcal{A}$, 存在一个$\mathcal{X}$上坏的分布以及一个目标函数, 以某个常数概率由算法$A$返回的假设误差为$\Omega\left(\dfrac{d}{m}\right)$. 这进一步反映了VC维在Learning中的作用.
2. 这个结果也说明了当VC维是无穷时, PAC学习在可实现(一致)的情况下是不可能的. 
___

### 4.2 不可实现(不一致)情况下的下界
令$\mathcal{H}$是一个假设集, 且它的VC维$d>1$. 那么对于任意的学习算法$\mathcal{A}$, 存在一个$\mathcal{X}\times \{0, 1\}$上的分布$\mathcal{\mathcal{D}}$使得
$$
\operatorname*{\mathbb{P}}\limits_{S\in \mathcal{\mathcal{D}}^m} \left(R_{\mathcal{\mathcal{D}}}(h_s) - \inf\limits_{h\in \mathcal{H}}R_{\mathcal{\mathcal{D}}}(h) > \sqrt{\dfrac{d}{320m}} \right) \ge \dfrac{1}{64}
$$
___
##### Proof: 
令$X = \{x_1, x_1, \cdots, x_{d}\}\subset \mathcal{X}$是一个能被$\mathcal{H}$完全打散的集合. 对于任意的$\alpha\in [0, 1]$以及任意的向量$\boldsymbol{\sigma}=(\sigma_1, \sigma_2, \cdots, \sigma_d)^{\top}\in \{-1, +1\}^d$, 我们定义一个在$\mathcal{X}\times \{0, 1\}$上的分布$\mathcal{D}_{\boldsymbol{\sigma}}$满足
$$
 \operatorname*{\mathbb{P}}\limits_{\mathcal{D}_{\boldsymbol{\sigma}}}(x_i, 1) =\dfrac{1}{d}\left(\dfrac{1}{2}+ \dfrac{\sigma_i \alpha}{2}\right), \quad \forall i \in [1, d]
$$
考虑贝叶斯分类器$h^{*}_{\mathcal{D}_{\boldsymbol{\sigma}}}$定义为
$$
h_{\mathcal{D}_\sigma}^*\left(x_i\right)=\operatorname*{argmax}\limits_{y \in\{0,1\}}  \mathbb{P}\left[y \mid x_i\right]= \mathbb{I}_{\sigma_i>0}
$$
因为$X$可以被完全打散, 因此$h_{\mathcal{D}_\sigma}^*\in \mathcal{H}$. 对于所有的$h\in \mathcal{H}$, 我们有
$$
R_{\mathcal{D}_{\boldsymbol{\sigma}}}(h)-R_{\mathcal{D}_{\boldsymbol{\sigma}}}\left(h_{\mathcal{D}_{\boldsymbol{\sigma}}}^*\right)=\frac{1}{d} \sum_{x \in X}\left(\frac{\alpha}{2}+\frac{\alpha}{2}\right) \mathbb{I}_{h(x) \neq h_{\mathcal{D}_{\boldsymbol{\sigma}}}^*(x)}=\frac{\alpha}{d} \sum_{x \in X} \mathbb{I}_{h(x) \neq h_{\mathcal{D}_{\boldsymbol{\sigma}}}^*(x)}
$$
现在, 用$h_s$表示学习算法接收到一个采样自$\mathcal{D}_{\boldsymbol{\sigma}}$的带标签的样本集$S$而返回的假设. 用$|S|_x$表示一个点$x$出现在$S$中的次数. 用$\mathcal{U}$表示在$\{-1, +1\}^d$上的均匀分布. 
$$
\begin{aligned}
 \underset{\substack{\boldsymbol{\sigma} \sim \mathcal{U} \\ S\sim \mathcal{D}^m_{\boldsymbol{\sigma}}}}{\mathbb{E}}\left[\frac{1}{\alpha}\left[R_{\mathcal{D}_{\boldsymbol{\sigma}}}\left(h_S\right)-R_{\mathcal{D}_{\boldsymbol{\sigma}}}\left(h_{\mathcal{D}_{\boldsymbol{\sigma}}}^*\right)\right]\right]  &=\frac{1}{d} \sum_{x \in X} \underset{\substack{\boldsymbol{\sigma} \sim \mathcal{U} \\ S \sim \mathcal{D}^m_{\boldsymbol{\sigma}}}}{\mathbb{E}}\left[\mathbb{I}_{h_s(x)\neq h_{\mathcal{D}_{\boldsymbol{\sigma}}}^*(x)}\right] \\
& =\frac{1}{d} \sum_{x \in X} \underset{\boldsymbol{\sigma}\sim \mathcal{U}}{\mathbb{E}}\left[\underset{S \sim \mathcal{D}_{\boldsymbol{\sigma}}^m}{\mathbb{P}}\left[h_S(x) \neq h_{\mathcal{D}_{\boldsymbol{\sigma}}}^*(x)\right]\right] \\
& =\frac{1}{d} \sum_{x \in X} \sum_{n=0}^m \underset{\boldsymbol{\sigma} \sim \mathcal{U}}{\mathbb{E}}\underset{S \sim \mathcal{D}_{\boldsymbol{\sigma}}^m}{\mathbb{P}}\left[h_S(x) \neq h_{\mathcal{D}_{\boldsymbol{\sigma}}}^*(x)\ \big|\ |S|_x=n\right] \mathbb{P}\left[|S|_x=n\right]\\
& \geq \frac{1}{d} \sum_{x \in X} \sum_{n=0}^m \Phi(n+1, \alpha) \mathbb{P}\left[|S|_x=n\right] \\
& \geq \frac{1}{d} \sum_{x \in \bar{x}} \Phi\left(\dfrac{m}{d+1}, \alpha\right) \\
& =\Phi\left(\dfrac{m}{d+1}, \alpha\right) \\
&
\end{aligned}
$$
这里, $\Phi(m, \varepsilon) = \dfrac{1}{4}\left(1-\sqrt{1-\exp \left(-\dfrac{m \epsilon^2}{1-\epsilon^2}\right)}\right)$, 第一个不等式成立是由下面的引理[[#5.1 Lemma 1]]保证的. 
于是一定存在某个$\boldsymbol{\sigma}\in \{-1, +1\}^d$使得
$$
\underset{S \sim \mathcal{D}_\sigma^m}{\mathbb{E}}\left[\frac{1}{\alpha}\left[R_{\mathcal{D}_\sigma}\left(h_S\right)-R_{\mathcal{D}_\sigma}\left(h_{\mathcal{D}_\sigma}^*\right)\right]\right]>\Phi\left(\dfrac{m}{d+1}, \alpha\right)
$$
根据引理[[#5.2. Lemma2]], 我们有
$$
\underset{S \sim \mathcal{D}_\sigma^m}{\mathbb{P}}\left[\frac{1}{\alpha}\left[R_{\mathcal{D}_\sigma}\left(h_S\right)-R_{\mathcal{D}_\sigma}\left(h_{\mathcal{D}_\sigma}^*\right)\right]>\gamma u\right]>(1-\gamma) u, \quad u = \Phi\left(\dfrac{m}{d+1}, \alpha\right)
$$
通过选择合适的$\delta$和$\varepsilon$, 使得$\delta\le (1-\gamma) u$和$\varepsilon \le  \gamma\alpha u$, 则
$$
\underset{S \sim \mathcal{D}_\sigma^m}{\mathbb{P}}\left[R_{\mathcal{D}_\sigma}\left(h_S\right)-R_{\mathcal{D}_\sigma}\left(h_{\mathcal{D}_\sigma}^*\right)>\varepsilon\right]>\delta
$$
设$\gamma = 1 - 8\delta, \alpha = \dfrac{8\varepsilon}{1-8\delta}$. 此时可以得到
$$
\delta \le (1-\gamma) u \iff u\ge \dfrac{1}{8}, \quad \varepsilon \le \gamma\alpha u \iff u\ge \dfrac{1}{8}
$$
于是我们只需要保证$u\ge \dfrac{1}{8}$. 取$\delta = \dfrac{1}{64}$, 我们有
$$
u\ge \dfrac{1}{8} \iff \dfrac{m}{d}\le \left(\dfrac{49}{64^2\varepsilon^2} - 1\right) \log \dfrac{4}{3} - 1
$$
右边是关于$\varepsilon$的减函数, 而当$\varepsilon = \sqrt{\dfrac{d}{320m}}$时, 不等式成立. 于是定理得证
#####
___
**Note**: 上面的定理告诉我们, 对于任意的学习算法$\mathcal{A}$, 在不可实现的情况下, 存在一个$\mathcal{X}\times \{0, 1\}$上坏的分布, 以某一个常数概率由算法$\mathcal{A}$返回的假设误差为$\Omega\left(\sqrt{\dfrac{d}{m}}\right)$. 特别地, 当VC维无限时, 不可知PAC学习是不可能的. 

## 5. Appendix
### 5.1. Lemma 1
设$\alpha$是一个取值为$\{\alpha_-, \alpha_+\}$的均匀分布, 其中$\alpha_- = \dfrac{1}{2} - \dfrac{\varepsilon}{2}$且$\alpha_+ = \dfrac{1}{2} + \dfrac{\varepsilon}{2}$. 设$S$是一个包含$m\ge 1$个取值为$\{0,1 \}$的随机变量的样本集, 这些随机变量独立同分布于$\mathcal{D}_{\alpha}$, 满足$\operatorname*{\mathbb{P}}\limits_{\mathcal{D_{\alpha}}}(X = 1) = \alpha$. 令$h$是一个从$\mathcal{X}^m$映射到$\{\alpha_-, \alpha_+\}$的函数, 则
$$
\underset{\alpha}{\mathbb{E}}\left[\underset{S \sim \mathcal{D}_\alpha^m}{\mathbb{P}}[h(S) \neq \alpha]\right] \geq \Phi(2\lceil m / 2\rceil, \epsilon)
$$
其中, 对于所有的$m, \varepsilon$, $\Phi(m ,\varepsilon)=\dfrac{1}{4}\left(1-\sqrt{1-\exp\left(-\dfrac{m\varepsilon^2}{1-\varepsilon^2}\right)}\right)$
___
##### Proof:
运用贝叶斯法则, 其最优准则是
$$
h(x) = \begin{cases}
\alpha_{-}, &\quad \text{if the number of } 1 \text{ in } x \text{ is less than }\dfrac{m}{2} \\
\alpha_{+}, &\quad \text{if the number of } 1 \text{ in } x \text{ is greater than }\dfrac{m}{2} 
\end{cases}
$$
于是我们有
$$
\underset{\alpha}{\mathbb{E}}\left[\underset{S \sim \mathcal{D}_\alpha^m}{\mathbb{P}}[h(S) \neq \alpha]\right]
$$
利用[[../概率论/概率不等式/Lecture 5. Inequalities Based on Specific Distribution#1. Slud 不等式(二项分布尾界)]], 我们可以得到
#####
___
### 5.2. Lemma2
设$Z$是在$[0,1]$上取值的随机变量, 那么对于任意的$\gamma\in [0, 1)$, 有
$$
\mathbb{P}[z>\gamma] \geq \frac{\mathbb{E}[Z]-\gamma}{1-\gamma}>\mathbb{E}[Z]-\gamma
$$
___
##### Proof: 
由于$Z$是在$[0,1]$上取值的随机变量, 所以
$$
\begin{aligned}
\mathbb{E}[Z] & =\sum_{z \leq \gamma} \mathbb{P}[Z=z] z+\sum_{z>\gamma} \mathbb{P}[Z=z] z \\
& \leq \sum_{z \leq \gamma} \mathbb{P}[Z=z] \gamma+\sum_{z>\gamma} \mathbb{P}[Z=z] \\
& =\gamma \mathbb{P}[Z \leq \gamma]+\mathbb{P}[Z>\gamma] \\
& =\gamma(1-\mathbb{P}[Z>\gamma])+\mathbb{P}[Z>\gamma] \\
& =(1-\gamma) \mathbb{P}[Z>\gamma]+\gamma
\end{aligned}
$$
#####
___
