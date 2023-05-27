## 1. 典型集
### 1.1. 渐进均分性(AEP)
若$X_1,X_2,\cdots , X_n$为独立同分布的离散随机变量, 其概率质量函数为$p(x)$, 则
$$
-\dfrac{1}{n}\log p(X_1,X_2,\cdots , X_n)\overset{p}{\to} H(X)
$$

设$X_1,X_2,\cdots , X_n$是一个服从于密度函数$f(x)$的独立同分布的随机变量序列, 那么
$$
-\dfrac{1}{n}\log f(X_1,X_2,\cdots , X_n)\overset{p}{\to} \mathbb{E}\left[-\log f(X)\right]=h(x)
$$
### 1.2. 典型集(typical set)
关于离散随机变量$X$的概率质量函数$p(x)$的典型集$\mathcal{A}_{\varepsilon}^{(n)}$是序列$(x_1,x_2,\cdots ,x_n)\in \mathcal{X}^n$的集合, 且满足性质
$$
2^{-n(H(x)+\varepsilon)}\le p(x_1,x_2,\cdots , x_n)\le 2^{-n(H(x)-\varepsilon)}
$$

对$\varepsilon>0$和任意的$n$, 定义$f(x)$的典型集$\mathcal{A}^{(n)}_{\varepsilon}$如下
$$
\mathcal{A}_{\varepsilon}^{(n)}=\left\{(x_1,x_2,\cdots , x_n)\in S^n: \left|-\dfrac{1}{n}\log f(X_1,X_2,\cdots , X_n)-h(X)\right|\le \varepsilon\right\}
$$
其中$f(X_1,X_2,\cdots , X_n)=\prod\limits_{i=1}^n f(x_i)$. 

### 1.3. 典型集的性质
典型集$\mathcal{A}_{\varepsilon}^{(n)}$具有如下性质
1. 如果$(x_1,x_2,\cdots , x_n)\in \mathcal{A}_{\varepsilon}^{(n)}$, 则$H(X)-\varepsilon\le -\dfrac{1}{n} \log p(x_1,x_2,\cdots, x_n)\le H(X)+\varepsilon$, 这表明典型集中的所有元素几乎是等可能的
2. 当$n$充分大时, $\mathbb{P}(\mathcal{A}_{\varepsilon}^{(n)})>1-\varepsilon$
3. $|\mathcal{A}_{\varepsilon}^{(n)}|\le 2^{n(H(X)+\varepsilon)}$或$\mathrm{Vol}(\mathcal{A}^{(n)}_{\varepsilon})\le 2^{n(h(X)+\varepsilon)}$
4. 当$n$充分大时, $|\mathcal{A}_{\varepsilon}^{(n)}|\ge (1-\varepsilon)2^{n(H(X)-\varepsilon)}$或$\mathrm{Vol}(\mathcal{A}^{(n)}_{\varepsilon})\ge (1-\varepsilon)2^{n(h(X)-\varepsilon)}$

___
##### Proof
1. 由典型集的定义可知
2. 由大数定律立得
3. 我们有
   $$
   \begin{aligned} 
        1 &= \sum\limits_{x\in \mathcal{X}}^{} p(\boldsymbol{x}) \\ 
        & \ge \sum\limits_{x\in A_{\varepsilon}^{(n)}}^{} p(\boldsymbol{x}) \\
        &\ge \sum\limits_{x\in A_{\varepsilon}^{(n)}}^{} 2^{-n(H(X)+\varepsilon)} \\
        & = 2^{-n(H(X)+\varepsilon)}|\mathcal{A}_{\varepsilon}^{(n)}|
   \end{aligned}
   $$
4. 最后, 当$n$充分大时, 有
   $$
   \begin{aligned} 
        1 - \varepsilon &< \mathbb{P}( A_{\varepsilon}^{(n)})\\  
        & \le \sum\limits_{x\in A_{\varepsilon}^{(n)}}^{} 2^{-n(H(x) - \varepsilon)}\\
        & = 2^{-n(H(X)-\varepsilon)}|\mathcal{A}_{\varepsilon}^{(n)}|
   \end{aligned}
   $$
   因此
   $$
   |\mathcal{A}_{\varepsilon}^{(n)}|\ge (1-\varepsilon)2^{n(H(X)-\varepsilon)}
   $$
#####
___

### 1.4. 熵是数据编码的确界(典型集的应用)
熵是数据编码的确界
___
##### Proof
由于典型集$\mathcal{A}_{\varepsilon}^{(n)}$中的序列个数不超过$2^{n(H(X)+\varepsilon)}$, 故可以用长度不超过$n(H+\varepsilon)+2$比特的序列编码, 其中首位为$0$. 对于非典型集中的元素, 可以用长度不超过$n\log |\mathcal{X}|+2$比特的序列编码, 其中首位为$1$. 则平均编码长度为
$$
\mathbb{E}(l(X^n))\le n(H+\varepsilon+\varepsilon\log |\mathcal{X}|)+2
$$
也就是说, 对于任意$\varepsilon_0>0$, 存在充分大的$n$, 使得
$$
\mathbb{E}\left[\dfrac{1}{n}l (X^n)\right]\le H(x)+\varepsilon_0
$$
从而我们证明了, 熵是数据编码的确界. 
#####
___

## 2. 最小高概集
### 2.1. 最小高概集的定义
对于每个$n=1,2,\cdots,$, 设$\mathcal{B}_{\delta}^{(n)}\subset \mathcal{X}^n$为满足如下条件的最小集, 即
$$
\mathbb{P}\left(\mathcal{B}_{\delta}^{(n)}\right) \ge 1-\delta
$$

### 2.2. 最小高概集的估计
设$X_1, X_2, \cdots, X_n$为服从$p(x)$的i.i.d.序列. 对$\delta<\dfrac{1}{2}$以及任意的$\delta^{\prime}>0$, 如果$\mathbb{P}\left(\mathcal{B}_{\delta}^{(n)}\right) \ge 1-\delta$, 则对于充分大的$n$, 有
$$
\dfrac{1}{n}\log |\mathcal{B}_{\delta}^{(n)}| \ge H(X)-\delta^{\prime}
$$
因此在一阶指数的意义下, $\mathcal{B}_{\delta}^{(n)}$至少含有$2^{nH}$个元素. 
___
##### Proof
显然, 我们有
$$
\begin{aligned} 
   1 - \varepsilon - \delta &\le \mathbb{P}\left(\mathcal{A}_{\varepsilon}^{(n)}\cap \mathcal{B}_{\delta}^{(n)}\right) \\ 
   & = \sum\limits_{\mathcal{A}_{\varepsilon}^{(n)}\cap \mathcal{B}_{\delta}^{(n)}} p(\boldsymbol{x}^n) \\ 
   & \le \sum\limits_{\mathcal{A}_{\varepsilon}^{(n)}\cap \mathcal{B}_{\delta}^{(n)}} 2^{-n(H(X)-\varepsilon)} \\
   & = 2^{-n(H(X)-\varepsilon)}|\mathcal{A}_{\varepsilon}^{(n)}\cap \mathcal{B}_{\delta}^{(n)}| \\ 
   & \le 2^{-n(H(X)-\varepsilon)}|\mathcal{B}_{\delta}^{(n)}|
\end{aligned}
$$
因此我们有
$$
\dfrac{1}{n}\log |\mathcal{B}_{\delta}^{(n)}| \ge H(X)-\delta^{\prime}
$$
#####
___