## 1. 多元函数的导数和微分
### 1.1. 可微性的定义
设$U\subset \mathbb{R}^n$, $\boldsymbol{p}$是$U$的一个内点, 映射$\boldsymbol{f}: U\to \mathbb{R}^m$. 假如存在一个线性映射$\mathcal{L}: \mathbb{R}^n \to \mathbb{R}^m$, 使得
$$
\lim_{\boldsymbol{h}\to \boldsymbol{0}}\dfrac{1}{|\boldsymbol{h}|}[\boldsymbol{f}(\boldsymbol{p+h})-\boldsymbol{f(p)}-\mathcal{L}\boldsymbol{h}]=\boldsymbol{0}
$$
则称$\boldsymbol{f}$在点$\boldsymbol{p}\in U$处可微. 若$\boldsymbol{f}$在$U$的每一点处可微, 则称$\boldsymbol{f}$在$U$上是可微的

**线性映射的唯一性**: 可微性定义中的线性映射如果存在, 则它是唯一确定的. 事实上, 如果存在$\mathcal{L}_1,\mathcal{L}_2$同时满足方程
$$
\lim_{\boldsymbol{h}\to \boldsymbol{0}}\dfrac{1}{|\boldsymbol{h}|}[\boldsymbol{f}(\boldsymbol{p+h})-\boldsymbol{f(p)}-\mathcal{L}\boldsymbol{h}]=\boldsymbol{0}
$$
则有
$$
\lim_{\boldsymbol{h}\to\boldsymbol{0}}\dfrac{1}{|\boldsymbol{h}|}(\mathcal{L}_1\boldsymbol{h}-\mathcal{L}_2\boldsymbol{h})=\boldsymbol{0}
$$
将$\boldsymbol{h}=\lambda \boldsymbol{k}$代入, 其中$\boldsymbol{k}$为任意非零向量, $\lambda>0$. 取$\lambda\to 0$, 上式变成
$$
\dfrac{1}{|\boldsymbol{k}|}(\mathcal{L}_1\boldsymbol{k}-\mathcal{L}_2\boldsymbol{k})=\boldsymbol{0}
$$
故$\forall \boldsymbol{k}\neq \boldsymbol{0}$, 都有$\mathcal{L}_1\boldsymbol{k}-\mathcal{L}_2\boldsymbol{k}=\boldsymbol{0}$. 因此$\mathcal{L}_1=\mathcal{L}_2$

### 1.2. 导数的定义
假如映射$\boldsymbol{f}: U\to \mathbb{R}^m$在点$\boldsymbol{p}\in U$处可微. 则由$\displaystyle{\lim_{\boldsymbol{h}\to \boldsymbol{0}}\dfrac{1}{|\boldsymbol{h}|}[\boldsymbol{f}(\boldsymbol{p+h})-\boldsymbol{f(p)}-\mathcal{L}\boldsymbol{h}]=\boldsymbol{0}}$唯一确定的线性映射$\mathcal{L}$称为映射$\boldsymbol{f}$在点$\boldsymbol{p}\in U$处的微分, 记作$\mathrm{d}\boldsymbol{f_p}$. 有的文献将$\mathrm{d}\boldsymbol{f_p}$成为Fr$\'\text{e}$chet导数. 并记作$\mathrm{D}\boldsymbol{f}$. 线性映射$\mathrm{d}\boldsymbol{f_p}$相对于$\mathbb{R}^n$和$\mathbb{R}^m$的标准基的矩阵称为映射$\boldsymbol{f}$在点$\boldsymbol{p}\in U$处的Jacobi矩阵, 记作$\boldsymbol{f'(p)}$或$J_{\boldsymbol{f}}(\boldsymbol{p})$. 

