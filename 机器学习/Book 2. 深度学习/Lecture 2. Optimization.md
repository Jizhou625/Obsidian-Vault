## 1. Batch and Stochastic Batch
### 1.1. Batch size 
1. Batch大小为$n$时, 计算复杂度为O($n$), 但标准差的收敛速度为$O(\sqrt{ \dfrac{1}{n}  })$, 因此增大batch size的边际效应递减. 
2. 考虑到并行计算的能力, batch size太小的时候不会带来计算速度的提升
### 1.2. Regularization
1. Mini-batch size越小, 每一步引入的noise越大, 正则化的作用就越大
2. SGD有正则化效应, 因为SGD版本的batch每次选择的样本都不同, 相当于在训练的时候不断引入新的样本, 降低了泛化误差

## 2. Challenge in Optimization
### 2.1. Ill Conditioning 
1. 条件数: $$\lim _{\varepsilon \rightarrow 0} \sup _{\|\delta \boldsymbol{x}\| \leq \varepsilon} \frac{\delta f(\boldsymbol{x})}{\delta \boldsymbol{x}}$$
2. 矩阵条件数: 最大奇异值 / 最小奇异值
3. 在优化问题中, Hessian矩阵的条件数可能特别大, 不利于算法的稳定性
### 2.2. Multi Local Minimal: 
1. model identity: 如果两套参数下model的结果相同, 则优化不可能得到唯一的结果, 一定会有local minimal的存在
2. 神经网络不具有model identity
	- 神经网络的对称性: hidden unit是可以交换的
	- 层与层之间可以成对地乘除一个常数
3. 神经网络一般不存在大量的局部最小值
### 2.3. Cliff: 在某个区域梯度很大
1. 参数很小的扰动会导致结果上非常大的变动, 由于算法是梯度下降, 当局部梯度特别抖时, 优化会很不稳定
2. 处理技巧是gradient clipping


## 3. 优化上的理论极限
### 3.1 可计算性理论
从可计算性理论上来说, non-convex的问题很多是NP-hard的
### 3.2. 统计角度
我们只追求统计上的泛化功能, 不追求计算上精确的solution

## 4. 基本算法
### 4.1. SGD算法
1. 收敛条件
   $$
   \sum_{k=1}^{\infty} \varepsilon_k \rightarrow \infty, \quad \sum_{k=1}^{\infty} \varepsilon_k^2<\infty
   $$
   intuitively, 步长无限, 噪声有限

2. In practice
  $$
  \varepsilon_k=(1-\alpha) \varepsilon_0+\alpha \varepsilon_\tau, \quad \alpha=\frac{k}{\tau}
  $$
  一般可以取 $\varepsilon_\tau=0.01 \varepsilon_0$
### 4.2 Momentum算法
1. Intuition: SGD更像是random walk, 每一步的更新和之前的更新无关, 因此会浪费很多的信息, momentum算法会重新利用过去的梯度
2. Math:
	$$
	v_k \leftarrow \alpha v_{k-1}-\varepsilon g(\theta_{k-1}), \quad \theta_k \leftarrow \theta_{k-1}+v_k
	$$
	变体: 用考虑momentum后的结果计算$g$
	$$
	\theta_{k-1}^{\prime} \leftarrow \theta_{k-1}+\alpha v_{k-1}
	$$
	$$
	v_k \leftarrow \alpha v_{k-1}-\varepsilon g(\theta_{k-1}^{\prime}), \quad \theta_k \leftarrow \theta_{k-1}+v_k
	$$
	
	

## 5. 初始值的选取

具体内容见 **[Initialization of Neural Network](../../重要方法/Initialization%20of%20Neural%20Network.md)**


## 6. Step size/Learning rate
### 6.1. Delta-bar-delta:
**Intuition**: tracking the sign of the gradient changes for each weight, and adjusting the learning rate based on consistency of those changes of time 
**算法**: 如果连续好几步不变号, 增大learning rate; 如果出现变号, 减小learning rate
**Note**: 不适合SGD这种引入了noise的求解方法
###