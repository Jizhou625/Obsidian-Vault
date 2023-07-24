## 0. 讨价还价博弈
### 0.1. 讨价还价博弈
一个讨价还价博弈是有序组合$(S, \boldsymbol{d})$, 其中
1. $S\subseteq \mathbb{R}^2$是非空凸紧集, 叫做备选方案集
2. $\boldsymbol{d} = (d_1,d_2)\in S$叫做分歧点
3. 存在满足$\boldsymbol{x} >> \boldsymbol{d}$的备选方案$\boldsymbol{x} = (x_1, x_2)\in S$ . 这里, $\boldsymbol{x} >> \boldsymbol{d}$表示对任意的$1\le i\le \mathrm{len}(\boldsymbol{x})$, 都有$x_i>d_i$. 

用$\mathcal{F}$表示所有讨价还价博弈组成的集合. 

### 0.2. 解的概念
将每个讨价还价博弈$(S, \boldsymbol{d})\in \mathcal{F}$和一个备选方案$\boldsymbol{\varphi}(S, \boldsymbol{d})\in S$联系起来的函数$\boldsymbol{\varphi}$叫做解的概念.

## 1. 纳什解
### 1.1. 纳什解的特征
#### 1.1.1. 对称性
如果满足如下的两个特征, 那么称讨价还价博弈$(S, \boldsymbol{d})\in \mathcal{F}$是对称的
1. 分歧点是对称的: $d_1 = d_2$
2. 备选方案集是对称的: 如果$\boldsymbol{x} = (x_1, x_2)\in S$, 那么$\boldsymbol{x}^{\prime} = (x_2, x_1)\in S$. 

从几何上来看, 对称性意味着备选方案集$S$关于$\mathbb{R}^2$内的主对角线是对称的. 

我们称解的概念$\boldsymbol{\varphi}$是对称的, 如果对每个对称的讨价还价博弈$(S, \boldsymbol{d})\in \mathcal{F}$, 向量$\boldsymbol{\varphi}(S, \boldsymbol{d}) =(\varphi_1(S, \boldsymbol{d}), \varphi_2(S, \boldsymbol{d}))$满足$\varphi_1(S, \boldsymbol{d}) = \varphi_2(S, \boldsymbol{d})$.

#### 1.1.2. 有效率
一个备选方案$\boldsymbol{x}\in S$在$S$内是有效率的, 如果不存在一个备选方案$\boldsymbol{y}\in S$, $\boldsymbol{y}\neq \boldsymbol{x}$, 使得$\boldsymbol{y}\ge \boldsymbol{x}$. 我们用$\mathrm{PO}(S)$表示在$S$内有效率点的集合. 

一个备选方案$\boldsymbol{x}\in S$在$S$内是弱有效率的, 如果在$S$内不存在被双方参与人都严格偏好的备选方案. 换言之, 不存在$\boldsymbol{y}\in S$, 使得$\boldsymbol{y}>>\boldsymbol{x}$. 用$\mathrm{PO}^W(S)$表示$S$内弱有效率点的集合.

一个解的概念$\boldsymbol{\varphi}$是有效率的, 如果对每个讨价还价博弈$(S, \boldsymbol{d})\in \mathcal{F}$, 都有$\boldsymbol{\varphi}(S, \boldsymbol{d}) \in \mathrm{PO}(S)$. 一个解的概念$\boldsymbol{\varphi}$是弱有效率的, 如果对每个讨价还价博弈$(S, \boldsymbol{d})\in \mathcal{F}$, 都有$\boldsymbol{\varphi}(S, \boldsymbol{d}) \in \mathrm{PO}^{W}(S)$.

#### 1.1.3. 正向仿射变换下的协变
一个解的概念$\boldsymbol{\varphi}$在正向仿射变换的变化下是协变的, 如果对每个讨价还价博弈$(S, \boldsymbol{d})\in \mathcal{F}$, 每个向量$\boldsymbol{a}\in \mathbb{R}^2$(满足$\boldsymbol{a}>>0$)和每个向量$\boldsymbol{b}\in \mathbb{R}^2$, 都有
$$
\boldsymbol{\varphi}(\boldsymbol{a}\odot S + \boldsymbol{b}, \boldsymbol{a}\odot\boldsymbol{d}+ \boldsymbol{b}) = \boldsymbol{a}\odot \boldsymbol{\varphi}(S, \boldsymbol{d})+ \boldsymbol{b}
$$


