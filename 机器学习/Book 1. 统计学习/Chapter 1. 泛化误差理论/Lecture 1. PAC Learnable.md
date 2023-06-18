## 1. 基本概念
### 1.1. 泛化误差
#### 1.1.1. 确定性问题的泛化误差
给定一个假设 $h\in \mathcal{H}$, 一个目标概念 $c(x)$ 和一个定义在$\mathcal{X}$上的hidden distribution $\mathcal{D}$, 泛化误差 (generalization risk) 定义为
$$
R(h) = \operatorname*{\mathbb{P}}\limits_{x\sim \mathcal{D}}(h(x)\neq c(x)) = \operatorname*{\mathbb{E}}\limits_{x\sim \mathcal{D}}\mathbb{I}(h(x)\neq c(x))
$$

#### 1.1.2. 随机性问题的泛化误差
给定一个假设 $h\in \mathcal{H}$, 对于大多数的监督学习情境, hidden distribution $\mathcal{D}$定义在$\mathcal{X}\times \mathcal{Y}$上, 并且训练样本是根据$\mathcal{D}$采样得到的带标签的i.i.d. 样本
$$
S = \left((x_1, y_1), \cdots, (x_{m}, y_{m})\right)
$$
此时泛化误差定义为
$$
R(h) = \operatorname*{\mathbb{P}}\limits_{(x, y)\sim \mathcal{D}}(h(x)\neq y) = \operatorname*{\mathbb{E}}\limits_{(x, y)\sim \mathcal{D}}\mathbb{I}(h(x)\neq y)
$$


#### 1.1.3. 泛化误差评述
1. 在学习器上, 假设的泛化误差并不能直接计算得到. 对于确定性问题, 这是因为目标概念 $c(x)$ 和分布$\mathcal{D}$都是未知的. 对于非确定性问题, 这是因为联合分布$\mathcal{D}$是未知的
2. 确定性问题和随机性问题的区别在于, 对于确定性问题, 给定$x$的取值, $y$的取值被唯一确定了. 对于随机性问题, 给定$x$的取值, $y$的取值仍然是一个随机的分布. 

### 1.2. 经验误差
#### 1.2.1. 确定性问题的经验误差
给定一个假设 $h\in \mathcal{H}$, 一个目标概念 $c(x)$ 和一个样本$S = \{x_1, x_2, \cdots, x_m\}$. 经验误差(empirical risk) 定义为
$$
\hat{R}(h) = \dfrac{1}{m}\sum\limits_{i=1}^{m}\mathbb{I}(h(x_i)\neq c(x_i))
$$
#### 1.2.2. 随机性问题的经验误差
给定一个假设 $h\in \mathcal{H}$, 随机性问题给定的样本是$S = \{(x_1, y_1), (x_2, y_2), \cdots , (x_m, y_m)\}$, 经验误差(empirical risk) 定义为
$$
\hat{R}(h) = \dfrac{1}{m}\sum\limits_{i=1}^{m}\mathbb{I}(h(x_i)\neq y_i)
$$

### 1.3. 经验误差与泛化误差
对于一个固定的$h\in \mathcal{H}$, 在i.i.d. 样本集上经验误差的期望就等于泛化误差
$$
\mathbb{E}[\hat{R}(h)] = R(h)
$$

## 2. PAC (Probably Approximately Correct) Learnable
### 2.1. PAC Learnable的定义
#### 2.1.1. 确定性问题的PAC Learnable
如果存在一个算法$\mathcal{A}$和一个多项式函数$p$, 使得对于任意$\varepsilon>0$以及$\delta>0$, 对于所有在$\mathcal{X}$上的分布$\mathcal{D}$以及目标概念$c(x)\in \mathcal{C}$. 当样本规模$m\ge p\left(\dfrac{1}{\varepsilon}, \dfrac{1}{\delta}, n, \mathrm{size}(\mathcal{C})\right)$时均有下式成立 (其中$O(n)$表示对任意元素$x\in\mathcal{X}$计算表示的代价的上界, $\mathrm{size}(\mathcal{C})$表示对概念$c\in \mathcal{C}$计算表示的最大代价)
$$
\operatorname*{\mathbb{P}}\limits_{S\sim \mathcal{D}^m}\left({R}(h_s)\leq \varepsilon\right)\geq 1-\delta
$$
则称概念类$\mathcal{C}$ PAC-learnable. 

