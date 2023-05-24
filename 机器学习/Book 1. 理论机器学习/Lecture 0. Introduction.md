## 1\. Introduction to Learning Theory
### 1.1 History
- 1969-1971: VC theory
- 1984: PAC Learning, A Theory of Learnable
- 1990s: SVM, Boosting (theory inspired algorithm)
- 1980s: Graphical Model
- Deep Learning (Model)
- Reinforcement learning
### 1.2. Subfield
- supervised learning: classification(with class label)
- unsupervised learning
- self-supervised learning
- online learning
- reinforcement learning


## 2. Formulation
### 2.1 Supervised Classification
#### 2.1.1 Algorithm
1. collecting training data
	$$
	(x_1, y_1), \cdots, (x_n, y_n), \quad x_i\in \mathcal{X}, y_i\in \mathcal{Y}
	$$
2. design learning algorithm $A$
	1. input: training data $\{x_i,y_i\}_{i=1}^n$
	2. output: $f:\mathcal{X}\to\mathcal{Y}$​​ 
3.  test data $f(x_{n+1})$​
	$$
	\text{cost fuction: }\mathbb{P}(Y\neq f(x))
	$$

#### 2.1.2 Common Assumptions:

**i.i.d. assumption:** training data and test data are i.i.d. samples
有的时候可以放宽独立性条件, 更一般地, 还可以只假设test data和training data之间存在某种联系

#### 2.1.3 理论极限
监督分类器的理论极限是Bayesian classifier, 当已知$(x, y)$的联合分布时, 最优估计是
$$
f^*(x) = \max\limits_{y}\mathbb{P}(y\mid x)
$$