#### 1.1.4. 无关备选方案的独立性(Independent of Irrelevant Alternatives, IIA)
解的概念$\boldsymbol{\varphi}$满足IIA性, 如果对每个讨价还价博弈$(T, \boldsymbol{d})\in \mathcal{F}$和$S\subseteq T$, 下式成立: 
$$
\boldsymbol{\varphi}(T, \boldsymbol{d}) \in S \implies \boldsymbol{\varphi}(S, \boldsymbol{d}) = \boldsymbol{\varphi}(T, \boldsymbol{d})
$$



### 1.2. 纳什解的唯一性
在所有满足对称性、有效率、正向仿射变换下的协变和IIA的族$\mathcal{F}$中, 存在唯一的解的概念$\boldsymbol{\mathcal{N}}$. 讨价还价博弈$(S, \boldsymbol{d})$的解$\boldsymbol{\mathcal{N}}(S, \boldsymbol{d})$是$S$内个体理性的备选方案, 并且最大化矩形的面积
$$
f(\boldsymbol{x}) = (x_1 - d_1)(x_2 -d_2)
$$
___
##### Proof
首先我们证明, 对每个讨价还价博弈$(S, \boldsymbol{d})\in \mathcal{F}$, 在集合$S$中存在唯一的点$\boldsymbol{x}$最大化
$$
f(\boldsymbol{x}) = (x_1 - d_1)(x_2 -d_2)
$$ 
集合$D = \{\boldsymbol{x}\in S \mid \boldsymbol{x}\ge \boldsymbol{0}\}$是凸紧集$S$和闭凸集$\{\boldsymbol{x}\in \mathbb{R}^2\mid \boldsymbol{x}\ge \boldsymbol{0}\}$的交集, 因此$D$也是凸紧集. 又因为$f$是连续的, 因此在$D$上存在最大值. 如果在$D$上存在两个不同的点$\boldsymbol{y}, \boldsymbol{z}$同时使得$f$取得最大值. 也就是说 
$$
(y_1-d_1)(y_2-d_2) = (z_1-d_1)(z_2-d_2)
$$
定义
$$
\boldsymbol{w} = \frac{1}{2}(\boldsymbol{y} + \boldsymbol{z})
$$
可以证明
$$
f(\boldsymbol{w}) > f(\boldsymbol{y})
$$
这与$\boldsymbol{y}$使得$f$取最大值矛盾!这就证明了$f(\boldsymbol{x})$在唯一的点实现最大化. 
因此, 下面的函数是良好定义的
$$
\boldsymbol{\mathcal{N}}(S, \boldsymbol{d}) = \operatorname*{argmax}\limits_{\boldsymbol{x}\in S, \boldsymbol{x}\ge \boldsymbol{d}}(x_1 - d_1)(x_2 -d_2) >> \boldsymbol{d}
$$
不难验证解的概念$\boldsymbol{\mathcal{N}}$满足对称性、有效率、正向仿射变换下的协变和IIA. 下面只需要证明$\boldsymbol{\mathcal{N}}$是唯一满足条件的解的概念. 

假设$\boldsymbol{\varphi}$是另外一个满足对称性、有效率、正向仿射变换下的协变和IIA的解的概念. 用$\boldsymbol{y}^*$表示$\mathcal{N}(S, \boldsymbol{d})$. 首先实施正向仿射变换
$$
L(x_1, x_2) = \left(\dfrac{x_1-d_1}{y_1^* - d_1}, \dfrac{x_2-d_2}{y_2^* - d_2}\right)
$$
这个仿射变换将$\boldsymbol{y}^*$变换为$(1,1)$, 将$\boldsymbol{d}$变换为$(0,0)$. 因此, 可以不妨设$\mathcal{N}(S, \boldsymbol{d}) = (1,1)$, $\boldsymbol{d} = (0,0)$. 根据$\mathcal{N}$的最优性, 对每个$\boldsymbol{x}\in S$, 都有$x_1+x_2\le 2$成立. 设$T$是一个相对于对角线$x_1 = x_2$的对称方格, 包含$S$, 其中一个边沿着线$x_1+x_2=2$(如下图所示)
![1](Lecture%209.%20%E8%AE%A8%E4%BB%B7%E8%BF%98%E4%BB%B7-%E6%8B%8D%E5%8D%96.assets/%E7%BA%B3%E4%BB%80%E8%A7%A3%E7%9A%84%E8%AF%81%E6%98%8E.png)  

