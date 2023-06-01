## 1. 内积和范数
### 1.1. 张量的内积
设矩阵(张量)$A, B$具有相同的形状, 则矩阵(张量)$A, B$的内积记作$\langle A, B\rangle$. 定义为两个拉长向量$\mathrm{vec}(A)$和$\mathrm{vec}(B)$的内积. 也就是说
$$
\langle A, B\rangle = \langle \mathrm{vec}(A), \mathrm{vec}(B)\rangle
$$
当$A, B$都是矩阵时, 矩阵$A, B$的内积可以写为$\langle A, B\rangle = \mathrm{tr}\left\{A^{\top}B\right\}$

### 1.2. 矩阵范数
依照范数的定义，一个从 $\mathcal{M}_{m, n}(\mathbb{K})$ 映射到非负实数的矩阵范数 $\|\cdot\|$应该满足以下的条件:
1. **严格正定性**: 对任意矩阵 $A \in \mathcal{M}_{m, n}(\mathbb{K})$ ，都有 $\|A\| \geq 0$ ，且等号成立若且唯若 $A=0$ 
2. **线性性**: 对任意系数 $\alpha \in \mathbb{K}$ 、任意矩阵 $A \in \mathcal{M}_{m, n}(\mathbb{K})$ ，都有 $\|\alpha A\|=|\alpha|\|A\|$ 
3. **三角不等式**: 任意矩阵 $A, B \in \mathcal{M}_{m, n}(\mathbb{K})$ ，都有 $\|A+B\| \leq\|A\|+\|B\|$ 
   
此外，某些定义在方块矩阵组成空间 $\mathcal{M}_n(\mathbb{K})$ 上的矩阵范数满足一个或多个以下的条件:
1. **Consistency Property:** $\|A B\| \leq\|A\|\|B\|$ ；
2. **共轭转置相等条件:** $\|A\|=\left\|A^{\mathrm{H}}\right\|$ 


## 2.1. 诱导范数(induced norm)
### 2.1. 诱导范数的定义
诱导范数又被称为$m\times n$矩阵空间上的算子范数, 定义为
$$
\|A\|=\max\{\|A\boldsymbol{x}\|: \boldsymbol{x}\in \mathbb{K}^n, \|\boldsymbol{x}\|=1\}= \max\left\{ \frac{\|A\boldsymbol{x}\|}{\|\boldsymbol{x}\|}: \boldsymbol{x}\in \mathbb{K}^n, \boldsymbol{x}\neq 0 \right\}
$$
其中$\|\boldsymbol{x}\|$是$\boldsymbol{x}$的向量范数. 

### 2.2. 常见的诱导范数
#### 2.2.1. 绝对列和范数
$$
\|A\|_1= \max_{1\le j\le n}\sum\limits_{i=1}^{m}|a_{ij}|
$$

#### 2.2.2. 谱范数
$$
\|A\|_2 = \sqrt{ \lambda_{\max}(A^{\top} A) }
$$

#### 2.2.3. 绝对行和范数
$$
\|A\|_{\infty} = \max_{1\le i\le m}\sum\limits_{j=1}^{n}|a_{ij}|
$$

## 3. 元素形式范数(entrywise norm)
### 3.1. 元素形式范数的定义
将$m\times n$矩阵先按照列堆栈的形式, 排列成一个$mn\times 1$向量, 然后采用向量的范数定义, 即可得到矩阵的范数, 元素形式范数是下面的$p$矩阵范数
$$
\|A\|_p = \left(\sum\limits_{i=1}^{m} \sum\limits_{j=1}^{n}|a_{ij}|^p \right)^{1/p}
$$

### 3.2. 常见的元素形式范数
#### 3.2.1. 和范数
$$
\|A\|_1 = \sum\limits_{i=1}^{m}\sum\limits_{j=1}^{n} |a_{ij}|
$$

#### 3.2.2. Frobenius范数 
$$
\|A\|_F =\left(\sum\limits_{i=1}^{m}\sum\limits_{j=1}^{n} |a_{ij}|^2\right)^{1/2} = \sqrt{\mathrm{tr}\left\{A^{\top}A\right\}}
$$
由正定矩阵$\Omega$进行加权的Frobenius范数
$$
\|A\|_{\Omega}= \sqrt{ \mathrm{tr}\left\{A^{\top} \Omega A\right\} }
$$
   
#### 3.2.3. 最大范数
$$
\|A\|_{\infty}=\max_{i,j}\{|a_{ij}|\}
$$