进一步地, 若$\mathcal{A}$的运行复杂度在 $p\left(\dfrac{1}{\varepsilon}, \dfrac{1}{\delta}, n, \mathrm{size}(\mathcal{C})\right)$内, 则称概念类$C$是efficiently PAC-learnable. 当这样的算法$\mathcal{A}$存在时, 则称该算法为$C$的一个PAC-learning algorithm.

#### 2.1.2. 随机性问题的PAC Learnable(不可知PAC Learnable)
设$\mathcal{H}$是一个假设集, $\mathcal{A}$是一个不可知PAC学习算法的条件是: 存在一个多项式函数$p$, 使得对于任意的$\varepsilon>0$, $\delta>0$和所有在$\mathcal{X}\times \mathcal{Y}$上的分布$\mathcal{D}$. 当样本规模$m\ge p\left(\dfrac{1}{\varepsilon}, \dfrac{1}{\delta}, n, \mathrm{size}(\mathcal{C})\right)$时, 有下面的不等式成立 (这里的$\mathrm{size}(\mathcal{C})$表示表示生成 $(x, y)$的最大代价)
$$
\operatorname*{\mathbb{P}}\limits_{S\sim \mathcal{D}^m}\left({R}(h_s) - \min\limits_{h\in \mathcal{H}}R(h)\leq \varepsilon\right)\geq 1-\delta
$$
进一步地, 如果算法$\mathcal{A}$可以在$p\left(\dfrac{1}{\varepsilon}, \dfrac{1}{\delta}, n, \mathrm{size}(\mathcal{C})\right)$内执行, 则其可被称为高效的不可知PAC学习算法.

#### 2.1.3. PAC Learnable的理解
1. PAC-learnable假设了训练集和测试集来源于相同的分布
2. PAC之所以被称为概率近似正确, 可以作如下理解: 如果输入到一个算法的样本点的数目对于$\dfrac{1}{\varepsilon}$ 和$\dfrac{1}{\delta}$是多项式的, 并且由该算法基于这些样本点得到的假设是以高概率近似正确的, 则概念类$\mathcal{C}$是PAC可学习的. 这里, $\delta>0$用来定义置信程度(confidence) $1-\delta$, $\varepsilon>0$用来定义准确性(accuracy) $1-\varepsilon$. 

### 2.2. 理论下界——贝叶斯误差
给定一个在$\mathcal{X}\times \mathcal{Y}$上的分布$\mathcal{D}$, 相应的贝叶斯误差$R^*$定义为由可测函数类$h: \mathcal{X}\times \mathcal{Y}$产生的误差下界
$$
R^* = \inf\limits_{h\ \mathrm{measurable}} R(h)
$$
一个满足$R(h) = R^*$的假设$h$被称为贝叶斯假设或贝叶斯分类器. 

对于确定性的情景, 我们有$R^* = 0$, 但对于随机性情景, $R^*\neq 0$. 进一步地, 贝叶斯分类器$h_{\mathrm{Bayes}}$可以用条件概率进行定义
$$
\forall x\in \mathcal{X}, \quad h_{\mathrm{Bayes}}(x) = \operatorname*{argmax}\limits_{y \in \{0,1 \}} \mathbb{P}(y\mid x)
$$

### 2.3. 误差分解
对于一个假设$h\in \mathcal{H}$的误差$R(h)$和贝叶斯误差$R^*$, 其差异可以按照下式进行分解
$$
R(h) - R^* = (R(h) - R(h^*)) + (R(h^*) - R^*)
$$
其中, $h^*$表示$\mathcal{H}$中误差最小的假设. 

