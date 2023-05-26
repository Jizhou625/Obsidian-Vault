## 1. 熵
### 1.1. 熵的概念
一个离散型随机变量$X$的熵$H(X)$定义为
$$
H(X)=-\sum_{x\in\mathcal{X}} p(x)\log p(x)=-\mathbb{E}_{p(x)}\log p(X)
$$
对于任意$n$个随机变量$X_1, X_2, \cdots, X_n$, 其联合熵(joint entropy)定义为
$$
H(X_1, X_2, \cdots, X_n) = - \mathbb{E}_{p(x_1, x_2, \cdots, x_n)} \log p(X_1, X_2, \cdots, X_n)
$$
从直观上讲, 随机变量的熵度量了随机变量的不确定性, 熵越大, 不确定性就越强. 

### 1.2. 条件熵(conditional entropy)
对于任意$n$个随机变量$X_1, X_2, \cdots, X_n$和$m$个随机变量$Y_1, Y_2, \cdots, Y_m$, 其条件熵(conditional entropy)定义为
$$
\begin{aligned} 
      H(Y_1, Y_2, \cdots, Y_m\mid X_1, X_2, \cdots, X_n) = - \mathbb{E}_{p(x_1, x_2, \cdots, x_n, y_1, y_2, \cdots, y_m)} \log p(Y_1, Y_2, \cdots, Y_m\mid X_1, X_2, \cdots, X_n) 
\end{aligned}
$$

### 1.3. 条件熵的链式法则
条件熵具有链式法则, 对于任意$n$个随机变量$X_1, X_2, \cdots, X_n$, 我们有
$$
H(X_1,X_2,\cdots, X_n)=\sum_{i=1}^n H(X_i\mid X_{i-1},\cdots, X_1)\le \sum_{i=1}^nH(X_i)
$$
___
##### Proof
根据条件概率公式, 我们有
$$
p(x_1, x_2,\cdots, x_n) = p(x_1)p(x_2\mid x_1)p(x_3\mid x_1, x_2)\cdots p(x_n\mid x_1, x_2,\cdots, x_{n-1})
$$
取对数可以得到
$$
\log p(x_1, x_2,\cdots, x_n) = \sum\limits_{i=1}^n \log p(x_i\mid x_1, x_2,\cdots, x_{i-1})
$$
对$p(x_1,x_2, \cdots, x_n)$取期望, 可以得到
$$
H(X_1,X_2,\cdots, X_n)=\sum_{i=1}^n H(X_i\mid X_{i-1},\cdots, X_1)
$$
#####
___

### 1.4. 熵与不确定性
#### 1.4.1. 条件作用使熵变小
设$X,Y$是任意两个随机变量, 则有
$$
H(X)\ge H(X\mid Y)
$$
等号成立当且仅当$X,Y$相互独立. 这意味着信息不会有负面影响. 	


#### 1.4.2. 熵的组合法则(组合使熵变小)
设$\boldsymbol{p}=(p_1,p_2,\cdots , p_m)$为$m$个元素上的概率分布, 定义$m-1$个元素上的新分布$\boldsymbol{q}$为$q_1=p_1,\cdots,  q_{m-2}=p_{m-2}$以及$q_{m-1}=p_{m-1}+p_m$, 则
$$
H(\boldsymbol{p})=H(\boldsymbol{q})+(p_{m-1}+p_m)H\left(\dfrac{p_{m-1}}{p_{m-1}+p_m}\right)
$$
___
##### Proof
事实上, 我们有
$$
\begin{aligned} 
    H(\boldsymbol{p}) &= \sum\limits_{i=1}^{m} p_i \log \dfrac{1}{p_i} \\ 
    &= \sum\limits_{i=1}^{m-2} q_i \log \dfrac{1}{q_i} + p_{m-1}\log \dfrac{1}{p_{m-1}} + p_m\log \dfrac{1}{p_m} \\  
     &= H(\boldsymbol{q}) -(p_{m-1}+p_m)\log \dfrac{1}{p_{m-1}+p_m}+ p_{m-1}\log \dfrac{1}{p_{m-1}} + p_m\log \dfrac{1}{p_m} \\ 
     & = H(\boldsymbol{q}) + (p_{m-1}+ p_m) H\left(\dfrac{p_{m-1}}{p_{m-1}+p_m}\right)
