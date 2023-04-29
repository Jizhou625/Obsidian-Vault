## 1. Rademacher复杂度
### 1.1. 经验Rademacher复杂度
令$\mathcal{G}$表示能够将$\mathcal{Z}$映射到$[a,b]$的某一函数族, 设$S = (z_1, z_2, \cdots, z_m)$为一个包含$\mathcal{Z}$中元素且有固定样本规模$m$的样本集, 则$\mathcal{G}$关于$S$的经验Rademacher复杂度定义为
$$
\widehat{\mathcal{R}_s}(\mathcal{G}) = \operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}} \left(\sup\limits_{g\in \mathcal{G}}\dfrac{1}{m}\sum\limits_{i=1}^{m}\sigma_ig(z_i) \right)
$$
其中$\boldsymbol{\sigma} = (\sigma_1, \sigma_2, \cdots, \sigma_m)^{\top}$, $\sigma_i$是在$\{-1, +1\}$上均匀取值的独立同分布的随机变量, 被称为Rademacher变量.
如果用$\boldsymbol{g}_s$表示函数$g$在样本集$S$上的取值, 即
$$
\boldsymbol{g}_s = (g(z_1), g(z_2), \cdots , g(z_m))^{\top}
$$
则经验Rademacher复杂度可以被写成
$$
\widehat{\mathfrak{R}_s}(\mathcal{G}) =  \operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}} \left(\sup\limits_{g\in \mathcal{G}}\dfrac{1}{m}\boldsymbol{\sigma}^{\top}\boldsymbol{g}_s \right)
$$



### 1.2. 对经验Rademacher复杂度的理解
1. $\boldsymbol{\sigma}^{\top}\boldsymbol{g}_s$这样的内积衡量了$\boldsymbol{g}_s$和随机噪声向量$\boldsymbol{\sigma}$的关联度. 因此, 经验Rademacher复杂度实际上衡量了函数族$\mathcal{G}$在样本集$S$上与随机噪声关联程度的期望. 
2. 经验Rademacher复杂度描述了函数族$\mathcal{G}$的丰富度: 更复杂的函数族$\mathcal{G}$可以产生更多的$\boldsymbol{g}_s$, 在平均意义下会更好地与随机噪声相关联.

### 1.3. Rademacher复杂度
令$\mathcal{\mathcal{D}}$表示样本分布, 对于任意整数$m\ge 1$, 函数族$\mathcal{G}$的Rademacher复杂度定义为所有规模为$m$, 依据分布$\mathcal{D}$得到的样本集的经验Rademacher复杂度的期望, 即
$$
\mathfrak{R}_m(\mathcal{G}) = \operatorname*{\mathbb{E}}\limits_{S\sim \mathcal{D}^m}\widehat{\mathfrak{R}_s}(\mathcal{G})
$$