**标准基矩阵**: 设$\mathbb{R}^n$的一组基是由向量组$\{\boldsymbol{e}_1,\cdots ,\boldsymbol{e}_n\}$组成的, 又设$\mathbb{R}^m$的一组基是由向量组$\{\boldsymbol{f}_1,\cdots ,\boldsymbol{f}_m\}$组成, 而线性映射$\mathcal{L}$由下式确定
$$
\mathcal{L}\boldsymbol{e}_j=\sum_{i=1}^m a_j^i\boldsymbol{f}_i,\quad j=1,2,\cdots ,n
$$
若有分解
$$
\boldsymbol{u}=\sum_{j=1}^nu_j\boldsymbol{e}_j\ \text{和}\ \boldsymbol{v}=\sum_{i=1}^m v_i\boldsymbol{f}_i
$$
则线性映射满足
$$
\mathcal{L}\boldsymbol{u}=\sum_{j=1}^nu_j\mathcal{L}\boldsymbol{e}_j=\sum_{i=1}^m\left(\sum_{i=1}^na_j^iu_j\right)\boldsymbol{f}_i
$$
线性映射$\mathcal{L}$相对于$\mathbb{R}^n$和$\mathbb{R}^m$的标准基的矩阵为
$$
[a_j^i]=\begin{pmatrix}
	a_1^1 &  a_2^1 &  \cdots  &  a_n^1\\
	a_1^2 &  a_2^2 &  \cdots  &  a_n^2\\
	\vdots  &  \vdots  &    &  \vdots \\
	a_1^m &  a_2^m &  \cdots  &  a_n^m
\end{pmatrix}
$$

### 1.3. 链式法则
设$U\subset \mathbb{R}^n$和$V\subset \mathbb{R}^m$, $U$和$V$分别是$\mathbb{R}^n$和$\mathbb{R}^m$中的开集. $\boldsymbol{f}: U\to \mathbb{R}^m$, $\boldsymbol{g}: V\to \mathbb{R}^k$且$\boldsymbol{f}(U)\subset V$. 又设$\boldsymbol{f}$在点$\boldsymbol{p}$处可微, $\boldsymbol{q}=\boldsymbol{f}(\boldsymbol{p})$, $\boldsymbol{g}$在点$\boldsymbol{q}$处可微, 则$\boldsymbol{g}\circ\boldsymbol{f}$在点$\boldsymbol{p}$处可微,  且$\mathrm{d}(\boldsymbol{g}\circ\boldsymbol{f})_{\boldsymbol{p}}=\mathrm{d}\boldsymbol{g_q}\circ\mathrm{d}\boldsymbol{f_p}$. 用导数的语言表示, 有$(\boldsymbol{g}\circ\boldsymbol{f})'(\boldsymbol{p})=\boldsymbol{g}'(\boldsymbol{q})\boldsymbol{f}'(\boldsymbol{p})$

### 1.4. 方向导数和偏导数
1. **方向导数**: 设$U\subset \mathbb{R}^n$是开集, $\boldsymbol{f}: U\to \mathbb{R}^m, \boldsymbol{p}\in U,\boldsymbol{q}\in \mathbb{R}^n$, 且有$\varepsilon>0$, 使得$[\boldsymbol{p}-\varepsilon\boldsymbol{q}, \boldsymbol{p}+\varepsilon\boldsymbol{q}]\subset U$, 函数$\boldsymbol{g}(t)=\boldsymbol{f}(\boldsymbol{p}+t\boldsymbol{q})$在区间$[-\varepsilon, \varepsilon]$上有定义. 假如$\boldsymbol{g}$在$t=0$上可微, 即
   $$
   \boldsymbol{g}(t)=\boldsymbol{g}(0)+\mathrm{d}\boldsymbol{g}_0t+\boldsymbol{r}(t),\quad \lim_{t\to 0}\dfrac{|\boldsymbol{r}(t)|}{t}=0	
   $$
   则称$\boldsymbol{f}$在点$\boldsymbol{p}$处沿$\boldsymbol{q}$方向是可微的, $\mathrm{d}\boldsymbol{g}_0$称为$\boldsymbol{f}$在点$\boldsymbol{p}$处沿着$\boldsymbol{q}$方向的方向微分或$\boldsymbol{f}$在点$\boldsymbol{p}$处沿$\boldsymbol{q}$方向的方向导数, 记作
   $$
   D_{\boldsymbol{q}}\boldsymbol{f}(\boldsymbol{p})=\lim_{t\to \infty}\dfrac{\boldsymbol{f}(\boldsymbol{p}+t\boldsymbol{q})-\boldsymbol{f}(\boldsymbol{p})}{t}=\mathrm{d}\boldsymbol{g}_0(\boldsymbol{1})
   $$
   其中$\mathrm{d}\boldsymbol{g}_0(\boldsymbol{1})$表示线性映射$\mathrm{d}\boldsymbol{g}_0$作用在一维单位向量$\boldsymbol{1}$上的值