根据$\boldsymbol{\varphi}$是对称的和有效率的, 因此$\boldsymbol{\varphi}(T, (0,0)) = (1,1)$. 又因为IIA并且$S\subseteq T$, 于是$\boldsymbol{\varphi}(S, (0,0)) = (1,1)$. 这就证明了$\boldsymbol{\varphi} = \boldsymbol{\mathcal{N}}$.
#####
___

### 1.3. 纳什解的最小特征
下面我们将给出例子, 当某个特征无法满足, 而另外三个特征满足时, 解的概念$\boldsymbol{\mathcal{N}}$不再是唯一的.
#### 1.3.1. 不满足有效率
定义解的概念$\boldsymbol{\varphi}$如下
$$
\boldsymbol{\varphi}(S, \boldsymbol{d}) = \dfrac{\boldsymbol{d}+ \mathcal{N}(S, \boldsymbol{d})}{2}
$$
在四个纳什特征中, 这个解的概念唯一没有满足的是有效率.

#### 1.3.2. 不满足对称性
定义解的概念$\boldsymbol{\varphi}$如下
$$
\boldsymbol{\varphi}(S, \boldsymbol{d}) = \operatorname*{argmax}\limits_{\boldsymbol{x}\in \mathrm{PO}(S), \boldsymbol{x}\ge \boldsymbol{d}} x_1
$$
在四个纳什特征中, 这个解的概念唯一没有满足的是对称性.

#### 1.3.3. 不满足正向仿射变换下的协变
对每个角$0<\alpha < \dfrac{\pi}{2}$. 令$\lambda_{\alpha}(S, \boldsymbol{d})$为如下所示的射线上的最高点. 
![2](Lecture%209.%20%E8%AE%A8%E4%BB%B7%E8%BF%98%E4%BB%B7-%E6%8B%8D%E5%8D%96.assets/%E6%AD%A3%E5%90%91%E4%BB%BF%E5%B0%84%E5%8F%98%E6%8D%A2%E4%B8%8B%E7%9A%84%E5%8D%8F%E5%8F%98.png)  

在四个纳什特征中, $\lambda_{\frac{\pi}{4}}(S, \boldsymbol{d})$唯一没有满足的是正向仿射变换下的协变.


#### 1.3.4. 不满足IIA
定义解的概念$\boldsymbol{\varphi}$如下: 如果存在一个正向的仿射变换$L$, 满足特征$(L(S), L(\boldsymbol{d}))$是一个对称的讨价还价博弈, 那么$\boldsymbol{\varphi}(S, \boldsymbol{d}) = \mathcal{N}(S, \boldsymbol{d})$. 
$$
\boldsymbol{\varphi}(S, \boldsymbol{d}) = \begin{cases} \mathcal{N}(S, \boldsymbol{d}), & \exists L \text{ is affine},\ \mathrm{s.t.} (L(S), L(\boldsymbol{d})) \text{ is a symmetric bargaining game} \\ 
\operatorname*{argmax}\limits_{\boldsymbol{x}\in\mathrm{PO}(S); \boldsymbol{x}\ge \boldsymbol{d}} x_1, &\mathrm{Others}\end{cases}
$$
在四个纳什特征中, $\boldsymbol{\varphi}$唯一没有满足的是IIA.

### 1.4. 对纳什解的批评
#### 1.4.1. 正向仿射变换下的协变的不合理性
改变分歧点$\boldsymbol{d}$和备选方案集$S$可能会让参与人产生新的需求. 例如, 如果两个能力大致相同的参与人谈判瓜分$\$1000$, 对称的解$(\$500, \$500)$是合理的. 但如果其中的一个参与人非常富有, 那么对于讨价还价的结果, 会出现两个相反的影响. 一方面, 缺钱的人得到更大的份额看起来会更加公平; 另一方面, 富有的人拥有更强的谈判权. 