## 2. Rademacher复杂度的泛化界
### 2.1. 损失函数的泛化界
设$\mathcal{G}$表示能够将$\mathcal{Z}$映射到$[0,1]$的某一函数族. 那么, 对于任意的$\delta >0$, 至少以$1-\delta$的概率, 使得下面的不等式成立
$$
\mathbb{E} g(z) \le \dfrac{1}{m} \sum\limits_{i=1}^{m} g(z_i) + 2\mathfrak{R}_m (\mathcal{G}) +\sqrt{\dfrac{\log \dfrac{1}{\delta}}{2m}}, \quad \forall g\in \mathcal{G}
$$
和
$$
\mathbb{E}g(z) \le \dfrac{1}{m} \sum\limits_{i=1}^{m} g(z_i) + 2\widehat{\mathfrak{R}}_m (\mathcal{G}) +3\sqrt{\dfrac{\log \dfrac{2}{\delta}}{2m}}, \quad \forall g\in \mathcal{G}
$$
___
##### Proof: 
对于任意的样本集$S=(z_1, z_2, \cdots, z_m)$和任意的$g\in \mathcal{G}$, 我们用$\widehat{\mathbb{E}}_s(g) = \dfrac{1}{m} \sum\limits_{i=1}^{m} g(z_i)$表示$g$在$S$上的平均经验期望. 定义
$$
\Phi(S) = \sup\limits_{g\in \mathcal{G}} \left[ \mathbb{E}(g) - \widehat{\mathbb{E}}_s(g) \right]
$$
设$S$和$S^{\prime}$为只有一个元素不同的两个集合, 即$z_m$在$S$中而$z_m^{\prime}$在$S^{\prime}$中. 我们又
$$
\Phi(S^{\prime}) - \Phi(S) \le \sup\limits_{g\in \mathcal{G}}\left[ \widehat{\mathbb{E}}_s(g)  - \widehat{\mathbb{E}}_{s^{\prime}}(g) \right] = \sup\limits_{g\in \mathcal{G}} \dfrac{g(z_m) - g(z^{\prime}_m)}{m} \le \dfrac{1}{m}
$$
于是可以得到
$$
|\Phi(S^{\prime}) - \Phi(S) | \le \dfrac{1}{m}
$$
利用[[../概率论/Book 1. 初等概率论/Chapter 1. 概率不等式/Lecture 2. Hoeffding Type Bounds#3. McDiarmid's Inequality]], 有
$$
\mathbb{P}\left(\Phi(S) - \operatorname*{\mathbb{E}}\limits_s\Phi(S)\ge t\right) \le \exp\left(-{2mt^2}\right)
$$
令右边为${\delta}$, 可以得到, 以至少$1-\delta$的概率, 下面的不等式成立
$$
\Phi(S) \le \operatorname*{\mathbb{E}}\limits_s\Phi(S) + \sqrt{\dfrac{\log \dfrac{1}{\delta}}{2m}}
$$
接下来约束右边的期望项
$$
\begin{aligned}
\operatorname*{\mathbb{E}}\limits_s\Phi(S) & = \operatorname*{\mathbb{E}}\limits_s\sup\limits_{g\in \mathcal{G}} \left[ \mathbb{E}(g) - \widehat{\mathbb{E}}_s(g) \right] \\ 
& =\operatorname*{\mathbb{E}}\limits_s \sup\limits_{g\in \mathcal{G}}  \operatorname*{\mathbb{E}}\limits_{s^{\prime}} \left[\widehat{\mathbb{E}}_{s^{\prime}}(g) - \widehat{\mathbb{E}}_{s}(g)\right] \\ 
& \le \operatorname*{\mathbb{E}}\limits_{s, s^{\prime}} \sup\limits_{g\in \mathcal{G}}  \operatorname*{\mathbb{E}}\limits_{s^{\prime}} \left[\dfrac{1}{m} \sum\limits_{i=1}^{m} g(z_i^{\prime}) - \dfrac{1}{m} \sum\limits_{i=1}^{m} g(z_i)\right] \\
& \le \operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}, s, s^{\prime}} \sup\limits_{g\in \mathcal{G}} \dfrac{1}{m}\sum\limits_{i=1}^{m} \sigma_i(g(z_i^{\prime}) - g(z_i)) \\ 
& \le 2\operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}, s} \sup\limits_{g\in \mathcal{G}} \dfrac{1}{m}\sum\limits_{i=1}^{m} \sigma_i g(z_i) \\
& = 2\mathfrak{R}_m(\mathcal{G})
\end{aligned}
$$
这就得到了第一个不等式. 而将$\delta$更改为$\dfrac{\delta}{2}$. 我们可以得到
$$
\mathfrak{R}_m(\mathcal{G}) \le \widehat{\mathfrak{R}}_s(\mathcal{G}) +\sqrt{\dfrac{\log \dfrac{2}{\delta}}{2m}}
$$
于是可以得到, 至少以$1-\delta$的概率保证
$$
\Phi(S) \le   2\widehat{\mathfrak{R}}_m(\mathcal{G}) +3\sqrt{\dfrac{\log \dfrac{2}{\delta}}{2m}}
$$
#####
___

### 2.2. 二分类问题关于Rademacher复杂度的泛化界
令$\mathcal{H}$为取值为$\{-1, +1\}$的某一函数族, 令$\mathcal{D}$为输入空间$\mathcal{X}$的分布, 那么, 对于规模为$m$, 分布为$\mathcal{D}$的某一样本集$S$和任意的$\delta>0$, 至少以概率$1-\delta$, 有
$$
R(h) \le \widehat{R}(h) + \mathfrak{R}_s(\mathcal{H}) +\sqrt{\dfrac{\log \dfrac{1}{\delta}}{2m}}, \quad \forall h\in \mathcal{H}
$$
$$
R(h) \le \widehat{R}(h) + \mathfrak{R}_s(\mathcal{H}) +3\sqrt{\dfrac{\log \dfrac{2}{\delta}}{2m}}, \quad \forall h\in \mathcal{H}
$$

