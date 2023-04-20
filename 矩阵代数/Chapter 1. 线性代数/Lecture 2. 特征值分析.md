## 1. 特征值

### 1.1. 定义

若非零向量$\boldsymbol{u}$作为线性算子$\mathcal{L}$的输入时, 所产生的输出与输入只相差一个常数因子$\lambda$, 即
$$
\mathcal{L}(\boldsymbol{u}) = \lambda \boldsymbol{u}, \quad \boldsymbol{u}\neq 0
$$
则称向量$\boldsymbol{u}$是线性算子$\mathcal{L}$的特征向量, 称标量$\lambda$为线性算子$\mathcal{L}$的特征值. 当线性算子为矩阵时, 我们就得到了矩阵的特征值与特征向量. 写成
$$
(A-\lambda I)\boldsymbol{u} = 0
$$

### 1.2 代数多重度与几何多重度

1. **代数多重度**: 称$A$的特征值$\lambda$具有代数多重度$\mu$, 若$\lambda$是特征多项式$|A - zI|=0$的$\mu$重根. 若特征值$\lambda$的代数多重度为$1$, 则称该特征值为单特征值. 非单的特征值称为多重特征值
2. **几何多重度**: 称$A$的特征值$\lambda$具有几何多重度$\gamma$, 若与$\lambda$对应的线性无关的特征向量的个数为$\gamma$, 换言之, 几何多重度是特征空间$\mathrm{Ker}(A-\lambda I)$的维数
3. **半单特征值**: 一个特征值称为半单特征值, 如果其代数多重度等于其几何多重度, 不是半单的特征值称为亏损特征值.

### 1.1. 特征值分解

设$A$是一个$n\times n$的对称矩阵, 则$A$可以被写成
$$
A = Q\Lambda Q^{\top} 
$$
其中$Q\in \mathbb{R}^{n\times n}$是正交矩阵, $\Lambda=\mathrm{diag}\{\lambda_1, \lambda_2,\cdots,\lambda_n\}$. $\lambda_i$是矩阵$A$的实特征值. $Q$的列是矩阵$A$的对应于$\lambda_i$的特征向量. 该分解称为矩阵$A$的特征值分解.
**特征值的求法**: 我们用$\lambda_i(A)$表示矩阵$A$第$i$大的特征值, $\lambda_1(A) = \lambda_{\mathrm{max}}(A)$, $\lambda_n(A) = \lambda_{\mathrm{min}}(A)$. 可以证明对于对称矩阵$A$
$$
\lambda_{\mathrm{max}}(A)=\sup_{\boldsymbol{x}\neq 0}\frac{\boldsymbol{x}^{\top} A\boldsymbol{x}}{\boldsymbol{x}^{\top} \boldsymbol{x}},\quad \lambda_{\mathrm{min}}(A)=\inf_{\boldsymbol{x}\neq 0} \frac{\boldsymbol{x}^{\top} A\boldsymbol{x}}{\boldsymbol{x}^{\top} \boldsymbol{x}}
$$
此外, 如果我们已经得到了$\lambda_1, \lambda_2, \cdots,\lambda_k$和对应的特征向量$\boldsymbol{x}_1, \boldsymbol{x}_2, \cdots, \boldsymbol{x}_k$, 那么
$$
\lambda_{k+1}(A) = \sup_{\boldsymbol{x}\neq 0, \langle\boldsymbol{x}_i, \boldsymbol{x}  \rangle = 0, \forall i=1,2,\cdots,k} \frac{\boldsymbol{x}^{\top}A\boldsymbol{x}}{\boldsymbol{x}^{\top} \boldsymbol{x}} 
$$
**正定矩阵的squareroot**: 设$A$是正定矩阵, 其特征值分解是
$$
A = Q\mathrm{diag}\{\lambda_1, \lambda_2, \cdots, \lambda_n\}Q^{\top}
$$
我们可以定义$A$的对称的平方根矩阵为
$$
A^{1/2}=Q\mathrm{diag}\{\lambda_1^{1/2}, \lambda_2^{1/2}, \cdots, \lambda_n^{1/2}\}Q^{\top}
$$
则Square root $A^{1/2}$是矩阵方程$X^2=A$的唯一的对称半正定解.
