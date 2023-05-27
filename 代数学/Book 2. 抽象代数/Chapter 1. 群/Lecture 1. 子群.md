## 1. 子群
### 1.1. 子群的定义
如果群$G$的非空子集合$H$对于$G$的运算也构成一个群, 那么$H$称为$G$的子群. 简记为$H\le G$

### 1.2. 子群的例子
#### 1.2.1. 变换群
对任意的集合$M$, $S(M)$上的子群称为$M$的变换群. 

#### 1.2.2. 交错群
全体偶置换对于置换的乘法构成一个$S_n$的子群, 这个群称为$n$元交错群, 记为$A_n$. 

#### 1.2.3. 平凡子群
在群$G$中, 仅由单位元$e$组成的子集$\{e\}$显然是$G$的一个子群, 群$G$本身也是$G$的一个子群. 这两个子群称为$G$的一个平凡子群. 其余的子群称为非平凡子群. 

#### 1.2.4. 生成子群
在群$G$中, 任意一个元素$a$的全体方幂, 即集合
$$
\{a^m\mid m\in \mathbb{Z}\}
$$
构成一个子群, 这个子群称为由$a$生成的子群. 

### 1.3. 子群的判定
群$G$的非空子集合$H$是一个子群的充分必要条件是, 由$a, b\in H$可以推出$ab^{-1}\in H$. 
___
##### Proof
必要性是显然的, 下面证明充分性. 结合律天然满足, 我们只需要验证单位元, 逆元的存在性以及$H$对乘法运算的封闭性. 我们依次证明$H$中含有单位元, 逆元和对乘法运算的封闭性. 
1. **单位元**: 因为$H$非空, 所以$H$含有一个元素$a$, 于是
   $$
   aa^{-1}=e\in H
   $$
2. **逆元**: 根据$e, a\in H$, 可以得到$a^{-1}\in H$
3. **对乘法运算的封闭性**: 如果$a, b\in H$, 则$b^{-1}\in H$, 于是
   $$
   a(b^{-1})^{-1} = ab \in H
   $$

这就证明了$H$是一个子群. 
#####
___

### 1.4. 生成子群的概念
设$G$是一个群, $S$是$G$的一个非空子集合. 考虑$G$中所有包含$S$的子群. 这些子群的交集仍是一个子群, 它被称为$G$由$S$生成的子群, 记作$\langle S\rangle$. 也就是说
$$
\langle S\rangle=\bigcap_{S\subseteq H\leq G}H.
$$
事实上, 我们有
$$
\langle S\rangle=\left\{\prod_{i=1}^k s_i^{m_i} \mid s_i \in S, k \in \mathbb{N}, m_i \in \mathbb{Z}\right\}
$$


## 2. 模$n$乘法群与原根
### 2.1. 群$U(n)$
在集合 $\mathbb{Z}_n$ 中定义乘法为整数模 $n$ 的乘法, 则 $\mathbb{Z}_n$ 在这个运算下构成一个交换幺半群, 单位元为 1. 此幺半群的所有可逆元构成的群称为整数模 $n$ 的乘法群, 记作 $U(n)$.
$$
U(n) = \{k\in \mathbb{Z}_n\mid \operatorname{gcd}(k, n)=1\}, \quad n\ge 2
$$
整数模$n$的乘法群$U(n)$的阶为$\phi(n)$. 


### 2.2. 群论视角下的几个重要定理
1. **Fermat小定理**: 对任意整数 $a$, 若 $p \nmid a$, 则 
   $$
   a^{p-1} \equiv 1 \mod p
   $$
2. **Wilson定理**: 设$p$为一个素数, 则有
   $$
   (p-1)! \equiv -1 \mod p
   $$
___
##### Proof
1. 考虑群$U(p)$, 这是一个$p-1$阶的循环群, 对任意整数$a$, 若$a$与$p$互素. 从而$a\in U(p)$. 于是我们有, 对任意整数$a$, 若$p\nmid a$, 则
   $$
   a^{p-1} \equiv 1 \mod p
   $$
2. 设$G$为有限交换群, 显然
   $$
   \prod_{g\in G}g  = \prod_{a\in G, o(a)=2}a
   $$
   当$n=p$为素数时, 群$U(p)$有唯一的$2$阶元$-1$. 从而我们得到了
   $$
   (p-1)! \equiv -1 \mod p
   $$
   
#####
___

### 2.3. 原根
若群 $U(n)$ 为循环群, 则称模 $n$ 有原根, 群 $U(n)$ 的生成元称为模 $n$ 的原根. 

