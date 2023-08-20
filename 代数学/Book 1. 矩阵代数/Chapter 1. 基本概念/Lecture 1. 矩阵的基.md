## 1. 矩阵的基表示
### 1.1. 基的同构表示
如果$V$是域$\mathbb{F}$上的一个$n$维向量空间, 它有指定的基$\mathcal{B} = \{\boldsymbol{x}_1, \cdots , \boldsymbol{x}_n\}$, 那么, 由于任何元素$\boldsymbol{x}\in V$都可以用唯一的方式表示成$\boldsymbol{x} = a_1\boldsymbol{x}_1 +\cdots + a_n\boldsymbol{x}_n$, 其中$a_i\in \mathbb{F}$. 故我们可以将$\boldsymbol{x}$和一个$n$元向量$[\boldsymbol{x}]_{\mathcal{B}} = [a_1, \cdots, a_n]^{\top}$等同起来. 对任何基$\mathcal{B}$, 映射$\boldsymbol{x}\to [\boldsymbol{x}]_{\mathcal{B}}$都是$V$与$\mathbb{F}^n$之间的一个同构. 

### 1.2. 矩阵与线性变换
设$U$是一个$n$维线性空间, $V$是一个$m$维向量空间, 它们都以$\mathbb{F}$为基域. 设$\mathcal{B}_U$和$\mathcal{B}_V$分别是$U$和$V$的基. 任何线性变换$T:U\to V$都可以表示成一个$m\times n$矩阵$A$, 使得对任何$\boldsymbol{x}\in U$, 都有
$$
[\boldsymbol{y}]_{\mathcal{B}_V} = T(\boldsymbol{x}) = A[\boldsymbol{x}]_{\mathcal{B}_U}
$$ 
其中$[\boldsymbol{x}]_{\mathcal{B}_U}$是$\boldsymbol{x}$在基$\mathcal{B}_U$下的坐标向量, $[\boldsymbol{y}]_{\mathcal{B}_V}$是$\boldsymbol{y}$在基$\mathcal{B}_V$下的坐标向量.

### 1.3. $\mathcal{B}_1 - \mathcal{B}_2$基表示 (basis representation)
设$T: V\to V$是一个给定的线性变换, 定义$T$的$\mathcal{B}_1 - \mathcal{B}_2$基表示为
$$
_{\mathcal{B}_2}[T]_{\mathcal{B}_1} = ([T\boldsymbol{v}_1]_{\mathcal{B}_2}, \cdots, [T\boldsymbol{v}_n]_{\mathcal{B}_2}) = =\left(\begin{array}{ccc}
t_{11} & \cdots & t_{n 1} \\
\vdots & \ddots & \vdots \\
t_{1 n} & \cdots & t_{n t}
\end{array}\right)
$$
当$\mathcal{B}_1 = \mathcal{B}_2$时, 我们称$_{\mathcal{B}_1}[T]_{\mathcal{B}_1}$是$T$的$\mathcal{B}_1$基表示

显然, 对任意的$\boldsymbol{x}= \alpha_1\boldsymbol{v}_1+\cdots + \alpha_n\boldsymbol{v}_n\in V$, 都有
$$
[T\boldsymbol{x}]_{\mathcal{B}_2} = \left[\sum\limits_{j=1}^{n} \alpha_j T\boldsymbol{v}_j\right]_{\mathcal{B}_2} = \sum\limits_{j=1}^{n} \alpha_j [T\boldsymbol{v}_j]_{\mathcal{B}_2} = _{\mathcal{B}_2}[T]_{\mathcal{B}_1}[\boldsymbol{x}]_{\mathcal{B}_1}
$$

### 1.4. $\mathcal{B}_1 - \mathcal{B}_2$基变换矩阵 
容易证明
$$
{}_{\mathcal{B}_2}[T]_{\mathcal{B}_2} = {}_{\mathcal{B}_2}[I]_{\mathcal{B}_1} {}_{\mathcal{B}_1}[T]_{\mathcal{B}_1} {}_{\mathcal{B}_1}[I]_{\mathcal{B}_2}
$$
因此, 我们将${}_{\mathcal{B}_2}[I]_{\mathcal{B}_1}$称为$\mathcal{B}_1 - \mathcal{B}_2$基变换矩阵.