2. **偏导数**: 设$U\subset \mathbb{R}^n$是开集, 映射$\boldsymbol{f}: U\to \mathbb{R}^m, \boldsymbol{p}\in U$, 则$\boldsymbol{f}$在点$\boldsymbol{p}$处沿$\boldsymbol{e}_k$方向的方向导数称为$\boldsymbol{f}$在点$\boldsymbol{p}$处的第$k$个偏导数, 记作
   $$
   \mathrm{D}_k\boldsymbol{f}(\boldsymbol{p})=\dfrac{\partial \boldsymbol{f}}{\partial x_k}(\boldsymbol{p})=\lim_{t\to\infty} \dfrac{\boldsymbol{f}(\boldsymbol{p}+t\boldsymbol{e}_k)-\boldsymbol{f}(\boldsymbol{p})}{t}
   $$

3. **偏导数与方向导数**: 设$U\subset \mathbb{R}^n$是开集, 映射$\boldsymbol{f}: U\to\mathbb{R}^m, \boldsymbol{p}\in U, \boldsymbol{q}=(q_1,\cdots, q_n)\in \mathbb{R}^n$. 假如$\boldsymbol{f}$在点$\boldsymbol{p}$处是可微的, 则
   $$
   \mathrm{d}\boldsymbol{f_p}(\boldsymbol{q})=\sum_{k=1}^n q_k\mathrm{D}_k\boldsymbol{f}(\boldsymbol{p})=\sum_{k=1}^n q_k\dfrac{\partial \boldsymbol{f}}{\partial x_k}(\boldsymbol{p})
   $$

4. **Jacobi矩阵**: 设$U\subset \mathbb{R}^n$是开集, 映射$\boldsymbol{f}: U\to\mathbb{R}^m, \boldsymbol{p}\in U,\boldsymbol{f}=(f_1,\cdots , f_m)^T\in \mathbb{R}^m$. 假如$\boldsymbol{f}$在点$\boldsymbol{p}$处是可微的, 则
   $$
   \boldsymbol{f}'(\boldsymbol{p})=[D_1\boldsymbol{f}(\boldsymbol{p}),D_2\boldsymbol{f}(\boldsymbol{p}),\cdots, D_n\boldsymbol{f}(\boldsymbol{p})]=\begin{pmatrix}
   \dfrac{\partial f_1}{\partial x_1}(\boldsymbol{p}) &  \dfrac{\partial f_1}{\partial x_2}(\boldsymbol{p})  &  \cdots  &  \dfrac{\partial f_1}{\partial x_n}(\boldsymbol{p})\\
   \\
   \dfrac{\partial f_2}{\partial x_1}(\boldsymbol{p}) &  \dfrac{\partial f_2}{\partial x_2}(\boldsymbol{p})  &  \cdots  &  \dfrac{\partial f_2}{\partial x_n}(\boldsymbol{p})\\
   \\
   \vdots   &  \vdots  &    &  \vdots \\
   \\
   \dfrac{\partial f_m}{\partial x_1}(\boldsymbol{p}) &  \dfrac{\partial f_m}{\partial x_2}(\boldsymbol{p})  &  \cdots  &  \dfrac{\partial f_m}{\partial x_n}(\boldsymbol{p})
   \end{pmatrix} 
   $$
   上式的矩阵便是用$\boldsymbol{f}$的分量的偏导数表示的$\boldsymbol{f}$的导数, 或称Jacobi矩阵