模 $n$ 存在原根当且仅当 $n=1,2,4, p^m$ 或 $2 p^m$, 其中 $p$ 为奇素数, $m$ 为任意正整数.
___
##### Proof
证明较长, 我们分为以下的几个部分来证明. 首先证明充分性
1. 当$n=1,2,4$时, 不难验证原根存在
2. 当$n=p$为奇素数时, 用$S(d)$表示群$U(p)$中所有阶为$d$的元素的集合, 则我们有
   $$
   \sum\limits_{d\mid p-1}^{} |S(d)| = p-1 =  \sum\limits_{d\mid p-1} \varphi(d)  \tag{1}
   $$
   考虑同余方程
   $$
   x^d \equiv 1 \mod p
   $$
   其至多有$d$个根. 
   
   如果$S_d\neq \varnothing$, 则$a^d\equiv 1\mod p$, 则我们有$a, a^2, \cdots, a^{p-1}$是该方程互不相同的$d$个根, 因此也是全部根. 于是$a, a^2, \cdots, a^{p-1}$包含了$U(n)$中全部阶为$d$的元素. 显然可以得到此时$|S_d|=\varphi(d)$. 因此我们得到了$|S_d|$的取值只可能是$0$或$\varphi(d)$. 结合$(1)$知道$|S_d|=\varphi(d)$, 因此有$|S_{p-1}|=\varphi(p-1)$. 因此奇素数的原根存在. 
3. 当$n = p^{\alpha}, 2p^{\alpha}$时. 根据$U(2p^{\alpha})\cong U(2)\times U(p^{\alpha})\cong U(p^{\alpha})$, 我们只需要证明$n=p^{\alpha}$的情形. 我们采用数学归纳法, 假设当幂次为$\alpha$的时候成立, 即存在$g$, 使得$U(p^{\alpha}) = \langle g\rangle$. 设$g$在$U(p^{\alpha+1})$中的阶为$r$, 显然有$r\mid \varphi(p^{\alpha+1})$. 又显然有$\varphi(p^{\alpha}) \mid r$. 这意味着$r=\varphi(p^{\alpha})$或$\varphi(p^{\alpha+1})$. 如果$r=\varphi(p^{\alpha})$, 考虑$g+p$. 设$r_1$为$g+p$的阶, 因为
   $$
    \left(g+ p\right)^{p^{\alpha-1}(p-1)} \equiv 1 + (p-1)p^{\alpha}g^{p^{\alpha-1}(p-1)-1}\not\equiv 1 \mod p^{\alpha+1}
   $$
   因此有$r_1 \nmid \varphi(p^{\alpha})$. 又因为$r_1\mid \varphi(p^{\alpha+1})$, 故$r_1 =k p^{\alpha_0}$, 其中$k\mid p-1$. 于是
   $$
   1\equiv (g + ip)^{kp^{\alpha}} \equiv g^{kp^{\alpha}} \mod p^{\alpha+1}
   $$
   因此$(p-1)p^{\alpha-1}\mid kp^{\alpha-1}$. 这意味着$k=p-1$. 故$g$和$g+p$中必然有某一个为$U(p^{\alpha+1})$的原根. 

下面证明必要性. 用反证法, 假设$U(n)$有原根, 但$n$不满足任意题设中的形式. 那么, 一定有
$$
n = 2^{\alpha}(\alpha\ge 3), \quad n = 2^{\alpha}p_1^{\alpha_1}\cdots p_s^{\alpha_s}(\alpha\ge 2, s\ge 1), \quad n = 2^{\alpha}p_1^{\alpha_1}\cdots p_s^{\alpha_s}(\alpha\ge 0, s\ge 2)
$$ 
中的某一个成立. 也就是说
$$
\begin{aligned} 
U(n)&\cong U(2^{\alpha})(\alpha\ge 3)\\ 
 U(n)&\cong U(2^{\alpha})\times U(p_1^{\alpha_1})\times\cdots\times U(p_s^{\alpha_s})(\alpha\ge 2, s\ge 1)\\ 
U(n)& \cong U(2^{\alpha})\times U(p_1^{\alpha_1})\times\cdots\times U(p_s^{\alpha_s})(\alpha\ge 0, s\ge 2)
\end{aligned}
$$
中有一个成立. 显然当$\alpha\ge 3$时, 在$U(2^{\alpha})$中, 任意奇数的阶至多为$2^{\alpha-2}$. 而$2\mid \varphi(p_i^{\alpha_i})$. 无论如何, 都有$U(n)$中的最大阶小于$\varphi(n)$. 这与$U(n)$有原根矛盾. 因此必要性得证.
#####
___