#### 3.2.4. $(p,q)$ Norm
设$(\boldsymbol{a}_1, \cdots, \boldsymbol{a}_n)$是矩阵$A$的列向量, 矩阵$A$的$(p,q)$范数被定义为
$$
\|A\|_{p,q} =\left(\sum\limits_{j=1}^{n}\left(\sum\limits_{i=1}^{m}|a_{ij}|^p \right)^{\frac{q}{p}} \right)^{\frac{1}{q}}
$$
   或者用列向量的形式可以写成 
$$
\|A\|_{p,q} = \left\|(\|\boldsymbol{a}_1\|_p, \cdots, \|\boldsymbol{a}_n\|_p)\right\|_{q}
$$
当$q=1$时, 外层范数退化为$L_1$范数, 因此具有group sparsity的作用


## 4. Schatten范数
### 4.1. Schatten范数的定义
设$A$的奇异值为$\sigma_1\ge \sigma_2\ge \cdots\ge \sigma_r \ge 0$, 则矩阵$A$的Schatten范数定义为
$$
\|A\|_p = \|\boldsymbol{\sigma}\|_p = \left(\sum\limits_{i=1}^{\min\{m,n\}} \sigma_i^p\right)^{1/p}
$$

### 4.2. 核范数(Nuclear Norm)
$$
\|A\|_* = \sum\limits_{i=1}^{\min\{m,n\}} \sigma_i=\mathrm{tr}\left\{\sqrt{ A^{\top} A }\right\}
$$

### 4.3. 核范数的应用
考虑正则化
$$
\min\ f(A)+\lambda R(A)
$$
$R(A)$是使得矩阵满足低秩条件的正则化项, 例如$\mathrm{rank}(A)$.  

因为$\mathrm{rank}(A)$是离散的, 且计算难度较高, 在实践中, 我们通常用nuclear norm当成$\mathrm{rank}(A)$的凸包络来代替$\mathrm{rank}(A)$作为正则化项. 



## 3. Dual Norm
### 3.1. 对偶范数的定义
设$\|\cdot\|$是$\mathbb{R}^n$上的范数, 则其对应的dual norm, 记为$\|\cdot\|^*$, 定义为
$$
\|\boldsymbol{z}\|^* = \sup\{\boldsymbol{z}^{\top} \boldsymbol{x}\mid \|\boldsymbol{x}\|\le 1\}
$$
这样定义的$\|\cdot\|^*$是一个范数. 

### 3.2. Dual Norm的性质
1. **Generalized Cauchy-Schwartz Inequality**
   $$
   \boldsymbol{z}^{\top} \boldsymbol{x}\le \|\boldsymbol{x}\|\|\boldsymbol{z}\|^*
   $$
   
2. **自反性**: $\|\boldsymbol{x}\|^{**} = \|\boldsymbol{x}\|$

3. **对偶性质**: $\forall \boldsymbol{x}, \exists \boldsymbol{x}^*$. such that $\langle\boldsymbol{x}, \boldsymbol{x}^*\rangle = \|\boldsymbol{x}\|\|\boldsymbol{x}^*\|^*$


___
##### Proof
1. 对于$\|\boldsymbol{x}\|\ge 1$, 令$\boldsymbol{x}_{\mathrm{new}} = \dfrac{1}{\|\boldsymbol{x}\|}\boldsymbol{x}$, 则$\|\boldsymbol{x}_{\mathrm{new}}\|=1$, 于是我们只要证明
   $$
   \boldsymbol{z}^{\top} \boldsymbol{x}_{\mathrm{new}}\le \|\boldsymbol{z}\|^*
   $$
   因为
   $$
   \|\boldsymbol{z}\|^* = \sup\{\boldsymbol{z}^{\top} \boldsymbol{x}\mid \|\boldsymbol{x}\|\le 1\} \ge \boldsymbol{z}^{\top} \boldsymbol{x}_{\mathrm{new}}
   $$
   则我们结果成立. 
2. 可以不妨设$\|\boldsymbol{x}\|=1$, 于是我们只要证明存在$\boldsymbol{x}^*$使得$\boldsymbol{x}^{\top}\boldsymbol{x}^* = \|\boldsymbol{x}^{*}\|^{*}$. 由于
   $$
   \|\boldsymbol{x}^*\|^* = \sup\{\boldsymbol{x}^{*\top}\boldsymbol{y}\mid \|\boldsymbol{y}\|\le 1\}
   $$
#####
___
### 3.3. 例子

1. 



