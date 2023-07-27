## 1. 群的同构
### 1.1. 同构的定义
设$G$与$G^{\prime}$是两个群, 如果有一个从$G$到$G^{\prime}$的一一对应$\sigma$, 它对于所有的$x, y\in G$, 有
$$
\sigma(xy) = \sigma(x)\sigma(y)
$$
那么就称$G$同构于$G^{\prime}$, 记为$G\cong G^{\prime}$. 双射$\sigma$称为从$G$到$G^{\prime}$的一个同构映射. 



### 1.2. 同构的性质
群的同构作为群之间的一种关系, 具有如下性质:
1. **反身性**: $G\cong G$
2. **对称性**: $G\cong G^{\prime}\Longrightarrow G^{\prime}\cong G$
3. **传递性**: $G\cong G^{\prime}, G^{\prime}\cong G^{\prime\prime} \Longrightarrow G\cong G^{\prime\prime}$

因此同构是一个等价关系. 

### 1.3. 同构的例子
#### 1.3.1. 可逆线性变换群和一般线性群
设$V$是数域$\mathbb{F}$上的$n$维线性空间. $V$上全体可逆线性变换的群$\mathrm{GL}(V)$与一般线性群$\mathrm{GL}_n(\mathbb{F})$是同构的. 
#### 1.3.2. 整数加法群与整数群
对于$n\in \mathbb{Z}$, 记$n\mathbb{Z} = \{nk\mid k\in \mathbb{Z}\}$, 容易验证$n\mathbb{Z}$是$\mathbb{Z}$的子群. 而
$$
\sigma: \mathbb{Z} \to n\mathbb{Z},\quad\sigma(k) = nk
$$
是一个同构. 
#### 1.3.3. Cayley定理(变换群)
任何一个群都同构于某一集合上的变换群. 对于任意的群$G$, 定义集合$G$上的变换群为
$$
G_l = \{\sigma_a\mid a\in G\}, \quad \sigma_a(x) = ax, x\in G
$$
则$G\cong G_l$
___
##### Proof
设$G$是一个群, 对于每个$a\in G$, 我们定义集合$G$上的变换$\sigma_a$如下
$$
\sigma_a(x) = ax, \quad x\in G
$$
我们先证明$\sigma_a(x)$是$G$上的一个可逆变换. 事实上, 我们有
$$
\begin{aligned} 
   \sigma_{a^{-1}} \sigma_a (x) = \sigma_{a^{-1}}(ax) = a^{-1}ax = x \\
   \sigma_a \sigma_{a^{-1}} (x) = \sigma_a(a^{-1}x) = aa^{-1}x = x
\end{aligned}
$$
因此我们有
$$
\sigma_a^{-1} = \sigma_{a^{-1}}
$$
因此, $\sigma_a$是可逆变换. 这样, 我们就得到了集合$G$的一些可逆变换组成的集合
$$
G_l = \{\sigma_a\mid a\in G\}
$$
对于$\sigma_a, \sigma_b\in G_l$, 有
$$
\sigma_a \sigma_b^{-1}(x) = \sigma_{ab^{-1}}(x) \in G_l
$$
根据[子群的判定的判定定理](Lecture%201.%20子群#1.3.%20子群的判定), $G_l$是一个变换群. 显然, $a\mapsto\sigma_a$是$G\to G_l$的一个一一对应. 其满足
$$
\sigma_{ab} = \sigma_a\sigma_b
$$
这样, 我们就证明了$G\cong G_l$.
#####
___

### 1.4. 自同构群
群$G$到自身的同构映射称为$G$的一个自同构. 群$G$的所有自同构在映射的复合下构成一个群, 称为$G$的自同构群, 记为$\mathrm{Aut}(G)$.

设$G$为群, 对于任意的$g\in G$, 映射$\sigma_g: x\mapsto gxg^{-1}$是群$G$的一个自同构, 这样的自同构称为$G$的自内同构, 其构成的群称为$G$的自内同构群, 记为$\mathrm{Inn}(G)$.


## 2. 同态
### 2.1. 同态
设$G$与$G^{\prime}$是两个群, $\sigma$是群$G$到群$G^{\prime}$的一个映射, 如果$\sigma$适合条件
$$
\sigma(xy) = \sigma(x)\sigma(y), \quad x, y\in G
$$
那么$\sigma$就称为从$G$到$G^{\prime}$的一个同态映射, 或同态. 

### 2.2. 完全反像
对于同态$\sigma: G\to G^{\prime}$, 对于任意的$a^{\prime}\in G^{\prime}$, 我们考虑集合
$$
\{x\in G\mid \sigma(x) = a^{\prime}\}
$$
我们称这个集合为元素$a^{\prime}$的完全反像, 记为$\sigma^{-1}(a^{\prime})$. 

特别地, 单位元素的完全反像$\sigma^{-1}(e^{\prime})$称为同态$\sigma$的核, 记为$\ker(\sigma)$. 



## 3. 同构定理
### 3.1. 同构第一定理(同态基本定理)
设$G, G^{\prime}$是两个群, $\pi: G\to G^{\prime}$是群同态. 则
$$
G / \ker \pi \cong \pi(G)
$$
这说明了同态象一定同构于$G$的某个商群
___
##### Proof
设$K = \ker \pi$, 根据[同态核都是正规子群](Lecture%204.%20稳定化子、中心化子和正规化子#2.3.1.%20同态核都是正规子群), 我们有$K\triangleleft G$. 做映射
$$
\pi_1: G/K \to \pi(G), \quad \pi_1(gK) = \pi(g)
$$
不难验证$\pi_1$是双射. 

任意取定$g_1K, g_2K\in G / K$, 则我们有
$$
\pi_1(g_1K g_2 K) = \pi_1(g_1g_2K) = \pi(g_1g_2) = \pi(g_1)\pi(g_2) = \pi_1(g_1K)\pi_1(g_2K)
$$
这就得到了$\pi_1$是一个群同构, 从而
$$
G / \ker \pi \cong \pi(G)
$$
#####
___