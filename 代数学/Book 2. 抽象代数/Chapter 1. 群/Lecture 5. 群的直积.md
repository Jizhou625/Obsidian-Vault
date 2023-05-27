## 1. 直积
### 1.1. 直积的概念
设$G_1, G_2$为群, 则$G_1, G_2$(作为集合)的乘积
$$
G = G_1 \times G_2 = \{(g_1, g_2)\mid g_1\in G_1, g_2\in G_2\}
$$
在运算
$$
(g_1, g_2) \cdot (h_1, h_2) = (g_1h_1, g_2h_2)
$$
下构成群, 称为群$G_1$和$G_2$的直积.

### 1.2. 直积的判定
设$G$为群, $H, K$为$G$的两个子群, 且满足
1. $G = HK$
2. $H\cap K = \{e\}$
3. $H$中的每个元素与$K$中的每个元素可交换
   
则$G\cong H\times K$. 称群$G$为它的子群$H$与$K$的内直积. 习惯上也可以记$G = H\times K$
___
##### Proof
考虑映射
$$
\sigma: H\times K \to G, \quad \sigma(h, k) = hk
$$
根据条件1得到, $\sigma$为满射. 若$\sigma(h_1, k_1) = \sigma(h_2, k_2)$, 则有$h_2^{-1}h_1 = k_2 k_1^{-1}\in H\cap K$. 根据条件2可以得到, $h_2^{-1}h_1 = k_2 k_1^{-1} = e$, 即$h_1 = h_2, k_1 = k_2$. 因此$\sigma$为单射. 由此可知$\sigma$为双射. 进一步, 根据3, 我们有
$$
\sigma((h_1, k_1)(h_2, k_2)) = \sigma(h_1h_2, k_1k_2) = h_1h_2k_1k_2 = h_1k_1h_2k_2 = \sigma(h_1, k_1)\sigma(h_2, k_2)
$$
因此$\sigma$保持运算. 这就证明了同构. 
#####
___


## 2. 半直积
### 2.1. 半直积
设$A, B$是两个群, $\theta: B\to \mathrm{Aut}(A)$为群同态, 在集合$A\times B$上定义运算如下
$$
(a, b)(a^{\prime}, b^{\prime}) = (a\theta(b)(a^{\prime}), bb^{\prime})
$$
则它成为一个群, 称为群 $A$ 和 $B$ (关于 $\theta$) 的半直积, 记为 $A \rtimes_\theta B$.

### 2.2. 半直积的性质
$A$ 同构于 $A \rtimes_\theta B$ 的一个正规子群, $B$ 同构于 $A \rtimes_\theta B$ 的一个子群.
___
##### Proof
显然, $A\times \{e\}$是$A\rtimes_\theta B$的一个正规子群, 且$A\cong A\times \{e\}$. 

对于$B$
#####
___