1. 第一项称为**估计误差**, 不可知PAC学习的定义便是基于估计误差, 这种误差有时可以由泛化误差界定. 
2. 第二项称为**近似误差**, 这是由于其衡量了用假设集$\mathcal{H}$对贝叶斯误差的近似程度, 这种误差可以看作假设集$\mathcal{H}$的一个性质. 

## 3. 对有限假设集的学习保证
### 3.1. 一致的情况(确定性问题)
令$\mathcal{H}$是一个有限的, 由$\mathcal{X}\to \mathcal{Y}$的映射函数组成的集合. 令$\mathcal{A}$为学习任意目标概念$c\in \mathcal{H}$的算法, 并且根据i.i.d.的训练样本$S$返回的是一个一致的假设$h_s$: $\hat{R}(h_s) = 0$. 那么, 对于任意的$\varepsilon>0$和$\delta>0$. 不等式
$$
\operatorname*{\mathbb{P}}\limits_{S\sim \mathcal{D}^m}(R(h_s)\le \varepsilon)\ge 1-\delta
$$
成立的条件是
$$
 m \ge \dfrac{1}{\varepsilon}\left(\log\left(\dfrac{1}{\delta}\right)+\log|\mathcal{H}|\right)
$$
对应的, 这样的样本复杂度等价地可以得到如下的泛化界: 对于任意$\varepsilon>0$和$\delta>0$, 以至少$1-\delta$的概率, 有
$$
R(h_s) \le \dfrac{1}{m}\left(\log\left(\dfrac{1}{\delta}\right)+\log|\mathcal{H}|\right)
$$
这里, $\log|\mathcal{H}|$可以理解为表示$\mathcal{H}$所需要的二进制数位, 从这个角度而言, 泛化误差由二进制表示位数$\log |\mathcal{H}|$和样本规模$m$控制
___
##### Proof: 
固定$\varepsilon>0$. 我们有
$$
\begin{aligned}
\mathbb{P}\left(\exists h\in \mathcal{H}: \hat{R}(h) = 0 \wedge R(h)> \varepsilon\right) 
&\le \sum\limits_{h\in \mathcal{H}} \mathbb{P}\left(\hat{R}(h) = 0 \wedge R(h)> \varepsilon\right) \\
& \le \sum\limits_{h\in \mathcal{H}}^{}  \mathbb{P}\left(\hat{R}(h) = 0 \mid R(h)> \varepsilon\right) \\ 
& \le |\mathcal{H}|(1-\varepsilon)^m
\end{aligned}
$$
让右边等于$\delta$, 则原定理得证. 
#####
___



### 2.2. 不一致的情况(随机性问题)
令$\mathcal{H}$为一个有限的假设集, 则对于任意的$\delta>0$, 以至少为$1-\delta$的概率, 有下面的不等式成立
$$
\forall h\in \mathcal{H}, \quad R(h) \le \hat{R}(h) + \sqrt{\dfrac{\log |\mathcal{H}| +\log\left(\dfrac{2}{\delta}\right) }{2m}}
$$
___
##### Proof: 
设$h_1, \cdots, h_{|\mathcal{H}|}$是$\mathcal{H}$的组成元素, 利用[[../../../概率论/Book 2. 概率论/Chapter 1. 概率不等式/Lecture 2. Hoeffding Type Bounds#2. Hoeffding Inequality|Hoeffding Inequality]]不等式, 我们有
$$
\begin{aligned}
\mathbb{P}\left(\exists h\in \mathcal{H}: |\hat{R}(h) - R(h)|>\varepsilon\right)&\le \sum\limits_{h\in \mathcal{H}}^{} \mathbb{P}\left(|\hat{R}(h) - R(h)|> \varepsilon\right) \\ 
&\le 2 |\mathcal{H}|\exp\left(-2m\varepsilon^2\right) \\
\end{aligned}
$$
令上式右边等于$\delta$, 则可以得到上述的结论. 这也就是说, 对于一个有限的假设集$\mathcal{H}$
$$
\forall h\in \mathcal{H}, \quad R(h) \le \hat{R}(h) + \sqrt{\dfrac{\log |\mathcal{H}| +\log\left(\dfrac{2}{\delta}\right) }{2m}}
$$
#####
___