### 1.5 中值定理
**数值函数的中值定理**: 设$E\subset \mathbb{R}^n$是$\mathbb{R}^n$的开集, 若映射$f: E\to \mathbb{R}$在$E$的每一个点处都可微, 则对于任何$[\boldsymbol{a,b}]\subset E$, 有$\boldsymbol{c}\in [\boldsymbol{a,b}]$使得
$$
f(\boldsymbol{b})-f(\boldsymbol{a})=\mathrm{d}f_{\boldsymbol{c}}(\boldsymbol{b-a})=f'(\boldsymbol{c})(\boldsymbol{b-a})
$$
**数值多元函数的有限增量定理**: 设$U\subset \mathbb{R}^n$是凸的开集, 映射$f: U\to \mathbb{R}$在$U$上可微, 且$||\mathrm{d}f_{\boldsymbol{p}}||\le M$对于一切点$\boldsymbol{p}\in U$成立, 则
$$
\forall \boldsymbol{a,b}\in U,\ |f(\boldsymbol{b})-f(\boldsymbol{a})|\le M|\boldsymbol{b-a}|
$$

## 2. 高阶偏导数
### 2.1 高阶偏导数的定义
设$f:\Omega\to \mathbb{R}$, 假若对于开集$U\subset \Omega$中的一切点$\boldsymbol{p}$, 偏导数$\mathrm{D}_jf(\boldsymbol{p})$都存在, $\mathrm{D}_jf$可以看成$\Omega$到全体$1\times1$矩阵组成的线性空间的映射. 这样, 就可以定义$\mathrm{D}_k\mathrm{D}_jf=\mathrm{D}_k(\mathrm{D}_jf)$, 其中$1\le k \le n$, $\mathrm{D}_k\mathrm{D}_jf$称为$f$的二阶偏导数. 归纳地, 我们可以定义$f$的$r$阶偏导数

### 2.2. Schwarz定理
设$\Omega \in\mathbb{R}^n$是开集, 点$\boldsymbol{p}\in \Omega$, 映射$f: \Omega\to \mathbb{R}$. 又设$\mathrm{D}_if, \mathrm{D}_jf$和$\mathrm{D}_j\mathrm{D}_if$在$\boldsymbol{p}$的一个邻域中存在且它们在点$\boldsymbol{p}$处都是连续的, 则$\mathrm{D}_i\mathrm{D}_jf(\boldsymbol{p})$存在, 且$\mathrm{D}_i\mathrm{D}_jf(\boldsymbol{p})=\mathrm{D}_j\mathrm{D}_if(\boldsymbol{p})$. 

### 2.3. 简化记法
**重指标**: 若$f\in C^r, r>1$, 则$f$的$r$阶的混合偏导数在该开集上可以写成以下的标准形式
$$
\mathrm{D}_{j_1}\mathrm{D}_{j_2}\cdots \mathrm{D}_{j_r}f=\mathrm{D}_1^{\alpha_1}\mathrm{D}_2^{\alpha_2}\cdots \mathrm{D}_n^{\alpha_n}f
$$
其中$\alpha_i=\sum\limits_{k=1}^r\delta_{j_k,i}$. 显然$\sum\limits_{i=1}^n\alpha_i=r$. $n$个指标组成的指标组$\boldsymbol{\alpha}=(\alpha_1,\cdots , \alpha_n)$称为重指标, $k=\sum\limits_{i=1}^n\alpha_i$称为$\boldsymbol{\alpha}$的阶, 记作$|\boldsymbol{\alpha}|$. 此外我们记$\boldsymbol{\alpha }!=\alpha_1!\cdots \alpha_n!$