#### 1.4.2. IIA的不合理性
IIA是一个有争议的概念. 当解的概念$\boldsymbol{\varphi}$反映了最佳的结果时, IIA是合理的. 但是, 当解的概念$\boldsymbol{\varphi}$反映了妥协的结果时, IIA是不合理的
![3](Lecture%209.%20%E8%AE%A8%E4%BB%B7%E8%BF%98%E4%BB%B7-%E6%8B%8D%E5%8D%96.assets/IIA%E7%9A%84%E6%89%B9%E8%AF%84.png)  
如上图所示, 两个讨价还价博弈的纳什解都是$(50, 10)$, 但在Game B中, $(50,10)$给参与人1带来了最大可能收益, 但参与人2却没有得到他的最大可能收益. 因此, 参与人2要求更高的收益而参与人1做出妥协是合理的. 

#### 1.4.3. 分别的改善未必带来均衡的改善
![4](Lecture%209.%20%E8%AE%A8%E4%BB%B7%E8%BF%98%E4%BB%B7-%E6%8B%8D%E5%8D%96.assets/%E5%88%86%E5%88%AB%E7%9A%84%E6%94%B9%E5%96%84%E6%9C%AA%E5%BF%85%E5%B8%A6%E6%9D%A5%E5%9D%87%E8%A1%A1%E7%9A%84%E6%94%B9%E5%96%84.png)  
如上图所示, 浅色阴影部分相比于深色阴影部分, 两个参与人都会得到更多的收益. 但是, 浅色阴影部分的纳什解$(1, 0.7)$和深色阴影部分的纳什解$(0.75, 0.75)$相比, 参与人2的收益反而下降了. 

#### 1.4.4. 纳什解的概率不可加性
![5](Lecture%209.%20%E8%AE%A8%E4%BB%B7%E8%BF%98%E4%BB%B7-%E6%8B%8D%E5%8D%96.assets/%E7%BA%B3%E4%BB%80%E8%A7%A3%E7%9A%84%E6%A6%82%E7%8E%87%E4%B8%8D%E5%8F%AF%E5%8A%A0%E6%80%A7.png)  
考虑两个参与人以$\dfrac{1}{2}$的概率参与讨价还价博弈$(S, \boldsymbol{0})$和$(T, \boldsymbol{0})$. 理论上来说, 这等价于他们在参加讨价还价博弈$\left(\dfrac{1}{2}S + \dfrac{1}{2}T, \boldsymbol{0}\right)$. 不难计算出, 博弈$(S, \boldsymbol{0})$的纳什解是$(25, 50)$, $(T, \boldsymbol{0})$的纳什解为$(50, 25)$, 它们的均值是$(37.5, 37.5)$. 但在讨价还价博弈$\left(\dfrac{1}{2}S + \dfrac{1}{2}T, \boldsymbol{0}\right)$中, 纳什解是$(50, 50)$. 



## 2. 对纳什解的深入讨论
### 2.1. 纳什解的几何刻画
对每个讨价还价博弈$(S, \boldsymbol{d})\in \mathcal{F}$, 我们有$\boldsymbol{\mathcal{N}}(S, \boldsymbol{d}) = \boldsymbol{y}$当且仅当
1. $\boldsymbol{y}\in \mathrm{PO}(S)$
2. $\boldsymbol{y}>>\boldsymbol{d}$
3. 在$\boldsymbol{y}$处存在$S$的支撑线$l$. 设$l$与$x_2 = d_2$相交于点$\boldsymbol{p}$, 则三角形$\Delta DYP$是一个等腰三角形. 

![6](Lecture%209.%20%E8%AE%A8%E4%BB%B7%E8%BF%98%E4%BB%B7-%E6%8B%8D%E5%8D%96.assets/%E7%BA%B3%E4%BB%80%E8%A7%A3%E7%9A%84%E5%87%A0%E4%BD%95%E5%88%BB%E7%94%BB.png)  

___
##### Proof
给定讨价还价博弈$(S, \boldsymbol{d})\in \mathcal{F}$和$\boldsymbol{y}^* = \mathcal{N}(S, \boldsymbol{d})$. 我们知道, 存在正向的仿射变换$L$, 使得$L(\boldsymbol{d}) = (0, 0), \boldsymbol{z}^* = L(\boldsymbol{y}^*) = (1,1)$, 并且$L(S)$是半空间$x_1+ x_2 \le 2$的子集. 因此$x_1+x_2=2$是$L(S)$在$\boldsymbol{z}^*$处的支撑线. 而$(0, 0), (1,1)$和$(2,0)$三个点恰好构成一个等腰三角形. 根据仿射变换的性质. 我们不难证明纳什解的几何性质. 
#####
___