**Note**: 第二个界是数据相关的, 因为经验Rademacher复杂度是依据特定样本集$S$的分布的. 因此, 该泛化界在我们能够计算出$\widehat{\mathfrak{R}}_s(\mathcal{H})$的情况下, 是更紧的泛化界.
___
##### Proof: 
根据[[Lecture 2. VC Theory#1.2. 损失函数的泛化界]]中的结论, 我们有
$$
R(h) \le \widehat{R}(h) + 2\mathfrak{R}_m(\mathcal{G}) +\sqrt{\dfrac{\log \dfrac{1}{\delta}}{2m}}, \quad \forall h\in \mathcal{H}
$$
$$
R(h) \le \widehat{R}(h) + 2\widehat{\mathfrak{R}}_m(\mathcal{G}) +3\sqrt{\dfrac{\log \dfrac{2}{\delta}}{2m}}, \quad \forall h\in \mathcal{H}
$$
于是只要证明
$$
2\widehat{\mathfrak{R}}_m(\mathcal{G}) = \widehat{\mathfrak{R}}_s(\mathcal{H})
$$
___

***Lemma***: 令$\mathcal{H}$为取值为$\{-1, +1\}$的某一函数族, $\mathcal{G}$为关于$\mathcal{H}$的$0-1$损失函数族: $\mathcal{G} = \{(x,y)\mapsto \mathbb{I}_{h(x)\neq y}: h\in \mathcal{H}\}$. 对于任意取值为$\mathcal{X}\times \{-1,+1\}$的样本集$S = \left((x_1, y_1), (x_2, y_2), \cdots, (x_m, y_m)\right)$, 令$S_{\mathcal{X}}$表示它在$\mathcal{X}$上的投影: $S_{\mathcal{X}} = (x_1, \cdots, x_m)$. 那么, 下面$\mathcal{G}$和$\mathcal{H}$的经验Rademacher复杂度满足下面的关系:
$$
\widehat{\mathfrak{R}}_s(\mathcal{G})  = \dfrac{1}{2}\widehat{\mathfrak{R}}_{s_{\mathcal{X}}}(\mathcal{H})
$$
___
对于任意取值为$\mathcal{X}\times \{-1, +1\}$的样本集$S = \left((x_1, y_1), (x_2, y_2), \cdots, (x_m, y_m)\right)$. 我们可以得到
$$
\begin{aligned}
\widehat{\mathfrak{R}}_s(\mathcal{G}) & =  \operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}} \left[\sup\limits_{h\in \mathcal{H}}\dfrac{1}{m}\sum\limits_{i=1}^{m} \sigma_i \mathbb{I}(h(x_i)\neq y_i) \right]\\
& = \operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}} \left[\sup\limits_{h\in \mathcal{H}}\dfrac{1}{m}\sum\limits_{i=1}^{m} \sigma_i \dfrac{1- y _i h(x_i)}{2} \right]\\
&= \dfrac{1}{2}\operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}} \left[\sup\limits_{h\in \mathcal{H}} \dfrac{1}{m} \sum\limits_{i=1}^{m}  - \sigma_i y_ih(x_i) \right] \\ 
&= \dfrac{1}{2}\operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}} \left[\sup\limits_{h\in \mathcal{H}} \dfrac{1}{m} \sum\limits_{i=1}^{m}  \sigma_i h(x_i) \right] \\ 
& = \dfrac{1}{2}\widehat{R}_{S_{\mathcal{X}}}(\mathcal{H})
\end{aligned}
$$
#####
___
## 3. 和Rademacher随机变量相关的不等式
### 3.1. Massart引理
设$A\subset \mathbb{R}^m$是一个有限集, 以及$r = \max\limits_{\boldsymbol{x}\in A} \|\boldsymbol{x}\|_2$, 那么有
$$
\operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}}\left[\dfrac{1}{m}\sup\limits_{\boldsymbol{x}\in A}\sum\limits_{i=1}^{m} \sigma_ix_i  \right] \le \dfrac{r\sqrt{2\log |A|}}{m}
$$
其中, $\sigma_i$是Rachmacher随机变量, $x_1, x_2, \cdots, x_m$是向量$\boldsymbol{x}$的元素.
___