\end{aligned}
$$
#####
___

#### 1.4.3. 函数作用使熵变小
给定$X_1,X_2,\cdots ,X_n$为任意的随机变量, $\boldsymbol{g}(X_1,X_2,\cdots ,X_n)$为$X_1,X_2,\cdots ,X_n$的向量值函数, 则有不等式
$$
H(X_1,X_2,\cdots ,X_n)\ge H(\boldsymbol{g}(X_1,X_2,\cdots ,X_n))
$$
成立, 即函数变换不增加原始随机变量的熵. 

#### 1.4.4. 混合使熵变大
概率分布
$$
\boldsymbol{p}_1 = (p_1,\cdots ,p_i,\cdots ,p_j,\cdots, p_m)
$$
的熵小于概率分布
$$
\boldsymbol{p}_2 =\left(p_1,\cdots ,\dfrac{p_i+p_j}{2},\cdots, \dfrac{p_i+p_j}{2},\cdots, p_m\right)
$$
的熵, 即$H(\boldsymbol{p}_1) \le H(\boldsymbol{p}_2)$. 更进一步, 任何使得概率分布更加均匀的变换都会使得熵增加. 

### 1.5. 熵的公理化定义
若对称函数序列$H_m(p_1, p_2, \cdots, p_m)$满足下列性质
1. 标准化: $H_2\left(\dfrac{1}{2}, \dfrac{1}{2}\right) = 1$
2. 连续性: $H_2(p, 1-p)$是$p$的连续函数
3. 组合法则: $H_m(p_1, p_2, \cdots, p_m) = H_{m-1}(p_1 + p_2, p_3, \cdots, p_m) + (p_1+p_2) H_2\left(\dfrac{p_1}{p_1+p_2}, \dfrac{p_2}{p_1+p_2}\right)$

则$H_m$必然具有如下的形式
$$
H_m (p_1, p_2,\cdots, p_m) = - \sum\limits_{i=1}^{m} p_i\log p_i, \quad m=2,3,\cdots
$$
___
##### Proof
我们首先对组合法则进行拓展. 令$\boldsymbol{p} = (p_1, p_2, \cdots, p_m)$且$\boldsymbol{q} = (q_1, q_2, \cdots, q_n)$. 设$p = \sum\limits_{i=1}^{m} p_i$, $q=\sum\limits_{j=1}^{n} q_i$, 其中$p+q=1$. 则我们有
$$
H_{m+n}(\boldsymbol{p}, \boldsymbol{q}) = H_{n+1}(p, \boldsymbol{q}) +  p H_{m}\left(\dfrac{1}{p}\boldsymbol{p}\right) = H_2(p,q) + p H_{m}\left(\dfrac{1}{p}\boldsymbol{p}\right) + q H_{n}\left(\dfrac{1}{q}\boldsymbol{q}\right)
$$

接下来, 令$f(n) = H_n\left(\dfrac{1}{n}, \dfrac{1}{n}, \cdots, \dfrac{1}{n}\right)$, 显然, 
$$
f(mn) = f(m) + f(n)
$$ 
#####
___

## 2. 相对熵
### 2.1. 相对熵的定义
两个概率密度函数为$p(x)$和$q(x)$之间的相对熵或Kullback-Leibler Divergence定义为
$$
D(p\mid\mid q)=\sum_{x\in \mathcal{X}}p(x)\log \dfrac{p(x)}{q(x)}=\mathbb{E}_{p(x)}\log \dfrac{p(x)}{q(x)}
$$ 
可以证明, $D(p\mid\mid q)\ge 0$, 等号成立当且仅当对任意的$x$, 有$p(x)= q(x)$
___
##### Proof 
事实上, 我们有
$$
\begin{aligned} 
      - D(p\mid\mid q) &= -\sum\limits_{x\in A}^{} p(x)\log\dfrac{p(x)}{q(x)} \\ 
      & = \sum\limits_{x\in A}^{} p(x)\log\dfrac{q(x)}{p(x)} \\
      & \le \log\left(\sum\limits_{x\in A}^{} p(x)\dfrac{q(x)}{p(x)}\right) \\
      & = 0 
\end{aligned}
$$
因此$D(p\mid\mid q)\ge 0$, 等号成立当且仅当对任意的$x$, 有$p(x)= q(x)$
#####
___