**偏导数的简化记法**: 偏导数有以下简化的记法
$$
\mathrm{D}_1^{\alpha_1}\mathrm{D}_2^{\alpha_2}\cdots \mathrm{D}_n^{\alpha_n}f=\dfrac{\partial ^{|\boldsymbol{\alpha}|}f}{\partial x_1^{\alpha_1}\cdots \partial x_n^{\alpha^n}}=\mathrm{D}^{\boldsymbol{\alpha}}f=\dfrac{\partial ^{\boldsymbol{\alpha}}f}{\partial x^{\boldsymbol{\alpha}}}
$$

**多项式的简化记法**: 设$\boldsymbol{\alpha}=(\alpha_1,\cdots ,\alpha_n),\ \boldsymbol{x}=(x_1,\cdots, x_n)$. 记
$$
\boldsymbol{x^{\alpha}}=x_1^{\alpha_1}\cdots x_n^{\alpha_n}
$$
则$n$元多项式可以写成$\sum\limits_{|\boldsymbol{\alpha}|\le r}c_{\boldsymbol{\alpha}}\boldsymbol{x^{\alpha}}$, 常数$c_{\boldsymbol{\alpha}}$称为多项式的系数

### 2.4. 多元函数的Taylor展开公式
设$U$是$\mathbb{R}^n$中的开凸集, $f: U\to \mathbb{R}$是$\mathcal{C}^{r+1}$类的函数, $r\ge 0$. 若$\boldsymbol{p}\in U$和$\boldsymbol{q=p+h}\in U$, 则存在$\theta\in (0,1)$, 使得以下多元函数的Taylor公式成立
$$
f(\boldsymbol{q})=\sum_{|\boldsymbol{\alpha}|\le r}\dfrac{ \mathrm{D}^{\boldsymbol{\alpha }}f(\boldsymbol{p})}{\boldsymbol{\alpha}!}\boldsymbol{h^{\alpha}}+\sum_{|\boldsymbol{\alpha }|=r+1}\dfrac{\mathrm{D}^{\boldsymbol{\alpha}}f(\boldsymbol{p}+\theta\boldsymbol{h})}{\boldsymbol{\alpha}!}\boldsymbol{h}^{\boldsymbol{\alpha}}
$$

## 3. 反函数定理与隐函数定理
### 3.1. 反函数定理
假设$\Omega\subset \mathbb{R}^n$是开集, 映射$\boldsymbol{f}: \Omega\to \mathbb{R}^n$是$\mathcal{C}^r$类的($r\ge 1$), $\boldsymbol{p}\in \Omega$, 且$\mathrm{d}\boldsymbol{f_p}$是可逆的. 则存在$\boldsymbol{p}$的开邻域$U$, 使得$\boldsymbol{f}$在$U$上是单射, $V=\boldsymbol{f}(U)$是$\mathbb{R}^n$中的开集, $\boldsymbol{f}|_U$的逆映射$\boldsymbol{g}=(\boldsymbol{f}|_U)^{-1}$是$\mathcal{C}^r$类的, 且$\mathrm{d}\boldsymbol{g_{f(p)}}\equiv \mathrm{d}\left[(\boldsymbol{f}|_U)^{-1}\right]=(\mathrm{d}\boldsymbol{f_p})^{-1}$

