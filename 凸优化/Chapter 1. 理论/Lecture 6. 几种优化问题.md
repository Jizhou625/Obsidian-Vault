## 1. 线性规划问题
### 1.1. 线性规划的一般形式
当目标函数和约束函数都是仿射时, 问题称为线性规划(LP)问题. 一般的线性规划问题可以写成如下的形式:
$$
\begin{array}{ll}
\operatorname{minimize} & \boldsymbol{c}^{\top} \boldsymbol{x}+\boldsymbol{d} \\
\text { subject to } & G \boldsymbol{x} \preceq \boldsymbol{h} \\
& A \boldsymbol{x} = \boldsymbol{b}
\end{array} \tag{1}
$$
其中$G\in \mathbb{R}^{m\times n}$, $A\in \mathbb{R}^{p\times n}$

### 1.2. 线性规划的标准形式
标准形式的线性规划中仅有的不等式都是分量的非负约束$\boldsymbol{x}\succeq \boldsymbol{0}$
$$
\begin{array}{ll}
\operatorname{minimize} & \boldsymbol{c}^{\top} \boldsymbol{x} \\
\text { subject to } & A \boldsymbol{x} = \boldsymbol{b} \\
& \boldsymbol{x} \succeq \boldsymbol{0}
\end{array} \tag{2}
$$

有时需要将一般的线性规划(1)转化为标准形式(2), 第一步是引入松弛变量$s_i$, 得到
$$
\begin{array}{ll}
\operatorname{minimize} & \boldsymbol{c}^{\top} \boldsymbol{x}+\boldsymbol{d} \\
\text { subject to } & G \boldsymbol{x}+\boldsymbol{s}=\boldsymbol{h} \\
& A \boldsymbol{x}=\boldsymbol{b} \\
& \boldsymbol{s} \succeq 0 
\end{array}
$$
下一步是将变量$\boldsymbol{x}$表示为两个非负变量$\boldsymbol{x}^+$和$\boldsymbol{x}^{-}$的差, 即$\boldsymbol{x}=\boldsymbol{x}^{+}-\boldsymbol{x}^{-}$, 于是有
$$
\begin{array}{ll}
\operatorname{minimize} & \boldsymbol{c}^{\top} \boldsymbol{x}^{+}-\boldsymbol{c}^\top \boldsymbol{x}^{-}\\
\text { subject to } & G \boldsymbol{x}^{+}-G \boldsymbol{x}^{-}=\boldsymbol{h} - \boldsymbol{s} \\
& A \boldsymbol{x}^{+}-A \boldsymbol{x}^{-}=\boldsymbol{b} \\
& \boldsymbol{x}^{+} \succeq 0, \quad \boldsymbol{x}^{-} \succeq 0, \quad \boldsymbol{s} \succeq 0,
\end{array}
$$
这是一个标准形式的线性规划. 

## 2. 