### 2.2. 沙普利对纳什解的刻画(效用的人际比较)
令$(S, \boldsymbol{d})\in \mathcal{F}$是一个讨价还价博弈. 对每个满足$\boldsymbol{y}>> \boldsymbol{d}$的有效率点, 在$\boldsymbol{y}$处存在$S$唯一的切线. 那么存在唯一的备选方案$\boldsymbol{x}\in S$, 使得存在一个正数$c>0$满足
1. 平均主义: $x_2 - d_2 = c(x_1-d_1)$
2. 功利主义: $\boldsymbol{x}\in \operatorname*{argmax}\limits_{\boldsymbol{y}\in S} \{(y_2 - d_2)+ c(y_1 - d_1)\}$
   
这个备选方案$\boldsymbol{x}$就是纳什解$\mathcal{N}(S, \boldsymbol{d})$. 
___
##### Proof
我们首先验证纳什解$\boldsymbol{y}^* = \mathcal{N}(S, \boldsymbol{d})$满足平均主义和功利主义. 根据[[#2.1. 纳什解的几何刻画]], 设$\boldsymbol{y}^*$与$x_2 = d_2$交于点$p$. $DY$和$YP$的斜率互为相反数, 记$DY$的斜率为$c$, 不难验证, $c$就是满足平均主义和功利主义的正数.

接下来, 我们证明解的唯一性. 假设存在另外一个备选方案$\boldsymbol{x}^*\in S$, 满足平均主义和功利主义. 根据功利主义, $\boldsymbol{x}^*$有效率. 根据条件, 在$\boldsymbol{x}^*$处存在$S$唯一的切线. 根据平均主义和功利主义的定义, 这条切线的斜率和$DY$的斜率互为相反数. 因此三角形$\Delta DYP$是一个等腰三角形. 根据[[#2.1. 纳什解的几何刻画]], $\boldsymbol{x}^* = \mathcal{N}(S, \boldsymbol{d})$.
#####
___


### 2.3. 超过2人的讨价还价博弈
#### 2.3.1. 参与人集为$N$的讨价还价博弈
一个多人的讨价还价博弈是$(N, S, \boldsymbol{d})$, 这里
1. $N$是参与人的有限集合
2. $S\subseteq \mathbb{R}^N$是备选方案的非空凸紧集, 并且存在满足$\boldsymbol{x}>>\boldsymbol{d}$的备选方案$\boldsymbol{x}\in S$.
3. $\boldsymbol{d}\subseteq \mathbb{R}^N$是分歧点

用$\mathcal{F}^N$表示参与人集为$N$的所有讨价还价博弈$(N, S, \boldsymbol{d})$组成的集合. 用$\mathcal{F}^* = \bigcap\limits_{N\subseteq \mathbb{N}}^{} \mathcal{F}^N$表示具有有限参与人集的所有讨价还价博弈组成的集合. 

#### 2.3.2. 解的概念
解的概念$\boldsymbol{\varphi}$是一个函数, 它将每个讨价还价博弈$(N, S, \boldsymbol{d})\in \mathcal{F}^*$和一个备选方案$\boldsymbol{\varphi}(N, S, \boldsymbol{d})\in S$联系起来.


#### 2.3.3. 纳什解的唯一性
对于讨价还价博弈族$\mathcal{F}^*$, 存在唯一的解的概念$\boldsymbol{\mathcal{N}}^*$, 它满足对称性、有效率、正向仿射变换下的协变和IIA. 对每个讨价还价博弈$(N, S, \boldsymbol{d})\in \mathcal{F}^*$, 解的概念$\boldsymbol{\mathcal{N}}^*(N, S, \boldsymbol{d})$是$S$内个体理性的备选方案, 并且最大化超矩形的体积
$$
f(\boldsymbol{x}) = \prod\limits_{i\in N}^{} (x_i - d_i)
$$
### 2.4. 多人讨价还价博弈的纳什解的另一种刻画
#### 2.4.1. 一致性
解的概念$\boldsymbol{\varphi}$满足一致性, 如果对每个讨价还价博弈$(N, S, \boldsymbol{d})\in \mathcal{F}^*$和每个非空参与人集合$I\subset N$. $\{\varphi_i(I, S,\boldsymbol{d})\}_{i\in I}$是讨价还价博弈$(I, \widehat{S}, \widehat{d})$的解. 其中
1. 对每个$i\in I, \widehat{d}_i = d_i$. 
2. $\widehat{S} = \{(x_i)_{i\in I}\in \mathbb{R}^I\mid ((x_i)_{i\in I}, (\varphi_j(N, S, \boldsymbol{d}))_{j\notin I})\in S\}$. 

一致性特征是我们给出的唯一涉及不同参与人数量的博弈特征.

#### 2.4.2. 匿名性
解的概念$\boldsymbol{\varphi}$满足匿名性, 如果对每个讨价还价博弈$(N, S, \boldsymbol{d})\in \mathcal{F}^*$和参与人集合$N$的每个排列$\pi$
$$
\boldsymbol{\varphi}_{\pi(i)}(\pi(S), \pi(\boldsymbol{d})) = \varphi_i(S, \boldsymbol{d}), \quad \forall i \in N
$$

#### 2.4.3. 讨价还价博弈族$\mathcal{F}^*_0$
用$\mathcal{F}_0^*$表示讨价还价博弈$(N, S, \boldsymbol{d})$的族
1. 参与人集合$N$是有限的
2. 分歧点$\boldsymbol{d} = \boldsymbol{0}$
3. 集合$S$是$\mathbb{R}^N$内的非空凸紧集
4. 对每个$\boldsymbol{x}\in S$, 都有$\boldsymbol{x}\ge \boldsymbol{0}$, 并且存在$\boldsymbol{x}\in S$, 使得$\boldsymbol{x}>> \boldsymbol{0}$
5. 完备性: 如果$\boldsymbol{x}\in S$, 那么矩形$\operatorname*{\times}\limits_{i\in N}[d_i, x_i]\subseteq S$

#### 2.4.4. 纳什解的另一种刻画
在讨价还价博弈族$\mathcal{F}_0^*$中, 满足有效率、匿名性、正向仿射变换的协变以及一致性特征的唯一的解的概念是纳什解$\boldsymbol{\mathcal{N}}^*$.


## 3. 讨价还价博弈中其他解的概念
### 3.1. 单调性特征
解的概念$\boldsymbol{\varphi}$在一族讨价还价博弈$\mathcal{F}_0$上满足完全单调性, 如果对满足$S\subseteq T$的每一对讨价还价博弈$(S, \boldsymbol{d})$和$(T, \boldsymbol{d})$
$$
\boldsymbol{\varphi}(S, \boldsymbol{d}) \le \boldsymbol{\varphi}(T, \boldsymbol{d})
$$
当增加更多可能的结果并不恶化一个参与人的境况时, 完全单调性的特征就得到了满足. 

### 3.2. 乌托邦点
定义
$$
\begin{aligned} 
    m_1(S) = \max\{x_1\in \mathbb{R}\mid \exists x_2\in \mathbb{R}, \mathrm{s.t.}\ (x_1, x_2)\in S\} \\ 
m_2(S) = \max\{x_2\in \mathbb{R}\mid \exists x_1\in \mathbb{R}, \mathrm{s.t.}\ (x_1, x_2)\in S\} 
\end{aligned}
$$
点$(m_1(S), m_2(S))$叫做博弈的乌托邦点. 这个点通常不在$S$内.
![0](Lecture%209.%20%E8%AE%A8%E4%BB%B7%E8%BF%98%E4%BB%B7.assets/%E4%B9%8C%E6%89%98%E9%82%A6%E7%82%B9.png)  


### 3.3. 有限单调性
解的概念$\boldsymbol{\varphi}$在一族讨价还价博弈$\mathcal{F}_0$上满足有限单调性, 如果对$\mathcal{F}_0$内满足
1. $S\subseteq T$
2. $m_1(S) = m_1(T)$
3. $m_2(S) = m_2(T)$

的每一对讨价还价博弈$(S, \boldsymbol{d})$和$(T, \boldsymbol{d})$, 都有
$$
\boldsymbol{\varphi}(S, \boldsymbol{d}) \le \boldsymbol{\varphi}(T, \boldsymbol{d})
$$

### 3.4. $\boldsymbol{\lambda}_{\alpha}$解
令$\boldsymbol{\varphi}$是$\mathcal{F}_0$上解的概念, 满足弱有效率、齐次性、严格个体理性和完全单调性. 那么存在一个角$\alpha\in \left(0, \dfrac{\pi}{2}\right)$, 使得$\boldsymbol{\varphi} = \boldsymbol{\lambda}_{\alpha}$
___
##### Proof
令$\boldsymbol{\varphi}$是满足定理所述的四个特征的解的概念. 定义$\Delta\subseteq \mathbb{R}^2$如下
$$
\Delta = \{\boldsymbol{x}\in [0,1]^2\mid x_1 + x_2 \le 1\}
$$
用$\boldsymbol{y}^*$表示$\boldsymbol{\varphi}(\Delta)$. 令$\alpha = \arctan\left(\dfrac{y_2^*}{y_1^*}\right)$. 我们将证明$\boldsymbol{\varphi} = \boldsymbol{\lambda}_{\alpha}$对任意的$S\in \mathcal{F}_0$成立.

用$\boldsymbol{z}^*$表示$\boldsymbol{\lambda}_{\alpha}(S)$. 根据$\mathcal{F}_0$的定义, 矩形$[z^*_1, 0]\times [0, z_2^*]\in S$, 考虑凸四边形$V_{\varepsilon} = (\boldsymbol{0}, (z^*_1(1+\varepsilon), 0), \boldsymbol{z}^*, (0, z^*_2(1+\varepsilon)))$, 其中$\varepsilon$是一个足够小的正数. 
![1](Lecture%209.%20%E8%AE%A8%E4%BB%B7%E8%BF%98%E4%BB%B7.assets/lambda_alpha.png)  
不难证明$\boldsymbol{\varphi}(V_{\varepsilon}) = \boldsymbol{\varphi}(\Delta)$. 借助于辅助图形$V_{\varepsilon}$, 我们有
$$
\boldsymbol{\varphi}(S)= \boldsymbol{\lambda}_{\alpha}(S) 
$$
#####
___



### 3.5. Kalai-Smorodinsky解
在$\mathcal{F}_0$的族上存在唯一的解的概念$\mathcal{KS}$, 满足对称性、有效率、度量单位的独立性和有限单调性. 这个解是$S$内的最高点, 并且在连接分歧点$\boldsymbol{0}$和乌托邦点$(m_1(S), m_2(S))$的线段上.
___
##### Proof
首先$\mathcal{KS}$是良好定义的, 并且满足对称性、有效率、度量单位的独立性和有限单调性. 接下来我们证明$\mathcal{KS}$的唯一性. 令$\boldsymbol{\varphi}$是满足对称性、有效率、度量单位的独立性和有限单调性的解的概念. 令$\boldsymbol{y}^* = \mathcal{KS}(S, \boldsymbol{d})$. 定义
$$
T = \mathrm{conv}\{\boldsymbol{0}, (0, m_2(S)), \boldsymbol{y}^*, (m_1(S), 0)\}
$$
显然$T\subseteq S$. 


不妨设$(m_1(S), m_2(S)) = (1,1)$, 否则总可以实施正向度量单位变换, 使得$(m_1(S), m_2(S)) = (1,1)$. 于是$\mathcal{KS}(S)$在$x_1=x_2$上, 这意味着$T$是对称的. 根据对称性和有效率, 我们有$\mathcal{KS}(T) = \mathcal{KS}(S) = \boldsymbol{y}^*$. 同样地, 根据$T$的对称性和$\boldsymbol{\varphi}$有效率, 我们有$\boldsymbol{\varphi}(T) = \mathcal{KS}(T) = \boldsymbol{y}^*$. 又因为$\boldsymbol{\varphi}$和$\mathcal{KS}$满足有限单调性, 则有
$$
\boldsymbol{\varphi}(S)\ge \boldsymbol{\varphi}(T) = \boldsymbol{y}^*
$$
因为$\mathcal{KS}$是有效率的, 所以$S$唯一大于等于$\boldsymbol{y}^*$的备选方案是$\boldsymbol{y}^*$本身, 故$\boldsymbol{\varphi}(S) = \boldsymbol{y}^*$. 这就证明了$\mathcal{KS}$的唯一性.
#####
___