### 3.2. 隐函数定理
设$\Omega$是$\mathbb{R}^{n+m}$中的开集, $\boldsymbol{f}: \Omega\to \mathbb{R}^m$是$\mathcal{C}^r$类的映射, $r\ge 1$. 任给点$\boldsymbol{p}=\displaystyle{\binom{\boldsymbol{a}}{\boldsymbol{b}}}\in  \Omega$ ($\boldsymbol{a}\in \mathbb{R}^n, \boldsymbol{b}\in \mathbb{R}^m$). $\boldsymbol{f}$过点$\boldsymbol{p}$的等高曲面(简称等高面)$\Sigma$定义为
$$
\Sigma=\{\boldsymbol{q}\in \Omega: \boldsymbol{f}(\boldsymbol{q})=\boldsymbol{f}(\boldsymbol{p})\}
$$
又设$\mathcal{S}\in\mathcal{L}(\mathbb{R}^n)$和$\mathcal{T}\in \mathcal{L}(\mathbb{R}^m)$分别表示映射$\boldsymbol{f}$在点$\boldsymbol{p}$处的微分在$\mathbb{R}^n$和$\mathbb{R}^m$上的限制
$$
\mathcal{S}(\boldsymbol{h})=\mathrm{d}\boldsymbol{f_p}\binom{\boldsymbol{h}}{\boldsymbol{0}},\  \mathcal{T}(\boldsymbol{k})=\mathrm{d}\boldsymbol{f_p}\binom{\boldsymbol{0}}{\boldsymbol{k}}
$$
换言之
$$
\mathrm{d}\boldsymbol{f_p}\binom{\boldsymbol{h}}{\boldsymbol{k}}=\mathcal{S}(\boldsymbol{h})+\mathcal{T}(\boldsymbol{k})
$$
若$\mathcal{T}$可逆, 则存在点$\boldsymbol{p}$的邻域$U\subset \Omega$,  点$\boldsymbol{a}\in \mathbb{R}^n$的邻域$W$和一个$\mathcal{C}^r$映射$\boldsymbol{g}: W\to \mathbb{R}^m$, 使得$\Sigma \cap U$恰是映射$\boldsymbol{g}: W\to \mathbb{R}^m$的图像
$$
\Sigma \cap U=\left\{\binom{\boldsymbol{s}}{\boldsymbol{g}(\boldsymbol{s})}: \boldsymbol{s}\in W\right\}
$$
并且满足
$$
\mathrm{d}\boldsymbol{g_a}=-\mathcal{T}^{-1}\mathcal{S}
$$
关系式$\displaystyle{\Sigma \cap U=\left\{\binom{\boldsymbol{s}}{\boldsymbol{g}(\boldsymbol{s})}: \boldsymbol{s}\in W\right\}}$的含义是
$$
\forall \boldsymbol{s}\in W,\ \boldsymbol{f}\binom{\boldsymbol{s}}{\boldsymbol{g}(\boldsymbol{s})}=\boldsymbol{f}(\boldsymbol{p})
$$
也就是说, $\boldsymbol{g}(\boldsymbol{s})$是隐函数方程$\displaystyle{\boldsymbol{f}\binom{\boldsymbol{s}}{\boldsymbol{t}}=\boldsymbol{f}(\boldsymbol{p})}$的解$\boldsymbol{t}=\boldsymbol{g}(\boldsymbol{s})$

### 3.3. 微分同胚的分解
1. **微分同胚**: 从$\mathbb{R}^m$中的开集$U$到$\mathbb{R}^m$中的开集$V$的双射$\boldsymbol{\varphi}$称为开集$U$到开集$V$的$\mathcal{C}^r$类微分同胚, 如果$\boldsymbol{\varphi}$和$\boldsymbol{\varphi}^{-1}$都是$\mathcal{C}^r$类的映射
2. **初等微分同胚**:  定义在开集$U\subset \mathbb{R}^m$上的微分同胚$\boldsymbol{g}: U\to \boldsymbol{g}(U)\subset \mathbb{R}^m$称为初等微分同胚, 如果有某个$j\in \{1,\cdots ,m\}$, 使得映射$\boldsymbol{g}: \boldsymbol{x}=(x_1,\cdots , x_m)\to \boldsymbol{y}=(y_1,\cdots , y_m)$具有形式
   $$   
   y_i=\begin{cases}	
   x_i,\qquad &i\neq j\\		
   g_j(x_1,\cdots, x_m), &i=j	
   \end{cases}	
   $$
   换言之, 初等微分同胚像点与原像点之间最多除了一个坐标外, 其他坐标都是相同的, 恒等映射是初等微分同胚. 