### 2.2. 条件相对熵(conditional relative entropy)
对于联合概率密度函数$p(x,y)$和$q(x,y)$, 条件相对熵$D(p(y\mid x)\mid\mid q(y\mid x))$定义为条件概率密度$p(y\mid x)$和$q(y\mid x)$之间的平均相对熵, 也就是说
$$
D(p(y\mid x)\mid\mid q(y\mid x))=\sum_{x}p(x)\sum_{y}p(y\mid x)\log \dfrac{p(y\mid x)}{q(y\mid x)}=\mathbb{E}_{p(x,y)}\log\dfrac{p(y\mid x)}{q(y\mid x)}
$$

### 2.3. 相对熵的链式法则
我们可以写出相对熵的链式法则为
$$
D(p(x,y)\mid \mid q(x,y))=D(p(x)\mid \mid q(x))+D(p(y\mid x)\mid\mid q(y\mid x))
$$
___
##### Proof
事实上, 我们有
$$
\dfrac{p(x, y)}{q(x, y)} = \dfrac{p(x)}{q(x)}\dfrac{p(y\mid x)}{q(y\mid x)}
$$
两边取对数
$$
\log\dfrac{p(x, y)}{q(x, y)} = \log\dfrac{p(x)}{q(x)} + \log\dfrac{p(y\mid x)}{q(y\mid x)}
$$
对$p(x,y)$取期望, 可以得到
$$
D(p(x,y)\mid \mid q(x,y))=D(p(x)\mid \mid q(x))+D(p(y\mid x)\mid\mid q(y\mid x))
$$
#####
___

### 2.4. 相对熵的凸性
 $D(p\mid \mid q)$对$(p,q)$是凸的, 即, 如果$(p_1,q_1)$和$(p_2,q_2)$是两个概率密度函数, 则对于任意的$0\le \lambda \le 1$, 我们有