##### Proof: 
对于任意的$t>0$, 运用Jensen不等式, 我们有
$$
\begin{aligned}
\exp\left(t\operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}}\left[\sup\limits_{\boldsymbol{x}\in A}\sum\limits_{i=1}^{m} \sigma_ix_i  \right]\right) & \le \operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}}\left[\exp\left(t\sup\limits_{\boldsymbol{x}\in A}\sum\limits_{i=1}^{m} \sigma_ix_i  \right)\right]\\
& \le  \sum\limits_{\boldsymbol{x}\in A}^{} \operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}}\left[\exp\left(t\sum\limits_{i=1}^{m} \sigma_ix_i  \right)\right]\\
& = \sum\limits_{\boldsymbol{x}\in A}^{}\prod\limits_{i=1}^{m}\operatorname*{\mathbb{E}}\limits_{\sigma_i}\exp(t\sigma_ix_i)\\
\end{aligned}
$$
因为$-|x_i|\le \sigma_i x_i \le |x_i|$, 使用[[../概率论/Book 1. 初等概率论/Chapter 1. 概率不等式/Lecture 2. Hoeffding Type Bounds#1. Hoeffding Lemma]], 我们有
$$
\begin{aligned}
\exp\left(t\operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}}\left[\sup\limits_{\boldsymbol{x}\in A}\sum\limits_{i=1}^{m} \sigma_ix_i  \right]\right) & \le \operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}}\left[\exp\left(t\sup\limits_{\boldsymbol{x}\in A}\sum\limits_{i=1}^{m} \sigma_ix_i  \right)\right]\\
& \le \sum\limits_{\boldsymbol{x}\in A}^{}\prod\limits_{i=1}^{m}\operatorname*{\mathbb{E}}\limits_{\sigma_i}\exp(t\sigma_ix_i)\\
& \le \sum\limits_{\boldsymbol{x}\in A}^{}\prod\limits_{i=1}^{m} \exp \left(\dfrac{t^2(2x_i)^2}{8}\right) \\ 
& = \sum\limits_{\boldsymbol{x}\in A}^{} \exp\left(\dfrac{t^2\|\boldsymbol{x}\|_2^2}{2}\right)\\
& \le |A|e^{\frac{t^2 r^2}{2}}
\end{aligned}
$$
于是我们可以得到
$$
\operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}}\left[\sup\limits_{\boldsymbol{x}\in A}\sum\limits_{i=1}^{m} \sigma_ix_i  \right] \le \dfrac{\log |A|}{t} + \dfrac{tr^2}{2}, \quad \forall t>0
$$
取$t = \dfrac{\sqrt{2\log |A|}}{r}$, 可以最小化右边的上界
$$
\operatorname*{\mathbb{E}}\limits_{\boldsymbol{\sigma}}\left[\sup\limits_{\boldsymbol{x}\in A}\sum\limits_{i=1}^{m} \sigma_ix_i  \right] \le r \sqrt{2\log |A|}
$$
#####
___
### 3.2. Khintchine-Kahane不等式
Let $(\mathbb{H},\|\cdot\|)$ be a normed vector space and let $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_m$ be $m \geq 1$ elements of $\mathbb{H}$. Let $\boldsymbol{\sigma}=\left(\sigma_1, \ldots, \sigma_m\right)^{\top}$, $\sigma_i$ are independent Rademacher variables. Then, the following inequalities hold:
$$
\frac{1}{2} \underset{\boldsymbol{\sigma}}{\mathbb{E}}\left[\left\|\sum_{i=1}^m \sigma_i \boldsymbol{x}_i\right\|^2\right] \leq\left(\underset{\boldsymbol{\sigma}}{\mathbb{E}}\left[\left\|\sum_{i=1}^m \sigma_i \boldsymbol{x}_i\right\|\right]\right)^2 \leq \underset{\boldsymbol{\sigma}}{\mathbb{E}}\left[\left\|\sum_{i=1}^m \sigma_i \boldsymbol{x}_i\right\|^2\right]
$$
___
##### Proof: 
右边的不等式可以由Jensen立刻得到. 下面证明左边的不等式. 
设$\boldsymbol{\alpha}= (\alpha_1, \alpha_2, \cdots, \alpha_m)\in \mathbb{R}^m$, 则有
$$
t^2 \prod_{i=1}^m\left(1+\dfrac{\alpha_i}{t}\right)=t^2 \sum_{\boldsymbol{\delta}\in\{0,1\}^m} \dfrac{\boldsymbol{\alpha}^{\boldsymbol{\delta}}}{t^{|\boldsymbol{\delta}|}}  =\sum_{\boldsymbol{\delta} \in\{0,1\}^m} t^{2-|\boldsymbol{\delta}|} \boldsymbol{\alpha}^{\boldsymbol{\delta}}
$$
两边对$t$求导, 并且令$t=1$, 可以得到
$$
2 \prod_{i=1}^m\left(1+\alpha_i\right)-\sum_{j=1}^m \alpha_j \prod_{i \neq j}\left(1+\alpha_i\right)=\sum_{\boldsymbol{\delta} \in\{0,1\}^m}(2-|\boldsymbol{\delta}|) \boldsymbol{\alpha}^{\boldsymbol{\delta}}
$$
设$s_{\boldsymbol{\sigma}} = \sum\limits_{i=1}^m \sigma_i\boldsymbol{x}_i$, 并且令$\alpha_i = \sigma_i\sigma_i^{\prime}$. 在上式两边同时乘以$\|s_{\boldsymbol{\sigma}}\|\|s_{\boldsymbol{\sigma}^{\prime}}\|$, 并且对所有的$\boldsymbol{\sigma}, \boldsymbol{\sigma}^{\prime}\in \{-1,+1\}^{m}$求和, 可以得到
$$
\begin{aligned}
& \sum_{\boldsymbol{\sigma}, \boldsymbol{\sigma}^{\prime} \in\{-1,+1\}^m}\left(2 \prod_{i=1}^m\left(1+\sigma_i \sigma_i^{\prime}\right)-\sum_{j=1}^m \sigma_j \sigma_j^{\prime} \prod_{i \neq j}\left(1+\sigma_i \sigma_i^{\prime}\right)\right) \|s_{\boldsymbol{\sigma}}\|\|s_{\boldsymbol{\sigma}^{\prime}}\| \\
=&\sum_{\boldsymbol{\sigma}, \boldsymbol{\sigma}^{\prime} \in\{-1,+1\}^m} \sum_{\boldsymbol{\delta} \in\{0,1\}^m}(2-|\boldsymbol{\delta}|) \boldsymbol{\sigma}^{\boldsymbol{\delta}} \boldsymbol{\sigma}^{\prime \boldsymbol{\delta}} \|s_{\boldsymbol{\sigma}}\|\|s_{\boldsymbol{\sigma}^{\prime}}\|\\
=&\sum_{\boldsymbol{\delta} \in\{0,1\}^m}(2-|\boldsymbol{\delta}|) \sum_{\boldsymbol{\sigma}, \boldsymbol{\sigma}^{\prime} \in\{-1,+1\}^m} \boldsymbol{\sigma}^{\boldsymbol{\delta}} \boldsymbol{\sigma}^{\prime \boldsymbol{\delta}} \|s_{\boldsymbol{\sigma}}\|\|s_{\boldsymbol{\sigma}^{\prime}}\| \\
=&\sum_{\boldsymbol{\delta} \in\{0,1\}^m}(2-|\boldsymbol{\delta}|)\left(\sum_{\boldsymbol{\sigma} \in\{-1,+1\}^m} \boldsymbol{\sigma}^{\boldsymbol{\delta}} \|s_{\boldsymbol{\sigma}}\|\right)^2
\end{aligned}
$$
当$|\boldsymbol{\delta}|\ge 2$时, 右边的项都是非正的. 而当$\|\boldsymbol{\delta}\|=1$时, 因为$\|s_{\boldsymbol{\sigma}}\| = \|s_{\boldsymbol{-\sigma}}\|$. 我们有
$$
\sum_{\boldsymbol{\sigma} \in\{-1,+1\}^m} \boldsymbol{\sigma} ^{\boldsymbol{\delta}} \|s_{\boldsymbol{\sigma}}\|=0 
$$
于是, 右边的项被$\boldsymbol{\delta} = 0$限制, 即
$$
\sum_{\boldsymbol{\sigma}, \boldsymbol{\sigma}^{\prime} \in\{-1,+1\}^m}\left(2 \prod_{i=1}^m\left(1+\sigma_i \sigma_i^{\prime}\right)-\sum_{j=1}^m \sigma_j \sigma_j^{\prime} \prod_{i \neq j}\left(1+\sigma_i \sigma_i^{\prime}\right)\right) \|s_{\boldsymbol{\sigma}}\|\|s_{\boldsymbol{\sigma}^{\prime}}\|\le  2\left(\sum\limits_{\boldsymbol{\sigma}\in \{-1, +1\}^m}^{} \|s_{\boldsymbol{\sigma}}\|\right)^2
$$
重写不等式左边
$$
\begin{aligned}
& \sum_{\boldsymbol{\sigma}, \boldsymbol{\sigma}^{\prime} \in\{-1,+1\}^m}\left(2 \prod_{i=1}^m\left(1+\sigma_i \sigma_i^{\prime}\right)-\sum_{j=1}^m \sigma_j \sigma_j^{\prime} \prod_{i \neq j}\left(1+\sigma_i \sigma_i^{\prime}\right)\right) \|s_{\boldsymbol{\sigma}}\|\|s_{\boldsymbol{\sigma}^{\prime}}\| \\
=& \sum_{\boldsymbol{\sigma}\in\{-1,+1\}^m}\left(2^{m+1}-m 2^{m-1}\right) \|s_{\boldsymbol{\sigma}}\|^2 + 2^{m-1}\sum_{\substack{\boldsymbol{\sigma} \in\{-1,+1\}^m \\ \boldsymbol{\sigma}^{\prime} \in B(\boldsymbol{\sigma}, 1)}} \|s_{\boldsymbol{\sigma}}\|\|s_{\boldsymbol{\sigma}^{\prime}}\| \\ 
=& 2^m \sum_{\boldsymbol{\sigma} \in\{-1,+1\}^m}\|s_{\boldsymbol{\sigma}}\|^2+2^{m-1} \sum_{\boldsymbol{\sigma} \in\{-1,+1\}^m} \|s_{\boldsymbol{\sigma}}\|\left(\sum_{\boldsymbol{\sigma}^{\prime} \in B(\boldsymbol{\sigma}, 1)} \|s_{\boldsymbol{\sigma}^{\prime}}\| -(m-2) \|s_{\boldsymbol{\sigma}}\|^2\right)
\end{aligned}
$$
这里, $B(\boldsymbol{\sigma}, 1)$代表与$\boldsymbol{\sigma}$的Hamming距离为$1$的所有$\boldsymbol{\sigma}^{\prime}$的集合. 于是
$$
\sum_{\boldsymbol{\sigma}^{\prime} \in B(\boldsymbol{\boldsymbol{\sigma}}, 1)} s_{\boldsymbol{\sigma}}-s_{\boldsymbol{\sigma}^{\prime}}=2 s_{\boldsymbol{\sigma}}
$$
这样, 我们有
$$
\begin{aligned}
 (m-2) \|s_{\boldsymbol{\sigma}}\|&=\left\|m s_{\boldsymbol{\sigma}}\right\|-\left\|2 s_{\boldsymbol{\sigma}}\right\| \\ 
 &=\left\|\sum_{\boldsymbol{\sigma}^{\prime} \in B(\boldsymbol{\sigma}, 1)} s_{\boldsymbol{\sigma}}\right\|-\left\|\sum_{\boldsymbol{\sigma}^{\prime} \in B(\boldsymbol{\sigma}, 1)} s_{\boldsymbol{\sigma}}-s_{\boldsymbol{\sigma}^{\prime}}\right\| \\
