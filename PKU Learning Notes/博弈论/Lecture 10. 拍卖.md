## 1. 拍卖
### 1.1. 拍卖的形式
| 拍卖名称 | 形式 | 是否知道他人出价 | 应用场景 |
| :---: | :---: | :---: | :---: |
| 英式拍卖 (增价拍卖) | 逐步加价, 价高者得 | 是 | 古董艺术品 |
| 荷兰式拍卖 (降价拍卖) | 逐步降价, 愿意者得 | 是 | 农产品 |
| 首价密封拍卖 | 密封报价, 价高者得, 价格为最高价 | 否 | 招标 |
| 次价密封拍卖(Vickery 拍卖) | 密刲报价, 价高者得, 价格为次高价 | 否 | 广告位 |

### 1.2. 具有独立私人价值的密封拍卖
一个具有独立私人价值的密封拍卖是一个向量$(N, (\mathbb{V}_i, F_i)_{i\in N}, \boldsymbol{p}, \boldsymbol{c})$, 其中
1. $N=\{1,2,\cdots, n\}$是购买者的集合
2. $\mathbb{V}_i\in\mathbb{R}$是购买者$i$可能得私人价值集. 用$\mathbb{V}^N = \mathbb{V}_1\times \mathbb{V}_2\times \cdots \times \mathbb{V}_n$表示所有购买者可能得私人价值的集合. 对每个$i\in N$, $F_i$是$\mathbb{V}_i$上的概率分布. 
3. $\boldsymbol{p}:[0, \infty)^N\to \Delta(N)$是一个函数. 赢得拍卖的购买者根据分布$\boldsymbol{p}(\boldsymbol{b})$进行选择, 其中$\boldsymbol{b}$是购买者的报价向量.
4. $\boldsymbol{c}:N\times [0, \infty)^N\to \mathbb{R}^N$是一个确定每个购买者的支付的函数. 