## 2. 矩阵的秩
### 2.1. 秩-零化度定理(rank-nullity theorem)
对任意的$A\in \mathbb{M}_{m, n}(\mathbb{F})$, 有
$$
\dim(\mathrm{range}) + \dim(\mathrm{null\ space}) = \mathrm{rank}\left(A\right) + \mathrm{nullity}\left(A\right) = n
$$

### 2.2. Sylvester不等式
如果$A\in \mathbb{M}_{m, k}(\mathbb{F})$且$B\in \mathbb{M}_{k, n}(\mathbb{F})$, 那么
$$
\mathrm{rank}\left(A\right) + \mathrm{rank}\left(B\right) - k \le \mathrm{rank}\left(AB\right) \le \min\{\mathrm{rank}\left(A\right), \mathrm{rank}\left(B\right)\}
$$
___
##### Proof
不等式右侧显然成立, 下面只需要证明左侧的不等式成立. 我们用$A\sim B$表示经过一系列的初等行列变换, 可以从$A$得到$B$. 我们有
$$
\begin{pmatrix}A & I_k \\ 0 & B\end{pmatrix} \sim \begin{pmatrix}A & I_k \\ -BA & 0\end{pmatrix} \sim \begin{pmatrix}0 & I_k \\ -BA & 0\end{pmatrix}
$$
因此, 我们有
$$\mathrm{rank}\left(A\right) +\mathrm{rank}\left(B\right) \le \mathrm{rank}\begin{pmatrix}A & I_k \\ 0 & B\end{pmatrix} = \mathrm{rank}\begin{pmatrix}0 & I_k \\ -BA & 0\end{pmatrix} = k + \mathrm{rank}\left(BA\right)
$$
因此我们有
$$
\mathrm{rank}\left(A\right) + \mathrm{rank}\left(B\right) - k \le \mathrm{rank}\left(AB\right)
$$
##### 
___

### 2.3. Rank-sum不等式
如果$A, B\in \mathbb{M}_{m,n}(\mathbb{F})$, 那么
$$
|\mathrm{rank}\left(A\right) - \mathrm{rank}\left(B\right)| \le \mathrm{rank}\left(A+B\right) \le \mathrm{rank}\left(A\right) + \mathrm{rank}\left(B\right)
$$
其中第二个不等式中的等号成立当且仅当$\mathrm{range}(A) \cap \mathrm{range}(B) = \{0\}$并且$\mathrm{range}(A^{\top}) \cap \mathrm{range}(B^{\top}) = \{0\}$
___
##### Proof
不妨设$\mathrm{rank}\left(A\right)\ge \mathrm{rank}\left(B\right)$, 于是我们只需要证明
$$
\mathrm{rank}\left(A\right) - \mathrm{rank}\left(-B\right)\le \mathrm{rank}\left(A+B\right) \le \mathrm{rank}\left(A\right) + \mathrm{rank}\left(B\right)
$$
显然, 左侧的不等式和右侧的不等式在形式上是等价的, 因此, 我们只需要证明右侧的不等式成立. 设$\{\boldsymbol{v}_1, \boldsymbol{v}_2, \cdots, \boldsymbol{v}_s\}$是$A$的生成列向量, 而$\{\boldsymbol{u}_1, \boldsymbol{u}_2, \cdots, \boldsymbol{u}_t\}$是$B$的生成列向量. 显然, 
$$
\mathrm{span}(A+B)\subseteq \mathrm{span}\{\boldsymbol{v}_1, \boldsymbol{v}_2, \cdots, \boldsymbol{v}_s, \boldsymbol{u}_1, \boldsymbol{u}_2, \cdots, \boldsymbol{u}_t\}
$$
因此
$$
\mathrm{rank}\left(A+B\right) \le \mathrm{rank}\left(A\right) + \mathrm{rank}\left(B\right)
$$
如果等号成立, 那么显然有$\mathrm{range}(A) \cap \mathrm{range}(B) = \{0\}$并且$\mathrm{range}(A^{\top}) \cap \mathrm{range}(B^{\top}) = \{0\}$. 如果$\mathrm{range}(A) \cap \mathrm{range}(B) = \{0\}$并且$\mathrm{range}(A^{\top}) \cap \mathrm{range}(B^{\top}) = \{0\}$, 用反证法, 假设$\mathrm{rank}\left(A+B\right)\neq \mathrm{rank}\left(A\right) + \mathrm{rank}\left(B\right)$, 假设$\mathrm{span}\left(A+B\right) = \{\boldsymbol{v}_1, \boldsymbol{v}_2, \cdots, \boldsymbol{v}_l, \boldsymbol{u}_1, \boldsymbol{u}_2, \cdots, \boldsymbol{u}_r\}$, 这里, 我们重新排列了向量的顺序. 不妨设$l<s$, 并且
$$
\boldsymbol{\alpha}_1 + \boldsymbol{\beta}_1 = k_1\boldsymbol{v}_1 +\cdots k_s\boldsymbol{v}_s + d_1\boldsymbol{u}_1 + \cdots + d_r\boldsymbol{u}_r, \quad k_s\neq 0
$$
又因为$\boldsymbol{\alpha}_1 + \boldsymbol{\beta}_1$可以由$\{\boldsymbol{v}_1, \boldsymbol{v}_2, \cdots, \boldsymbol{v}_l, \boldsymbol{u}_1, \boldsymbol{u}_2, \cdots, \boldsymbol{u}_r\}$生成, 这意味着
$$
a_1\boldsymbol{v}_1 +\cdots a_s\boldsymbol{v}_s + b_1\boldsymbol{u}_1 + \cdots + b_r\boldsymbol{u}_r = 0, \quad a_s\neq 0
$$
这和线性无关相矛盾! 因此, 我们得到了等号成立当且仅当$\mathrm{range}(A) \cap \mathrm{range}(B) = \{0\}$并且$\mathrm{range}(A^{\top}) \cap \mathrm{range}(B^{\top}) = \{0\}$. 
#####
___

