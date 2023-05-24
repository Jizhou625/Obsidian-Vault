## 1. 置换
### 1.1. 置换、对换和轮换
1. **置换**: 当$M$含有$n$个元素时, $M$的可逆变换称为$n$元置换. 事实上, 任一 $\sigma \in S_n$ 可以写为
   $$
   \sigma= \left(\begin{array}{cccc}
   l_1 & l_2 & \cdots & l_n \\
   \sigma\left(l_1\right) & \sigma\left(l_2\right) & \cdots & \sigma\left(l_n\right)
   \end{array}\right)
   $$
   其中 $l_1, l_2 \cdots, l_n$ 是 $1,2, \cdots, n$ 的一个排列.
2. **对换**: 设 $n \geq 2, \sigma \in S_n$, 若满足 $\sigma(i)=j, \sigma(j)=i$, 且对任意 $k \in[n] \backslash\{i, j\}$ 有 $\sigma(k)=k$, 即 $\sigma$ 把 $[n]$ 中元素 $i, j$ 互换而把其它元素保持不动, 则称 $\sigma$ 为一个对换, 记作 $(i j)$.
3. **轮换**: 如果一个$n$元置换$\sigma$将$1,2,\cdots, n$中某$m$个数$\alpha_1, \cdots, \alpha_m$轮换, 即
   $$
   \sigma(\alpha_1)=\alpha_2, \sigma(\alpha_2) = \alpha_3, \cdots, \sigma(\alpha_m) = \alpha_1
   $$
   而保持其他的数不变, 那么$\sigma$称为一个轮换. 我们简单地用
   $$
   \sigma = (\alpha_1\alpha_2\cdots\alpha_m)
   $$
   来表示这个轮换. 


### 1.2. 置换的轮换分解
任何一个非单位的置换都可以表示为一些不相交的轮换的乘积, 而且在不考虑轮换因子的次序的意义下, 其表示法是唯一的.  
___
##### Proof:
设$\sigma$时一个$n$元置换, 在$1,2,\cdots, n$中任取一个元素$\alpha_1$, 用$\sigma$连续作用, 得到
$$
\alpha_2 = \sigma(\alpha_1), \quad \alpha_3 = \sigma(\alpha_2),\quad \cdots
$$
由于$\alpha_i\in\{1,2,\cdots, n\}$, $i=1,2,\cdots$, 所以序列中出现的元素必然有相同的, 设$\alpha_j$为序列
$$
\alpha_1, \alpha_2,\cdots
$$
中第一个重复出现的元素, 不妨设$\alpha_i = \alpha_j(i<j)$. 显然可以得到$i=1$. 也就是说
$$
\alpha_2 = \sigma(\alpha_1), \quad \alpha_3 = \sigma(\alpha_2), \quad \cdots, \quad \sigma(\alpha_{j-1}) = \alpha_1
$$
$\sigma$在元素$\alpha_1, \alpha_2, \cdots, \alpha_{j-1}$上成一个轮换. 我们再在$\alpha_1, \alpha_2, \cdots, \alpha_{j-1}$之外取一个元素, 重复上述讨论. 于是又得到一个轮换. 根据$\{1,2,\cdots,n\}$是有限的. 所以$\sigma$可以被分解为有限多个轮换的乘积. 
#####
___


### 1.3. 奇置换和偶置换
设 $n$ 元置换 $\sigma=\left(\begin{array}{cccc}1 & 2 & \cdots & n \\ l_1 & l_2 & \cdots & l_n\end{array}\right)$, 若排列 $l_1 l_2 \cdots l_n$ 为奇排列(即逆序数为奇数), 则称 $\sigma$ 为奇置换, 否则称为偶置换. 

对任意 $n \geq 2, S_n$ 中奇偶置换各占一半, 即均为 $\dfrac{1}{2} n!$ 个. 长度为奇数的轮换是偶置换, 长度为偶数的轮换是奇置换. 


根据[[#4.2. 置换的轮换分解]], 可以得到$n$元置换$\sigma$为偶置换当且仅当把$\sigma$写成互不相交的轮换乘积时, 出现的长度为偶数的轮换的个数为偶数.

### 1.4. 偶置换的$3$-轮换表示
每一个偶置换都可以表示为一些长度为$3$的轮换的乘积
___
##### Proof
根据线性代数知识, 我们首先可以得到, 每一个置换都可以表示为一些对换的乘积. 而每一个偶置换都可以表示为偶数个对换的乘积. 我们只需要证明任意两个不同的对换的乘积一定可以表示为$3$-轮换的乘积即可. 设$i, j,k,l$为四个不同的数, 我们有
$$
\begin{aligned} 
   (ij)(ik) &= (ijk) \\
   (ij)(kl) &= (ij)(jk)(jk)(kl) = (jki)(klj) \\
\end{aligned}
$$
这就完成了证明
#####
___

### 1.5. 置换的型
设把 $\sigma$ 写成不相交轮换的乘积, 其中长为 $i$ 的轮换出现 $\ell_i$ 次, $1 \leq i \leq n$, 则称 $\sigma$ 的型为 $\left(\ell_1, \ell_2, \cdots, \ell_n\right)$. 

显然 $\ell_1+2 \ell_2+\cdots+n \ell_n=n$, 且每个 $\ell_i$ 为非负整数.

## 2. 共轭

### 2.1. 共轭的定义
对于 $\rho, \sigma \in S_n$, 称 $\rho \sigma \rho^{-1}$ 为用 $\rho$ 对 $\sigma$ 做共轭变换，称 $\rho \sigma \rho^{-1}$ 为 $\sigma$ 的共轭元. 显然
$$
\rho \sigma \rho^{-1}=\left(\begin{array}{cccc}
\rho(1) & \rho(2) & \cdots & \rho(n) \\
\rho(\sigma(1)) & \rho(\sigma(2)) & \cdots & \rho(\sigma(n))
\end{array}\right)
$$

### 2.2. 置换的共轭
$k$ 长轮换的共轭元仍为 $k$ 长轮换, 也就是说
$$
\rho\left(\alpha_1 \alpha_2 \cdots \alpha_k\right) \rho^{-1}=\left(\rho\left(\alpha_1\right) \rho\left(\alpha_2\right) \cdots \rho\left(\alpha_k\right)\right)
$$ 

若 $\sigma=\left(\alpha_1 \alpha_2 \cdots \alpha_k\right) \cdots\left(\beta_1 \beta_2 \cdots \beta_t\right)$ 为不相交轮换的乘积, 则 
$$
\rho \sigma \rho^{-1} = \left(\rho\left(\alpha_1\right) \rho\left(\alpha_2\right) \cdots \rho\left(\alpha_k\right)\right) \cdots\left(\rho\left(\beta_1\right) \rho\left(\beta_2\right) \cdots \rho\left(\beta_t\right)\right) 
$$
仍为不相交轮换的乘积. 因此共轭的两个置换具有相同的型, 反之亦然.