## 1. 群的同构
### 1.1. 同构
设$G$与$G^{\prime}$是两个群, 如果有一个从$G$到$G^{\prime}$的一一对应$\sigma$, 它对于所有的$x, y\in G$, 有
$$
\sigma(xy) = \sigma(x)\sigma(y)
$$
那么就称$G$同构于$G^{\prime}$, 记为$G\cong G^{\prime}$. 双射$\sigma$称为从$G$到$G^{\prime}$的一个同构映射. 

**自同构**: 群$G$到自身的同构映射称为$G$的一个自同构. 群$G$的所有自同构在映射的复合下构成一个群, 称为$G$的自同构群, 记为$\mathrm{Aut}(G)$.


### 1.2. 同构的性质
群的同构作为群之间的一种关系, 具有如下性质:
1. **反身性**: $G\cong G$
2. **对称性**: $G\cong G^{\prime}\Longrightarrow G^{\prime}\cong G$
3. **传递性**: $G\cong G^{\prime}, G^{\prime}\cong G^{\prime\prime} \Longrightarrow G\cong G^{\prime\prime}$

这是一个等价关系. 

### 1.3. 同构的例子
#### 1.3.1. 可逆线性变换和一般线性群
设$V$是数域$\mathbb{F}$上的$n$维线性空间. $V$上全体可逆线性变换的群$\mathrm{GL}(V)$与一般线性群$\mathrm{GL}_n(\mathbb{F})$是同构的. 
#### 1.3.2. 整数加法群与整数群
对于$n\in \mathbb{Z}$, 记$n\mathbb{Z} = \{nk\mid k\in \mathbb{Z}\}$, 容易验证$n\mathbb{Z}$是$\mathbb{Z}$的子群. 而
$$
\sigma: \mathbb{Z} \to n\mathbb{Z},\quad\sigma(k) = nk
$$
是一个同构. 

### 1.4. Cayley定理
任何一个群都同构于某一集合上的变换群
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
根据[[#2.3. 子群的判定]], $G_l$是一个变换群. 显然, $a\mapsto\sigma_a$是$G\mapsto G_l$的一个一一对应. 其满足
$$
\sigma_{ab} = \sigma_a\sigma_b
$$
这样, 我们就证明了$G\cong G_l$.
#####
___

### 3.4. 平移与正则表示
我们称$\sigma_a$为由元素$a$在$G$上引起的左平移. 而变换群$G_l$称为群$G$的左正则表示. 同样地, 我们可以定义右平移和右正则表示. 
$$
\tau_a(x) = xa^{-1}, \quad G_{\tau} = \{\tau_a\mid a\in G\}
$$

## 2. 同态
### 2.1. 同态
设$G$与$G^{\prime}$是两个群, $\sigma$是群$G$到群$G^{\prime}$的一个映射, 如果$\sigma$适合条件
$$
\sigma(xy) = \sigma(x)\sigma(y), \quad x, y\in G
$$
那么$\sigma$就称为从$G$到$G^{\prime}$的一个同态映射, 或同态. 

### 2.2. 同态的反像
对于同态$\sigma: G\to G^{\prime}$, 对于任意的$a^{\prime}\in G^{\prime}$, 我们考虑集合
$$
\{x\in G\mid \sigma(x) = a^{\prime}\}
$$
我们称这个集合为元素$a^{\prime}$的完全反像, 记为$\sigma^{-1}(a^{\prime})$. 

特别地, 单位元素的完全反像$\sigma^{-1}(e^{\prime})$称为同态$\sigma$的核, 记为$\ker(\sigma)$. $\sigma$是单同态当且仅当$\ker(\sigma) = \{e\}$.

### 2.3. 核可以导出完全反像
设$\ker(\sigma) = H$, 可以证明, 如果$\sigma(a)=a^{\prime}$, 那么
$$
\sigma^{-1}(a^{\prime}) = aH = H a,\quad \forall a\in G
$$