### 2.4. Frobenius不等式
如果$A\in \mathbb{M}_{m, k}(\mathbb{F})$, $B\in \mathbb{M}_{k, p}(\mathbb{F})$, $C\in \mathbb{M}_{p,n}(\mathbb{F})$, 那么
$$
\mathrm{rank}\left(AB\right) + \mathrm{rank}\left(BC\right) \le \mathrm{rank}\left(B\right) +\mathrm{rank}\left(ABC\right)
$$
其中等号成立当且仅当存在矩阵$X$和$Y$, 使得$B=BCX+YAB$
___
##### Proof
仍然考虑初等变换, 我们有
$$
\begin{pmatrix} ABC & 0 \\ 0 & B\end{pmatrix} \sim \begin{pmatrix} ABC & -AB \\ 0 & B\end{pmatrix} \sim \begin{pmatrix} 0 & -AB \\ BC & B\end{pmatrix}
$$
于是我们有
$$
\mathrm{rank}\left(ABC\right) + \mathrm{rank}\left(B\right) = \mathrm{rank} \begin{pmatrix} 0 & -AB \\ BC & B\end{pmatrix} \ge \mathrm{rank}\left(AB\right) + \mathrm{rank}\left(BC\right)
$$
如果$B = BCX + YAB$, 那么
$$
\begin{pmatrix} 0 & -AB \\ BC & B\end{pmatrix} \sim \begin{pmatrix} 0 & -AB \\ BC & 0\end{pmatrix}
$$
因此, 等号成立. 而如果等号成立, 也就是说$\mathrm{rank} \begin{pmatrix} 0 & -AB \\ BC & B\end{pmatrix} = \mathrm{rank}\left(AB\right) + \mathrm{rank}\left(BC\right)$, 因此存在矩阵$X$和$Y$, 使得$B=BCX+YAB$. 
#####
___

### 2.5. Wedderburn化简公式
如果$A\in \mathbb{M}_{m, n}(\mathbb{F})$, $X\in \mathbb{M}_{n, k}(\mathbb{F})$以及$Y\in \mathbb{M}_{m, k}(\mathbb{F})$, 并且$W = Y^{\top}AX$是非奇异矩阵, 那么
$$
\mathrm{rank}\left(A - AXW^{-1}Y^{\top}A\right) = \mathrm{rank}\left(A\right) - \mathrm{rank}\left(AXW^{-1}Y^{\top}A\right)
$$
如果$\boldsymbol{x}\in\mathbb{F}^n$且$\boldsymbol{y}\in \mathbb{F}^m$, $\omega = \boldsymbol{y}^\top A\boldsymbol{x}\neq 0$, 那么
$$
\mathrm{rank}\left(A - \omega^{-1}A\boldsymbol{xy}^{\top}A\right) = \mathrm{rank}\left(A\right) -1
$$
这个公式称为Wedderburn秩1化简公式
___
##### Proof
为了简化表达, 我们用$B$表示$AXW^{-1}Y^{\top}A$, 利用初等变换, 我们有
$$
\left(\begin{array}{cc}
A-B & 0 \\
0 & B
\end{array}\right) \sim \left(\begin{array}{cc}
A & B \\
B & B
\end{array}\right) \sim \left(\begin{array}{cc}
A & 0 \\
0 & B\left(I-X W^{-1} Y^T A\right)
\end{array}\right)
$$
再根据$B$的定义, 我们有
$$
B\left(I-X W^{-1} Y^T A\right) = AXW^{-1}Y^{\top}A\left(I-X W^{-1} Y^T A\right) = 0
$$
这就证明了
$$
\mathrm{rank}\left(A - B\right) + \mathrm{rank}\left(B\right)  = \mathrm{rank}\left(A\right)
$$
#####
___