$$
D(\lambda p_1+(1-\lambda)p_2\mid \mid \lambda q_1+(1-\lambda )q_2)\le \lambda D(p_1\mid \mid q_1)+(1-\lambda )D(p_2\mid\mid q_2)
$$
___
##### Proof
将[[../代数学/Chapter 0. 代数不等式/Lecture 1. 基础不等式#2.1. 对数和不等式|对数和不等式]]运用于每一项
$$
(\lambda p_1(x) + (1-\lambda)p_2(x)) \log \dfrac{\lambda p_1(x) + (1-\lambda)p_2(x)}{\lambda q_1(x) + (1-\lambda)q_2(x)} \le \lambda p_1(x) \log \dfrac{p_1(x)}{q_1(x)} + (1-\lambda)p_2(x) \log \dfrac{p_2(x)}{q_2(x)}
$$
对所有的$x$求和, 就得到了相对熵的凸性. 
#####
___

### 2.5. 相对熵的数据处理不等式
如果$X\to Y\to Z$是Markov链, 则
$$
D(p(X)\mid \mid p(Y))\ge D(p(X)\mid \mid p(Z))
$$
此外
$$
D(p(X)\mid \mid p(Y))\ge D(p(Z)\mid \mid p(Y))
$$
___
##### Proof
根据[[#2.3. 相对熵的链式法则]], 我们可以将$D(p(x\mid y)p(z\mid y)p(x)\mid \mid p(x, y, z))$用两种方式展开
$$
\begin{aligned}
D(p(x\mid y)p(z\mid y)p(x)\mid\mid p(x,y,z))&=D(p(x\mid y)p(z\mid y)\mid\mid p(x,y\mid z))+D(p(x)\mid\mid p(z))\\
&=D(p(x\mid y)p(z\mid y)\mid\mid p(x,z\mid y))+D(p(x)\mid\mid p(y))\\
\end{aligned}
$$
在给定$Y$的条件下, $X, Z$是条件独立的. 因此$D(p(x\mid y)p(z\mid y)\mid\mid p(x,z\mid y)) = 0$. 这就意味着
$$
D(p(X)\mid\mid p(Y))\ge D(p(X)\mid\mid p(Z))
$$
我们将$D(\cdot\mid\mid \cdot)$两个参数位置互换, 可以得到另一个式子的证明. 
#####
___


### 2.6. Pythageorean不等式(分布的逼近)
对于闭凸集$E\subset \mathcal{P}$以及分布$Q\notin E$, 设$P^*\in E$是与$Q$的距离达到最小值的分布, 也就是说
$$
D(P^*\mid \mid Q)=\min_{P\in E}D(P\mid \mid Q)
$$
则对于任意的$P\in E$, 我们有
$$
D(P \| Q) \geq D\left(P \| P^{*}\right)+D\left(P^{*} \| Q\right)
$$
该定理的主要用途是, 假定有一列$P_n\in E$使得$D(P_n\mid \mid Q)\to D(P^*\mid \mid Q)$, 则由Pythageorean不等式可知$D(P_n\mid \mid P^*)\to 0$.
___
##### Proof
对任意的$P\in E$, 设
$$
P_{\lambda} = \lambda P + (1-\lambda) P^*
$$
则当$\lambda \to 0$时, $P_{\lambda}\to P^*$. 又因为$E$是凸集, 则对于任意的$\lambda\in [0,1]$, $P_{\lambda}\in E$. 因为$D(p^*\mid\mid Q)$为$D(P_{\lambda}\mid \mid Q)$沿路径$P^*\to P$上的最小值, 从而$D_{\lambda}=D(P_{\lambda}\mid \mid Q)$关于$\lambda$的导数在$\lambda = 0$的时候非负. 
$$
\frac{\mathrm{d} D_{\lambda}}{\mathrm{d} \lambda}=\sum\left(\left(P(x)-P^{*}(x)\right) \log \frac{P_{\lambda}(x)}{Q(x)}+\left(P(x)-P^{*}(x)\right)\right)
$$
令$\lambda=0$, 可以得到
$$
\left(\frac{\mathrm{d} D_{\lambda}}{\mathrm{d} \lambda}\right)_{\lambda=0}=D(P \| Q)-D\left(P \| P^{*}\right)-D\left(P^{*} \| Q\right)\ge 0
$$
这就证明了Pythageorean不等式.
#####
___

### 2.7. Pinsker不等式(相对熵收敛蕴含范数收敛)
设$P_1,P_2$是两个概率分布, 则有
$$
D(P_1\mid\mid P_2)\ge \dfrac{1}{2}\|P_1-P_2\|_1^2
$$ 
Pinsker不等式意味着相对熵的收敛性蕴含$\mathcal{L}_1$范数的收敛性
___
##### Proof
从简单的情形出发. 先证明两个伯努利分布的情况. 令
$$f(q)=p\log\dfrac{p}{q}+(1-p)\log\dfrac{1-p}{1-q}-2(p-q)^2
$$
对$q$求导可以得到
$$
f^{\prime} =-\dfrac{p}{q}+\dfrac{1-p}{1-q}-4(q-p)=(q-p)\left(\dfrac{1}{q(1-q)}-4\right)
$$
于是当$q\in (0,p]$时, $f$单调递减, 而$q\ge p$时, $f$单调递增. 因此$f$的最小值在$q=p$处取到. 

而当$p=q$时, 我们有$f(p)=0$. 因此这也就意味着$f(q)\ge 0, q\in (0,1)$. 这样, 我们就有
$$
p\log\dfrac{p}{q}+(1-p)\log\dfrac{1-p}{1-q}\ge 2(p-q)^2
$$
对于一般的情形, 考虑两个任意的分布$P_1, P_2$, 设
$$
A=\{x \mid P_1(x)>P_2(x)\}
$$
定义一个新的二元随机变量$Y=\phi(X)$为$A$的示性函数. 设$\hat{P}_1$和$\hat{P}_2$构成$Y$的分布. 利用[[../代数学/Chapter 0. 代数不等式/Lecture 1. 基础不等式#2.1. 对数和不等式|对数和不等式]], 可以得到
$$
\begin{aligned} 
      D(P_1\mid\mid P_2) &= \sum\limits_{x\in A}  P_1(x)\log \dfrac{P_1(x)}{P_2(x)} + \sum\limits_{x\notin A}  P_1(x)\log \dfrac{P_1(x)}{P_2(x)} \\ 
      & \ge \left(\sum\limits_{x\in A}  P_1(x)\right)\log \dfrac{\sum\limits_{x\in A}  P_1(x)}{\sum\limits_{x\in A}  P_2(x)} + \left(\sum\limits_{x\notin A}  P_1(x)\right)\log \dfrac{\sum\limits_{x\notin A}  P_1(x)}{\sum\limits_{x\notin A}  P_2(x)} \\ 
      & = P_1(A)\log \dfrac{P_1(A)}{P_2(A)} + (1-P_1(A))\log \dfrac{1-P_1(A)}{1-P_2(A)} \\
      & = D(\hat{P}_1\mid\mid \hat{P}_2) \\
      & \ge 2(P_1(A)-P_2(A))^2 \\
      & = 2\|P_1-P_2\|_1^2
\end{aligned}
$$
#####
___




## 3. 互信息(mutual information)
### 3.1. 互信息的定义
对于任意$n$个随机变量, 
考虑两个随机变量$X$和$Y$, 它们的联合概率密度函数为$p(x,y)$, 其边际概率密度函数分别是$p_X(x)$和$p_Y(y)$. 互信息$I(X,Y)$为联合分布$p(x,y)$和乘积分布$p(x)p(y)$之间的相对熵, 也即
$$
I(X,Y)=\sum_{x\in \mathcal{X}}\sum_{y\in\mathcal{Y}}p(x,y)\log \dfrac{p(x,y)}{p(x)p(y)}=D(p(x,y)\mid \mid p(x)p(y))=\mathbb{E}_{p(x,y)}\log \dfrac{p(x,y)}{p(x)p(y)}
$$
我们可以将互信息写成
$$
I(X,Y)=H(X)-H(X\mid Y)=H(Y)-H(Y\mid X)=H(X)+H(Y)-H(X,Y)
$$
因此, 互信息实际上就是在给定$Y$知识的条件下$X$的不确定度的缩减量, 或者是在给定$X$知识的条件下$Y$的不确定度的缩减量. 

### 3.2. 条件互信息(conditional mutual information)
随机变量$X$和$Y$在给定随机变量$Z$时的条件互信息定义为
$$
I(X,Y\mid Z)=H(X\mid Z)-H(X\mid Y,Z)
$$

### 3.3. 互信息的链式法则
互信息也具有链式法则
$$
I(X_1,X_2,\cdots ,X_n, Y)=\sum_{i=1}^n I(X_i, Y\mid X_{i-1}, X_{i-2},\cdots , X_1)
$$
___
##### Proof
$$
\begin{aligned} 
      I(X_1,X_2,\cdots ,X_n, Y) &= H(X_1, X_2, \cdots, X_n) - H(X_1, X_2, \cdots, X_n \mid Y) \\
      & = \sum\limits_{i=1}^{n} H(X_i\mid X_{i-1}, \cdots, X_1)  - \sum\limits_{i=1}^{n} H(X_i\mid X_{i-1}, \cdots, X_1, Y) \\
      & = \sum_{i=1}^n I(X_i, Y\mid X_{i-1}, X_{i-2},\cdots , X_1)
\end{aligned}
$$
#####
___

### 3.4. 数据处理不等式
若$X\to Y\to Z$为马尔科夫链, 则有
$$
I(X,Y)\ge I(X,Z)
$$
等号成立当且仅当$I(X,Y\mid Z)=0$. 
特别地, 如果$Z=g(Y)$, 则我们可以得到
$$
I(X,Y)\ge I(X,g(Y))
$$
这说明对数据$Y$的变换不会增加和$X$有关的信息量. 

**数据推理的理解**: 不存在对数据的优良操作能够使得从数据中所得到的推理获得改善. 

**数据传输的理解**: 如果$Y$是$X$和$Z$的中间人, 并且$Y$屏蔽了$X$和$Z$之间的通讯. 数据处理不等式表明, 从$X$经过$Y$传给$Z$的信息不可能比从$X$传给$Y$的信息更多. 

___
##### Proof 
根据链式法则, 我们可以将互信息以两种不同的方式展开
$$
I(X; Y; Z) = I(X; Y) + I(X; Z \mid Y) = I(X; Z) + I(X; Y \mid Z)
$$
在给定$Y$的情况下, $X$与$Z$是条件独立的, 因此$I(X; Z \mid Y) = 0$, 由于$I(X; Y; Z) \ge 0$, 所以有
$$
I(X; Y) \ge I(X; Z)
$$
#####
___