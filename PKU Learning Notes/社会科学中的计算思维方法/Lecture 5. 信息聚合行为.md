## 1. 外生事件的市场
### 1.1. 什么是外生事件的市场
外生事件的市场是指选择的好坏不受到行动参与者的影响的市场. 博彩市场和总统大选都是外生事件市场

### 1.2. 预测市场
预测市场中的商品通常都是简单的，一般是特别设计出来以聚合人们关于一个未来事件的预测，以形成市场的一个观点. 在一个预测市场中，参与者在某个事件的结果上下注. 

### 1.3. 效用评估
特别地, 我们取效用函数为对数函数, 对数效用具有一个简单的性质, 无论一个人当前的财富时多少, 财富翻倍对他的效用总是一致的. 

### 1.4. 下注策略
设$A$和$B$的赔付率分别为$O_A$和$O_B$, 假设赌客的财富总量为$w$, 在$A$上投放的财富的份额为$r$, 若$A$取胜, 它将拥有财富$rwO_A$. 赌客相信$A$取胜的概率为$a$, $B$取胜的概率为$1-a$. 则赌客在赌局结束后的期望效用为
$$
a\ln(rwO_A) + (1-a)\ln((1-r)wO_B)
$$
当$r=a$时, 期望效用最大, 这意味着赌客应该用他的信念作为下注策略. 

### 1.5. 赔付率的确定
赔付率即为赌场为赌客正确下注一块钱所需要支付的钱数. 赔付率的倒数被称为状态价格, 即赌客为了得到一块钱的回报所需要正确下注的钱数. 当采用无成本和非盈利假设时, 状态价格应该是赌客信念的加权平均, 权重即为赌客$n$的财富在总财富中的份额$f_n$. 
___
##### Proof
如果$A$获胜, 赛马场欠赌客$n$的钱就是$a_nw_nO_A$. 对于所有赌客求和就是
$$
w = \sum\limits_{i=1}^{N}a_iw_iO_A 
$$
令$f_i = \dfrac{w_i}{w}$, 则我们有
$$
a_1f_1+a_2f_2+\cdots + a_nf_n = \dfrac{1}{O_A}
$$ 
同理, 我们有
$$
(1-a_1)f_1+(1-a_2)f_2+\cdots + (1-a_n)f_n = \dfrac{1}{O_B}
$$
#####
___

### 1.6. 群众智慧
从市场长期的历史来看, 尽管每个人掌握的信息都是有限的, 但许多人的聚合行为可以产生非常准确的信念. 如果群众中对$A$的取胜概率的观点来自于一个独立分布, 均值等于$A$取胜的真实概率. 并且如果财富的份额时相等的, 那么状态价格随着群众规模的扩大收敛到真实的概率. 

### 1.7. 群众智慧的局限性
1. 级联的形成可能会影响群众观点的独立性
2. 财富分配不均匀可能会使得每个信念的权重不相同


## 2. 内生事件的市场
### 2.1. 信息不对称
在许多买卖双方有互动的情形中, 市场的一方对交易的货物或服务比另一方有更好的信息. 

### 2.2. 市场的财富动力学
一开始, 贝叶斯学习者不知道 $A$ 和 $B$ 取胜的概率, 他要通过多次观察比赛的情况来获得这两个参数。从 $N$ 个可能的概率假设开始 $\left(a_1, b_1\right),\left(a_2, b_2\right), \cdots,\left(a_N, b_N\right)$. 学习者从一个先验概率$\boldsymbol{f}$开始, 最初学习者预测$A$取胜的概率为
$$
a_1f_1+a_2f_2+\cdots + a_Nf_N
$$
用$\boldsymbol{s}$表示观察到的结果, 其中有$k$次$A$取得胜利, $l$次$B$取得胜利. $T = k+l$ 
$$
\mathbb{P}\left[\left(a_n, b_n\right) \mid \boldsymbol{s}\right]=\frac{\mathbb{P}\left[\boldsymbol{s} \mid\left(a_n, b_n\right)\right] \mathbb{P}\left[\left(a_n, b_n\right)\right]}{\mathbb{P}(\boldsymbol{s})}=\frac{f_n a_n^k b_n^l}{f_1 a_1^k b_1^l+f_2 a_2^k b_2^l+\ldots f_N a_N^k b_N^l}
$$ 
因此当观测到这些结果以后, 学习者对 ${A}$ 预测的概率就是 
$$
\mathbb{P}(A\mid \boldsymbol{s}) = a_1 \mathbb{P}\left[\left(a_1, b_1\right) \mid \boldsymbol{s}\right]+a_2 \mathbb{P}\left[\left(a_2, b_2\right) \mid \boldsymbol{s}\right]+\cdots+a_N \mathbb{P}\left[\left(a_N, b_N\right) \mid \boldsymbol{s}\right]
$$
记 
$$
R_n(\boldsymbol{s})=\frac{\mathbb{P}\left[\left(a_1, b_1\right) \mid \boldsymbol{s}\right]}{\mathbb{P}\left[\left(a_n, b_n\right) \mid \boldsymbol{s}\right]}=\frac{f_1 a_1^k b_1^l}{f_n a_n^k b_n^l}
$$
取对数 
$$
\ln \left(R_n(\boldsymbol{s})\right)=\ln \left(\frac{f_1}{f_n}\right)+k \ln \left(\frac{a_1}{a_n}\right)+l \ln \left(\frac{b_1}{b_n}\right)
$$ 
同时除以观察的总次数 $T$, 并取极限可得 
$$
\lim _{T \rightarrow \infty} \frac{\ln \left(R_n(\boldsymbol{s})\right)}{T}=a \ln a_1+b \ln b_1-\left(a \ln a_n+b \ln b_n\right)
$$
这表明一个贝叶斯学习者在极限意义上会给最接近真实情况的假设的后验概率赋值为$1$