### 2.6. Wedderburn化简公式的逆
如果$\sigma\in \mathbb{F}$, $\boldsymbol{u}\in \mathbb{F}^n$, $\boldsymbol{v}\in \mathbb{F}^m$, 且
$$
\mathrm{rank}\left(A - \sigma \boldsymbol{uv}^{\top}\right) <\mathrm{rank}\left(A\right)
$$
那么
$$
\mathrm{rank}\left(A - \sigma \boldsymbol{uv}^{\top}\right) = \mathrm{rank}\left(A\right) - 1
$$
且存在$\boldsymbol{x}\in \mathbb{F}^n$以及$\boldsymbol{y}\in \mathbb{F}^m$, 使得$\boldsymbol{u}=A\boldsymbol{x}$, $\boldsymbol{v}=A^{\top}\boldsymbol{y}$, $\boldsymbol{y}^{\top}A\boldsymbol{x}\neq 0$以及$\sigma=(\boldsymbol{y}^{\top}A\boldsymbol{x})^{-1}$

___
##### Proof
根据[2.2. Rank-sum不等式](#2.2.%20Rank-sum不等式),我们有
$$
\mathrm{rank}\left(A - \sigma\boldsymbol{uv}^{\top}\right) \ge |\mathrm{rank}\left(A\right) - \mathrm{rank}\left(\sigma \boldsymbol{uv}^{\top}\right)| = \mathrm{rank}\left(A\right) - 1
$$
又因为
$$
\mathrm{rank}\left(A - \sigma \boldsymbol{uv}^{\top}\right) <\mathrm{rank}\left(A\right)
$$
于是我们有
$$
\mathrm{rank}\left(A - \sigma \boldsymbol{uv}^{\top}\right) = \mathrm{rank}\left(A\right) - 1
$$
根据Rank-sum不等式的取等条件, 我们知道$\boldsymbol{u}\in \mathrm{span}\left(A\right)$并且$\boldsymbol{v}\in \mathrm{span}\left(A^{\top}\right)$. 于是存在$\boldsymbol{x}\in \mathbb{F}^n$以及$\boldsymbol{y}\in \mathbb{F}^m$, 使得$\boldsymbol{u}=A\boldsymbol{x}$, $\boldsymbol{v}=A^{\top}\boldsymbol{y}$, 于是
$$
\mathrm{rank}\left(A - \sigma A\boldsymbol{xy}^{\top}A\right) = \mathrm{rank}\left(A\right) - 1
$$
用$B$表示$\sigma A\boldsymbol{xy}^{\top}A$, 我们有
$$
\left(\begin{array}{cc}
A-B & 0 \\
0 & B
\end{array}\right) \sim \left(\begin{array}{cc}
A & B \\
B & B
\end{array}\right) \sim \left(\begin{array}{cc}
A & 0 \\
0 & B\left(I-\sigma \boldsymbol{xy}^T A\right)
\end{array}\right)
$$
于是我们有
$$
\mathrm{rank}\left(A-B\right) + 1 = \mathrm{rank}\left(A\right) + \mathrm{rank}\left\{B(1 - \boldsymbol{y}^{\top}A\boldsymbol{x})\right\} \implies \mathrm{rank}\left\{B(1 - \sigma\boldsymbol{y}^{\top}A\boldsymbol{x})\right\} = 0
$$
因此我们有$\boldsymbol{y}^{\top}A\boldsymbol{x}\neq 0$以及$\sigma=(\boldsymbol{y}^{\top}A\boldsymbol{x})^{-1}$. 
#####
___

