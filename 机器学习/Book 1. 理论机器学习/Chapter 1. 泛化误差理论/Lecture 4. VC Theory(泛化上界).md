## 1. VC维
### 1.1. Shattering
我们称假设集$\mathcal{H}$打散了(Shatter)集合$S = \{s_1, s_2, \cdots, s_m\}$, 如果
$$
\{(h(s_1), h(s_2), \cdots, h(s_m)) \mid h\in \mathcal{H}\} = \{0, 1\}^m
$$


### 1.2. VC维的定义
一个假设集$\mathcal{H}$的VC维是指它能完全打散的最大集合的大小
$$
\mathrm{VCdim}(\mathcal{H}) = \max \{m: \Pi_\mathcal{H}(m) = 2^m\}
$$
或者, 也可以用以下的形式定义VCdim$(\mathcal{H}) = d$
$$
\forall n\le d, \exists S = \{s_1, s_2, \cdots, s_n\}, \{(h(s_1), h(s_2), \cdots, h(s_n)) \mid h\in \mathcal{H}\} = \{0, 1\}^n
$$
$$
\forall n > d, \forall S = \{s_1, s_2, \cdots, s_n\}, \{(h(s_1), h(s_2), \cdots, h(s_n)) \mid h\in \mathcal{H}\} \subsetneqq \{0, 1\}^n
$$

### 1.3. Sauer引理
设$\mathcal{H}$是一个假设集, 且它的VC维VCdim$(\mathcal{H}) = d$, 则对于所有的$m\in \mathbb{N}$, 下面的不等式成立
$$
\Pi_\mathcal{H}(m) \le \sum\limits_{i=0}^{d} \binom{m}{i}
$$
当$m\le d$时, 有
$$
\Pi_\mathcal{H}(m) = 2^m
$$
___
##### Proof: 
对$m+d$进行归纳. 首先当$m=1, d=0$或$m=0, d=1$时, 上式显然成立. 假设上式对于$(m-1, d-1)$和$(m-1, d)$成立. 固定一个集合$S = \{x_1, x_2, \cdots, x_m\}$, 用$\mathcal{G}  = \mathcal{H}_s$表示限制在$S$上由$\mathcal{H}$诱导的概念集. 考虑集合$S^{\prime}= \{x_1, x_2, \cdots, x_{m-1}\}$, 用$\mathcal{G}  = \mathcal{H}_{s^{\prime}}$表示限制在$S^{\prime}$上由$\mathcal{H}$诱导的概念集. 我们定义$\mathcal{G}_2$为
$$
\mathcal{G}_2 = \{g^{\prime}\subseteq S^{\prime}\mid (g^{\prime}\in \mathcal{G}) \wedge (g^{\prime}\cup \{x_m\}\in \mathcal{G})\}
$$
根据$\mathcal{G}_1$和$\mathcal{G}_2$的定义, 我们有
$$
|\mathcal{G}| = |\mathcal{G}_1| + |\mathcal{G}_2|
$$
根据归纳假设, 可以得到
$$
|\mathcal{G}_1| \le \Pi_{\mathcal{G}_1} (m-1)\le \sum\limits_{i=0}^{d} \binom{m-1}{i}
$$
根据$\mathcal{G}_2$的定义, 可以得到VCdim$(\mathcal{G}_2) \le$ VCdim$(\mathcal{G}) - 1 = d - 1$. 因此
$$
|\mathcal{G}_2| \le \Pi_{\mathcal{G}_2} (m-1)\le \sum\limits_{i=0}^{d-1} \binom{m-1}{i}
$$
综上所述
$$
|\mathcal{G}| = |\mathcal{G}_1| + |\mathcal{G}_2| \le  \sum\limits_{i=0}^{d} \binom{m-1}{i}+ \sum\limits_{i=0}^{d-1} \binom{m-1}{i} = \sum\limits_{i=0}^{d} \binom{m}{i}
$$
#####
___
**推论**: 如果$\mathcal{H}$是一个假设集, 且它的VC维 VCdim$(\mathcal{H}) = d$, 则对于所有的$m\ge d$
$$
\Pi_\mathcal{H}(m)\le \left(\dfrac{\mathrm{e}m}{d}\right)^d= O(m^d)
$$

## 2. 关于VC维泛化界

### 2.1. 二分类问题关于VC维的泛化界
设$\mathcal{H}$是取值为$\{-1, +1\}$的假设集, 且它的VC维 VCdim$(\mathcal{H}) = d$, 则对于任意的$\delta>0$, 至少以$1-\delta$的概率, 满足
$$
R(h) \le \widehat{R}(h) + \sqrt{\dfrac{2d \log \dfrac{\mathrm{e}m}{d}}{m}} + \sqrt{\dfrac{\log \dfrac{1}{\delta}}{2m}} = \widehat{R}(h) + O\left(\sqrt{\dfrac{\log \dfrac{m}{d}}{\dfrac{m}{d}}}\right)
$$
___
##### Proof: 
利用[[Lecture 3. 生长函数#2.1. 二分类问题关于生长函数的泛化界]]和[[#1.3. Sauer引理]], 即得到结论成立. 
#####
___

### 2.2. 可实现情形下VC维的泛化界
如果一个假设$h$在样本$S\sim \mathcal{D}^m$上是一致的, 那么对于任意的$\varepsilon\ge \dfrac{8}{m}$, 有
$$
\mathbb{P}()
$$
___
##### Proof: 
设$H_s\subset H$是假设集中在样本集$S$上一致的假设构成的子集. 则
$$
\mathbb{P}\left(\hat{R}(h)\ge \dfrac{\varepsilon}{2}\right)
$$
#####
___