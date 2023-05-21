

## 5. 正规子群
### 5.1. 正规子群
设$H$是$G$的子群, 如果对于所有的元素$a\in G$, 都有$aH = Ha$, 那么$H$称为$G$的正规子群, 记为$H\triangleleft G$. 正规子群的定义可以改写为
$$
aH a^{-1} = H, \quad \forall a\in G
$$
显然, 在交换群中, 每一个子群都是正规的. 并且, 同态的核都是正规子群. 

### 5.2. 正规子群的判定(陪集)
设$H$是群$G$的一个子群, $H$是正规子群的充要条件是, 任意两个左(右)陪集的积仍然还是一个左(右)陪集
___
##### Proof
首先证明必要性, 若$H$是一个正规子群, $aH, bH$是两个左陪集, 则我们有
$$
aHbH = abHH = abH
$$
仍然是一个左陪集.

下面证明必要性, 设$aH, bH$是任意两个左陪集, 根据条件
$$
(aH) \cdot (bH) = cH
$$
显然我们有$ab\in (aH) \cdot (bH)$, 因此$ab\in cH$. 于是我们有
$$
(aH) \cdot (bH) = abH
$$
这样, 用$a^{-1}$左乘上式, 我们有
$$
HbH = bH
$$
这就证明了$Hb\subset bH$. 也就是说
$$
bHb^{-1} \subset H,\quad \forall b\in G
$$
将$b$换成$b^{-1}$, 可以得到
$$
bHb^{-1} \supset H,\quad \forall b\in G
$$
结合两个式子, 我们有
$$
bHb^{-1} =  H,\quad \forall b\in G
$$
这就证明了$H$是一个正规子群.
#####
___

### 5.3. 商群
设$G / H$表示正规子群$H$的所有不同右陪集组成的集合. $G / H$在陪集运算下构成一个群, 我们称这个群为群$G$对正规子群$H$的商群.  

### 5.4. 群同态基本定理
设$\sigma: G\to G^{\prime}$是一个满同态, $N$为$\sigma$的核, 则$G / N$与$G^{\prime}$同构
___
##### Proof
设$\varphi(a) = Ha$是$G\to G / N$上的自然同态. 定义
$$
\psi(Na) = \sigma(a)
$$
因为$\sigma$是满同态, 即$\sigma(G) = G^{\prime}$. 所以我们有$\psi$是$G / N\to G^{\prime}$的一个一一对应. 而
$$
\psi(NaNb) = \psi(NNab) = \psi(Nab) = \sigma(ab) = \sigma(a)\sigma(b) = \psi(Na)\psi(Nb)
$$
也就是说$\psi: G / N\to G^{\prime}$是一个同构. 从$\psi$的定义可以看出$\psi\varphi = \sigma$. 
#####
___


