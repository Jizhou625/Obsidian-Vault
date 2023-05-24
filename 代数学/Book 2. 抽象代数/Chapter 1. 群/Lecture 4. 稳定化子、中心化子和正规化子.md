## 1. 稳定化子
### 1.1. 稳定化子的定义
设群$G$作用在集合$M$上, 对于$x\in M$, 定义
$$
G_x = \{g\in G\mid g(x) = x\}
$$
称它是群$G$作用下$x$的稳定化子, 容易验证$G_x$是$G$的子群. 

更一般地, 我们可以定义某个集合的稳定化子, 设$H\in M$, 则集合$H$的稳定化子为
$$
G_H = \{g\in G\mid g(H) = H\}
$$
其中$g(H)$定义为
$$
g(H) = \{g(x)\mid x\in H\}
$$

### 1.2. 轨道和稳定化子
设$G$为有限群, $G$作用在集合$M$上, 则过$x$的轨道$O_x$的长度等于$G_x$在$G$中的指数, 即
$$
|O_x| = [G: G_x] = \dfrac{|G|}{|G_x|}
$$
此外, 同一轨道上的两个元素的稳定化子是共轭的. 也就是说, 若$y\in O_x$, 则存在$g\in G$, 使得$G_y = gG_xg^{-1}$.
___
##### Proof
定义
$$
\phi: O_x\to (G/G_x)_l, \quad \phi(g(x)) = gG_x
$$
容易验证这是一个一一对应, 于是$|O_x|=[G:G_x]$

若$y\in O_x$, 则存在$g\in G$, 使得$y=g(x)$. 任取$h\in G_x$, 则有
$$
(ghg^{-1})(y) = (ghg^{-1})(g(x)) = g(x) = y
$$
也就是说, $(ghg^{-1})\in G_y$, 这意味着$gG_xg^{-1}\subseteq G_y$. 同理, 可以得到$gG_xg^{-1}\supseteq G_y$. 这就证明了$gG_xg^{-1} =  G_y$
#####
___

### 1.3. Burnside引理
设$G$作用在集合$M$上, 对于$g\in G$, 用$\psi(g) = \{x\in M\mid gx=x\}$表示被$g$固定的$M$中元素的集合, 则$G$作用的轨道个数是
$$
\dfrac{1}{|G|}\sum_{g\in G}|\psi(g)|
$$
___
##### Proof
计算有序对$(g,x)$的个数, 其中$g\in G, x\in M$并且$gx=x$. 一方面, 这个数为$\sum\limits_{g\in G}^{} |\psi(g)|$. 另一方面, 对于$x\in M$, 有$|G_x|$个$g\in G$使得$gx=x$, 于是这个数为$\sum\limits_{x\in M}^{} |G_x|$. 由于$|O_x|= \dfrac{|G|}{|G_x|}$, 所以
$$
\sum_{g \in G}|\psi(g)|=\sum_{x \in M}\left|G_x\right|=|G| \sum_{x \in M} \frac{1}{\left|O_x\right|}
$$
又因为$G$的轨道划分了$M$并且$\sum\limits_{y \in O_x} \dfrac{1}{\left|O_y\right|}=1$. 所以$\sum\limits_{x\in M}^{} \dfrac{1}{|O_x|}$为轨道的个数. 
#####
___

## 2. 正规化子
### 2.1. 正规化子
若$H\le G$, 则对任意的$g\in G$, $gHg^{-1}$称为$H$的一个共轭子群, 令$M_H = \{gHg^{-1}\mid g\in G\}$为$H$的所有共轭子群的集合. 对于$H\in M_H$, $H$的稳定化子为
$$
N_G(H) = \{g\in G\mid gHg^{-1}=H\}
$$
也称为$H$关于$G$的正规化子. 显然, $N_G(H)\le G$也是一个子群. 

### 2.2. 正规子群
设$H$为群$G$的子群, 如果对任意的$g\in G$, 都有$gH=Hg$. 那么称$H$为$G$的正规子群, 记为$H\triangleleft G$. 

$H\triangleleft G$等价于对任意的$g\in G$, 有
$$
gHg^{-1} = H
$$
$H\triangleleft G$也等价于, 对任意的$g\in G$, $h\in H$, 都有
$$
ghg^{-1} \in H
$$
显然, 对任意的$H\le G$, 都有$H\triangleleft N(H)$


### 2.3. 商群
设$H\triangleleft G$, 在集合$G/H$上定义运算如下
$$
(g_1H)(g_2H) = (g_1g_2)H
$$
容易验证$G/H$在上面定义的运算下构成一个群. 称$G/H$为群$G$关于正规子群$H$的商群. 

## 3. 中心化子
### 3.1. 共轭类
$G$ 为有限群, 当$G$在$G$上的作用是共轭变换时, 此作用的轨道称为 $G$ 的共轭类, 含元素 $x \in G$ 的共轭类记为 $C_x$, 即
$$
C_x=\left\{g x g^{-1} \mid g \in G\right\}
$$

### 3.2. 中心化子与中心
对于$x\in G$, $x$在$G$的共轭作用下的稳定化子称为$x$在$G$中的中心化子, 记为$C_G(x)$, 即
$$
C_G(x) = \{g\in G\mid gxg^{-1}=x\} = \{g\in G\mid gx=xg\}
$$
设
$$
Z(G) = \bigcap\limits_{x\in G} C_G(x) = \{g\in G\mid gx=xg,\ \forall x\in G\}
$$
称$Z(G)$为群$G$的中心. $Z(G)$是与$G$中所有元素都可交换的$G$中元素组成的集合, $Z(G)$是$G$的子群. 

### 3.3. 类方程
共轭类的类长$|C_x|$等于$C_G(x)$在$G$中的指数, 也就是说
$$
|C_x| = [G: C_G(x)]
$$
设$G$中互不相同的共轭类为$C_{x_1}, C_{x_2}, \cdots, C_{x_n}$, 则
$$
|G| = \sum_{i=1}^n |C_{x_i}| = \sum_{i=1}^n [G: C_G(x_i)]
$$
这称为$G$的类方程. 

由于$Z(G)$中的每个元素恰含一个元素的共轭类. 因此类方程可以写成
$$
|G|=|Z(G)|+\sum_{i=1}^m\left[G: C_G\left(y_i\right)\right] ,\quad y_i \notin Z(G)
$$

### 3.4. $G / Z$定理
设$Z(G)$为群$G$的中心, 若$G / Z(G)$是循环群, 则$G$是交换群. 
___
##### Proof
设$G/Z(G) = \langle g Z(G)\rangle$. 对于任意的$a, b\in G$, 存在整数$i, j$, 使得
$$
aZ(G) = (gZ(G))^i = g^iZ(G),\quad bZ(G) = (gZ(G))^j = g^jZ(G)
$$
所以存在$x, y\in Z(G)$, 使得$a = g^i x$, $b=g^j y$, 故
$$
ab = g^i x g^j y = g^j y g^i x = ba
$$
#####
___

### 3.5. $p^2$阶群交换
设$p$为素数, 则$p^2$阶群是交换群
___
##### Proof
根据类方程, 可以得到$p\mid Z(G)$, 因此$|Z(G)| = p^2$或者$|Z(G)|=p$. 无论是哪一种情况, $G / Z(G)$都是循环群, 因此$G$是交换群.
#####
___