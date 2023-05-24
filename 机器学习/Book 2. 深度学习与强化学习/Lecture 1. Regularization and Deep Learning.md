## 1. 显式正则化
### 1.1. 类型
1. **Penalty**: soft regularization
2. **Constrain**: hard regularization    

### 1.2.  Comparison of Penalty and Constrains
1. **可解释性**: constrain很多时候都是可解释的, penalty的可解释性往往比较弱
2. **local minimal**: penalty正则化起到smoothing的作用, 在很多时候会使得导数变得更加平缓, 容易陷入local minimal, 而constrain不直接改变导数值的大小
3. **Stability**: constrain是硬约束, 在超出边界后进行reprojection, 因此具有更好的稳定性

### 1.3.  L2 Regularization/Weight Decay/Ridge
L2正则化的表达式为
$$
\min\limits_{w} f(\boldsymbol{w}) +\dfrac{1}{2} \alpha \|\boldsymbol{w}\|_2^2
$$
更新相当于
$$
w_{\text {new }} \leftarrow(1-\varepsilon \alpha) w-\varepsilon \nabla J(w)
$$
每一步更新的第一项都相当于是weight decay
如果我们用local quadratic approximation来近似$J(\boldsymbol{w})$, 则有
$$
J(\boldsymbol{w}) = J\left( \boldsymbol{w^*}\right) +\dfrac{1}{2} (\boldsymbol{w} - \boldsymbol{w}^*)^{\top} H  (\boldsymbol{w} - \boldsymbol{w}^*)
$$
目标函数是最优化
$$
\min_{\boldsymbol{w}} \dfrac{1}{2} (\boldsymbol{w} - \boldsymbol{w}^*)^{\top} H  (\boldsymbol{w} - \boldsymbol{w}^*) + \dfrac{\alpha}{2}\|\boldsymbol{w}\|_2^2
$$
设$H=Q\Lambda Q^{\prime}$, 则我们有
$$
\hat{w}=Q \operatorname{diag}\left\{\frac{\lambda_i}{\lambda_i+\alpha}\right\} Q^{\prime} \boldsymbol{w}^*
$$
该表达式表明L2正则化具有shrinkage effect

### 1.4.  L1 Regularization
L1正则化在统计上的性质较好(起到稀疏化的作用), 但在机器学习(尤其是深度学习)中和L2正则化似乎没有明显的性能上的差别



## 2. 隐式正则化
### 2.1.  Dataset Augmentation
1. 重复某些数据点

2. 加入在特定transformation下的不变性(例如图像识别中要求平移, 旋转不变性)

3. 加入noise
	- Noise加在input上: 
	  $$
	  \begin{gathered}
	  y_{\text {old }} \leftarrow x_1, x_2, \cdots, x_n \\
	  y_{\text {new }} \leftarrow x_1+\varepsilon_1, x_2+\varepsilon_2, \cdots, x_n+\varepsilon_n ,\quad y_{\text {new }}=y_{\text {old }} \\
	  \hat{y}_{\text {new }}=\hat{y}_{\text {old }}+\sum_{i=1}^n w_i \varepsilon_i
	  \end{gathered}
	  $$
	  Then we have 
	  $$
	  \mathbb{E}\left(\hat{y}_{\text {new }}-y_{\text {new }}\right)^2=\mathbb{E}\left(\hat{y}_{\text {old }}-y_{\text {old }}\right)^2+\sigma^2\|\boldsymbol{w}\|_2^2
	  $$
	  
	
	  事实上, $\|\boldsymbol{w}\|= D_{\boldsymbol{x}} \hat{y}$是$\hat{y}$对$\boldsymbol{x}$的梯度
	
	- Noise加在weight上: penalty是$\|D_{\boldsymbol{w}}\hat{y}\|_2^2$
	
	- Noise加在output上(label smoothing): hard label变成了soft label

### 2.2. Early Stopping

将迭代的步数作为hyper parameter, tuning by monitoring test error on a validation set. 
GD update: 
$$
\boldsymbol{w}^\tau-\boldsymbol{w}^*=\boldsymbol{w}^{\tau-1}-\varepsilon \nabla_\boldsymbol{w} J\left(\boldsymbol{w}^{\tau-1}\right)-\boldsymbol{w}^*=(I-\varepsilon H)\left(\boldsymbol{w}^{\tau-1}-\boldsymbol{w}^*\right)
$$
$$
\boldsymbol{w}^\tau=\left[I-(I-\varepsilon H)^\tau\right] \boldsymbol{w}^*
$$
如果$H = Q\Lambda Q^{\prime}$, 则有
$$
\boldsymbol{w}^\tau=Q\left[I-(I-\varepsilon \Lambda)^\tau\right] Q^\tau \boldsymbol{w}^*
$$
当$\left(1-\varepsilon \lambda_i\right)^\tau=\dfrac{\alpha}{\lambda_i+\alpha}$. 也即是 $\tau \varepsilon \approx \dfrac{1}{\alpha}$ 时, early stopping的正则化效果和weight decay等价. 
Early stopping不会有额外选择hyper parameter的计算代价, 因为hyper parameter的选取和迭代同时进行

### 2.3. Dropout (Ensemble; Bagging)

**做法:** 在训练时以概率$p$将隐藏层的神经元置为$0$, 同时将其他神经元乘以$\dfrac{1}{1-p}$. 保证输出值期望的一致性
$$
h^{\prime}= \begin{cases}0, & p \\ \dfrac{h}{1-p}, & \text { Others }\end{cases}
$$
假设$d$是一个服从二项分布的随机变量, 设原来的隐藏层为随机变量$h$, 则经过dropout以后可以表示为
$$
h^{\prime} = \dfrac{1}{1-p}dh
$$
此时均值为
$$
\mathbb{E}\left(h^{\prime}\right)=\frac{1}{1-p}(1-p) \mu_h=\mu_h
$$
方差是
$$
D\left(h^{\prime}\right)=\frac{1}{1-p}\left(\mu_h^2+\sigma_h^2\right)-\mu_h^2
$$
通过线性层和dropout层以后, 数据的方差发生了改变, 因此通过非线性激活函数时,激活层的均值会发生漂移
**代价:** 
1. 需要增大神经网络的规模才能收敛
2. dropout会造成隐藏层的方差漂移. 由于激活函数往往是非线性的(例如Relu), 这种方差偏移会被转化为activation均值的偏移, 进入最终线性投影层. 由于**回归**问题的output时一个绝对值, 对这种变化就很敏感, 但分类问题输出只是一个相对的logit, 对这种变化就没那么敏感.  