1. **微分同胚的初等微分同胚分解**: 设$G\subset \mathbb{R}^m$是开集, 映射$\boldsymbol{f}: G\to \boldsymbol{f}(G)\subset \mathbb{R}^m$是微分同胚, 则任意点$\boldsymbol{x}_0\in G$有个开邻域$U$, 使得
	$$
	\forall\boldsymbol{x}\in U, \boldsymbol{f}(\boldsymbol{x})=\boldsymbol{g}_1\circ\cdots \circ \boldsymbol{g}_m(\boldsymbol{x})
	$$
	其中$\boldsymbol{g}_1,\cdots,\boldsymbol{g}_m$是$m$个初等微分同胚

## 4. 单位分解
### 4.1. 单位分解定理
设$\{U_{\alpha}\}_{\alpha \in A}$是$\mathbb{R}^n$上的一族开集, $U=\bigcup\limits_{\alpha \in A}U_{\alpha}$. 则有一个定义在$\mathbb{R}^n$上的非负实值函数构成的(有限或无限)函数列$\{\phi_j\}_{j\in I\subset \mathbb{N}}$, 它具有以下性质
1. 每个$\phi_j$是紧支集的无穷次连续可微函数: $\phi_j\in \mathcal{C}_0^{\infty}(\mathbb{R}^n)$, 且有某个$\alpha(j)\in A$, 使得$\text{supp}\phi_j\subset U_{\alpha(j)}$
2. 函数序列$\{\phi_j\}_{j\in I\subset \mathbb{N}}$具有局部有限性, 换言之, 对于每个紧集$K\subset U$, 有$I$的有限子集$B$, 使得
	$$
	\forall \boldsymbol{x}\in K, \forall j\in I\backslash B,\ \phi_j(\boldsymbol{x})=0
	$$

## 5. 一次微分形式与线积分
### 5.1. 线性微分形式
给定在开集$U\subset \mathbb{R}^n$上定义的实值函数$a_j(\boldsymbol{x})$($j=1,\cdots ,n$), 表达式
$$
\sum_{j=1}^na_j(\boldsymbol{x})\mathrm{d}x_j=a_1(\boldsymbol{x})\mathrm{d}x_1+\cdots +a_n(\boldsymbol{x})\mathrm{d}x_n
$$
称为线性微分形式(或称一次微分形式, 简称1-形式). 显然线性微分形式是随着$\boldsymbol{x}\in U$的变化而变化的$\mathbb{R}^n\to \mathbb{R}$的线性映射. 

### 5.2. 函数的回拉
给定在开集$U\subset \mathbb{R}^n$上定义的(实值或复值)函数$f(\boldsymbol{x})$, 又给定由开集$V\subset \mathbb{R}^m$到开集$U\subset \mathbb{R}^n$的可微映射$\boldsymbol{\varphi}: V\to U$. 函数$f(\boldsymbol{x})$在可微映射$\boldsymbol{\varphi}$下的回拉(pullback)定义为
$$
\boldsymbol{\varphi}^*f=f\circ \boldsymbol{\varphi}
$$
换言之, 对于任何$\boldsymbol{y}\in V$
$$
(\boldsymbol{\varphi}^*f)(\boldsymbol{y})=f(\boldsymbol{\varphi}(\boldsymbol{y}))
$$
**Note**: $f$是定义在$U$上的函数, 而$\boldsymbol{\varphi}^*f$是定义在$V$上的. $\boldsymbol{\varphi}^{*}$把定义在$U$上的函数映成定义在$V$上的函数. $\boldsymbol{\varphi}^{*}$和$\boldsymbol{\varphi}$的方向正好相反, 因此称为回拉(pullback)