& \leq\left\|\sum_{\boldsymbol{\sigma}^{\prime} \in B(\boldsymbol{\sigma}, 1)} s_{\boldsymbol{\sigma}^{\prime}}\right\|\\ 
& \leq \sum_{\boldsymbol{\sigma}^{\prime} \in B(\boldsymbol{\sigma}, 1)} \|s_{\boldsymbol{\sigma}^{\prime}} \| \\
&
\end{aligned}
$$
于是我们有
$$
2^m \sum_{\boldsymbol{\sigma} \in\{-1,+1\}^m}\|s_{\boldsymbol{\sigma}}\|^2 \le 2\left(\sum\limits_{\boldsymbol{\sigma}\in \{-1, +1\}^m}^{} \|s_{\boldsymbol{\sigma}}\|\right)^2
$$
这就完成了证明. 当norm为quadratic norm时, 我们有
$$
\frac{1}{2} \sum_{i=1}^m\left\|\boldsymbol{x}_i\right\|_2^2 \leq\left(\underset{\boldsymbol{\sigma}}{\mathbb{E}}\left[\left\|\sum_{i=1}^m \sigma_i \boldsymbol{x}_i\right\|_2\right]\right)^2 \leq \sum_{i=1}^m\left\|\boldsymbol{x}_i\right\|_2^2
$$
#####
___