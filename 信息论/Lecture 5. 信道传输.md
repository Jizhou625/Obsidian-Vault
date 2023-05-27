## 1. 离散信道
### 1.1. 离散信道(discrete channel)
离散信道是由输入字母表$\mathcal{X}$, 输出字母表$\mathcal{Y}$和概率转移矩阵$p(y\mid x)$构成的系统, 其中$p(y\mid x)$表示发送字符$x$的条件下收到输出字符$y$的概率. 如果输出的概率分布仅依赖于它的输入, 而与先前信道的输入和输出条件独立, 就称这个信道是无记忆的. 

### 1.2. 信道容量(channel capacity)
离散无记忆信道的信息信道容量定义为
$$
C=\max\limits_{p(x)}I(X,Y)
$$
这里的最大值取自所有可能的输入分布$p(x)$

### 1.3. 对称信道
如果信道转移矩阵$p(y\mid x)$的任意两行互相置换, 任意两列也互相置换, 那么称该信道是对称的. 

如果转移矩阵的每一行$p(\cdot\mid x)$都是其他每行的置换, 而所有列的元素和$\sum\limits_{x}p(y\mid x)$相等, 则称这个信道是弱对称的. 

例如下面的转移矩阵$A$是弱对称但不是对称的

$$
A=\begin{pmatrix}
    \dfrac{1}{3} & \dfrac{1}{6} & \dfrac{1}{2} \\
    
    \\
    
    \dfrac{1}{3} & \dfrac{1}{2} & \dfrac{1}{6}
    \end{pmatrix}
$$

### 1.4. 对称和弱对称信道的信道容量
对于(弱)对称信道, 用$\boldsymbol{r}$表示转移矩阵的一行, 则有
$$
I(X;Y)=H(Y)-H(Y\mid X)\le \log|\mathcal{Y}|-H(\boldsymbol{r})
$$
等号成立当且仅当输出为均匀分布, $p(x)=\dfrac{1}{|\mathcal{X}|}$可以使得$Y$达到均匀分布.

### 1.5. 信道容量的例子
#### 1.5.1. 无噪声二元信道
对于无噪声二元信道, 它的二元输入在输出端能够精确地重现. 

![image-20230526235454408](Lecture%205.%20信道传输.assets/image-20230526235454408.png)

其信道容量$C = \max I(X; Y)=1$, 且在$p(x) =\left(\dfrac{1}{2}, \dfrac{1}{2}\right)$处取到

#### 1.5.2. 二元对称信道
考虑如下图所示的二元对称信道(Binary Symmetric Channel, BSC), 这个二元信道的输入字符以概率$p$互补. 

![image-20230527000130806](Lecture%205.%20信道传输.assets/image-20230527000130806.png)

其信道容量为$C = 1 - H(p)$, 当输入分布是均匀分布时等号成立. 
$$
\begin{aligned} 
    I(X; Y) & = H(Y) - H(Y\mid X)\\ 
    & = H(Y) - \sum\limits_{x}p(x)H(Y\mid X=x)\\
    & = H(Y) - \sum\limits_{x}^{} p(x)H(p) \\ 
    & = H(Y) - H(p) \\
    &\le 1 - H(p)
\end{aligned}
$$

### 1.5.3. 二元擦除信道
二元擦除信道(Binary Erasure Channel, BEC)的的输入字符以概率$\alpha$的概率被擦除, 并且接收者知道是哪些比特已经被擦除了
![image-20230527000557535](Lecture%205.%20信道传输.assets/image-20230527000557535.png)
设$\mathbb{P}(X=1) = \pi$. 
$$
H(Y) = H((1-\pi)(1-\alpha), \alpha, \pi(1-\alpha)) = H(\alpha) + (1-\alpha) H(\pi)
$$
因此
$$
\begin{aligned} 
    C & = \max\limits_{p(x)}I(X; Y)\\
    & = \max\limits_{p(x)}H(Y) - H(Y\mid X)\\ 
    & = \max\limits_{p(x)}H(Y) - H(\alpha)\\
    & = H(\alpha) + (1-\alpha) H(\pi) - H(\alpha) \\ 
    & = 1-\alpha
\end{aligned}
$$
当$\pi=\dfrac{1}{2}$时, 等号成立. 
