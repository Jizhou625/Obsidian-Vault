## 1. 卷积层的动机
### 1.1. 稀疏交互(sparse interaction)
全连接的神经网络使用矩阵乘法来建立输入和输出之间的联系. 其中, 参数矩阵的每一个单独的参数都描述了一个输入单元与输出单元的交互. 然而, 卷积神经网络具有稀疏交互的特征, 这是使核的大小远小于输入的大小来达到的. 

### 1.2. 参数共享(parameter sharing)
参数共享是指在一个模型的多个函数中使用相同的参数, 对于传统的神经网络, 当计算一层的输出时, 权重矩阵的每一个元素只使用一次. 而卷积神经网络含有绑定的权重, 核的每一个元素都作用在输入的每一个位置上. 

### 1.3. 等变表示(equivariant representation)
如果函数$f(x)$与$g(x)$满足$f(g(x)) = g(f(x))$, 我们就说$f(x)$对于变换$g$具有等变性. 对于卷积来说, 如果令$g$是输入的任何平移函数, 那么卷积函数对于$g$具有等变性. 

**区分等变性(equivariance)和不变性(invariance)**: 平移等变性(equivariance)是指随着输入平移, 输出也发生相应的平移. 平移不变性(invariance)是指随着输入平移, 输出不发生改变. 卷积层并不具有平移不变性的性质. 

**Example**: 在图像处理中, 卷积产生了一个二维映射来表明某些特征在输入中出现的位置, 如果我们移动输入中的图像, 它的表示也会在输出中移动相同的位置. 

**Limitation**: 卷积对其他的一些变换并不是天然等变的, 例如对于图像的放缩或者旋转, 这需要其他的机制来进行处理. 

### 1.4. 对卷积层的先验概率解释
我们可以把卷积层类比成全连接网络, 但对于这个全连接网络的权重有一个无限强的先验, 这个无限强的先验是说一个隐藏单元的权重必须与它的邻居的权重相同, 但可以在空间中连续. 除此之外, 这个先验也要求除了那些处在隐藏单元的小的空间连续的接受域内的权重以外, 其余的权重都为0.

**Comment**: 当一项任务涉及要对输入中相隔较远的信息进行合并时, 卷积所利用的先验就不正确了, 这会导致欠拟合.

## 2. 关于卷积层的讨论
### 2.1. 卷积层的步幅
我们有时候会希望跳过核中的一些位置来降低计算的开销. 我们可以把这个过程看作是对全卷积函数输出的下采样. 例如我们可以在输入的每个方向上每间隔$s$个像素进行采样, 我们把$s$称为是下采样卷积的步幅(stride). 当然也可以对不同的移动方向定义不同的步幅.  

### 2.2. 零填充
1. **有效卷积**: 有效卷积是指无论如何都不使用零填充的极端情况, 并且卷积核只允许访问那些图像中能够完全包含整个核的位置. 如果输入的宽度是$m$, 核的宽度是$k$, 那么输出的宽度就会变成$m-k+1$
2. **相同卷积**: 相同卷积是指进行足够的零填充来保持输入和输出具有相同的大小. 然而, 输入像素中靠近边界的部分相比于中间的部分对输出像素的影响更小, 这可能会造成一定程度上对边界像素的欠表示
3. **全卷积**: 进行足够多的零填充, 使得每个像素在每个方向上恰好被访问了$k$次, 最后图像的宽度为$m+k-1$. 但在这种情况下, 输出像素中靠近边界的部分相比于中间的部分是更少的像素, 这将导致学得一个在卷积特征映射的所有位置都表现出色的单核更加困难. 

**comment**: 通常零填充的最优数量处于有效卷积和相同卷积之间的某个位置. 

## 3. 关于池化层的讨论
### 3.1. 池化层的动机
使用池化可以看作增加了一个无限强的先验, 这一层学得的函数必须具有对少量平移的不变性. 局部平移不变性是一个很有用的性质, 尤其是当我们关心某个特征是否出现而不关心它出现的具体位置时. 当局部平移不变性的假设成立时, 池化可以极大地提高网络的统计效率.  

**Comment 1**: 从信号处理的角度，avg_pool 的作用主要是做低通滤波，max_pool 的作用类似，都是将一些高频细节过滤掉，保留低频突出的特征. 直觉上看，pool 能忽略其感受野范围内的位置信息，可以使网络具有一定的invariance。但也有文章实验性的证明了卷积网络的 invariance 和 pool 没多大关系

**Comment 2**: 如果一项任务依赖于保存精确的空间信息, 那么在所有特征上使用池化会增大训练误差, 导致欠拟合. 

### 3.2. 全局平均池化层
在GAP被提出之前，常用的方式是将feature map直接拉平成一维向量（下图左），但是GAP不同，是将每个通道的二维图像做平均，最后也就是每个通道对应一个均值（下图右）

![v2-2cf5f9802fe6b0f675ffc35b7d57c3e6_r](./Lecture%203.%20CNN.assets/v2-2cf5f9802fe6b0f675ffc35b7d57c3e6_r.jpg)


**全局池化层的优势**: 
      1. **抑制过拟合**: 直接拉平做全连接层的方式依然保留了大量的空间信息，假设feature map是32个通道的$10\times 10$图像，那么拉平就得到了$32\times 10\times 10$的向量，如果是最后一层是对应两类标签，那么这一层就需要$3200\times 2$的权重矩阵，而GAP不同，将空间上的信息直接用均值代替，32个通道GAP之后得到的向量是$32\times 1$的向量，那么最后一层只需要$32\times 2$的权重矩阵。
      2. **输入尺寸更灵活**: feature map经过GAP后的神经网络参数不再与输入图像尺寸的大小有关，也就是输入图像的长宽可以不固定
      3. **可解释性**: GAP相比全连接更加自然地加强了类别和feature map之间的联系. 

### 3.3. FcaNet频域通道注意力机制

考虑二维图像的余弦变换(DCT)
$$
\begin{aligned}
& f_{h, w}^{2 d}=\sum_{i=0}^{H-1} \sum_{j=0}^{W-1} x_{i, j}^{2 d} \underbrace{\cos \left(\frac{\pi h}{H}\left(i+\frac{1}{2}\right)\right) \cos \left(\frac{\pi w}{W}\left(j+\frac{1}{2}\right)\right)}_{\text {DCT weights }}, \\
& \text { s.t. } h \in\{0,1, \cdots, H-1\}, w \in\{0,1, \cdots, W-\mathrm{I}\},
\end{aligned}
$$
二维图像的每个元素也可以表示为一系列的DCT和基底乘积之和, 可以看到
$$
\begin{aligned}
& x_{i, j}^{2 d}=\sum_{h=0}^{H-1} \sum_{w=0}^{W-1} f_{h, w}^{2 d} \cos \left(\frac{\pi h}{H}\left(i+\frac{1}{2}\right)\right) \cos \left(\frac{\pi w}{W}\left(j+\frac{1}{2}\right)\right) \\
& = f_{0,0}^{2 d} B_{0,0}^{i, j}+f_{0,1}^{2 d} B_{0,1}^{i, j}+\cdots+f_{H-1, W-1}^{2 d} B_{H-1, W-1}^{i, j} \\
& = \mathrm{GAP}\left(x^{2 d}\right) H W+f_{0,1}^{2 d} B_{0,1}^{i, j}+\cdots+f_{H-1, W-1}^{2 d} B_{H-1, W-1}^{i, j} \\
& \text { s.t. } i \in\{0,1, \cdots, H-1\}, j \in\left\{0,1, \cdots, W-1\right\} \\
&
\end{aligned}
$$

## 4. 关于CNN平移不变性(invariance)的讨论

### 4.1. 卷积层的效果
在信号处理中，卷积（以及相关）的性质包含了平移等变性。对于共享权值的卷积层来说，只在平移量为stride的整数倍时平移等变性才严格成立。而仅仅在卷积核比较均匀而且输入也有很多均匀区域的时候才有比较弱的平移不变性，因为此时微小的移动对于输出改变比较少. 

### 4.2. 池化层的效果
普通池化层中，均值池化等价于固定卷积核的卷积层，因此性质也相同；最大值池化也类似，但取最大值的操作使其相对于均值带有更强的平移不变性。全局池化层将整个输入变成1x1大小的输出，忽略了特征的位置信息，当前面的输入具有平移等变性的时候具有比较强的平移不变性。

### 4.3. 全连接层的效果
全连接层既不具有平移不变性, 也不具有平移等变性，这是因为没有在不同位置共享权值，特征在不同位置对于输出的贡献变化很大

### 4.4. 总体效果
1. **CNN网络本身一般不具有Invariance**: 如果把这些层串起来，那么在使用全连接层的时候整个CNN的结构一般不具有平移不变性。就算用了全局池化层，由于前面叠加的多层卷积层的累计效应，全局池化层输入也基本上不具有平移等变性, 因此最后输出的平移不变性也很弱，只有当位移是整个网络的降采样倍数的整数倍才存在，概率很低。
2. **Invariance来源于参数(数据的学习)**: 能用于分类的平移不变性主要来源于参数。因为卷积层的平移等变性，这种平移不变性主要是由最后的全连接层来学习，而没有全连接层的卷积神经网络很难有这种性质。参数的学习需要数据，由于数据中平移的分布一般都比较不均匀，引入平移的数据增强（augmentation）肯定是必要的。 裁切（crop）就是一种平移的数据增强方式，因为不同裁切方式对应的patch之间的变换就是平移。而且这种方式相比于平移更加自然，没有周围的黑边padding，因此更加常用。
3. **Augmentation不一定可以完全带来平移不变性**: 即使只考虑平移, 如果降采样的倍数时$n$, 就需要$O(n^2)$的样本数量才能保证平移不变性. 再加上旋转和尺度变化就更不可能了. 
4. **平移不变性的其他解释**: 因为拍照的人也有一定的位置bias, 所以测试集的平移分布也和训练集类似，而当测试集和训练集同分布时, 可以证明泛化效果最好. 

## 5. 梯度计算
### 5.1. 全连接神经网络的梯度计算
**模型**: 设$\boldsymbol{x}$是神经网络的输入, 第$i$层到第$i+1$层通过线性层和激活层的表达式为
$$
  \boldsymbol{s}_{i} = W_i\boldsymbol{z}_i+\boldsymbol{b}_i,\quad \boldsymbol{z}_{i+1} = f(\boldsymbol{s}_i) 
$$
  这里$\boldsymbol{s}_i$是线性层的输出, $\boldsymbol{z}_{i+1}$是激活层的输出, 同时是下一线性层的输入

对cost function求导可以得到
$$
\dfrac{\partial \mathrm{Cost}}{\partial \boldsymbol{\boldsymbol{s}_i^{\top}}} = \dfrac{\partial \mathrm{Cost}}{\partial \boldsymbol{\boldsymbol{s}_{i+1}^{\top} }}\dfrac{\partial \boldsymbol{s}_{i+1}  }{\partial \boldsymbol{s}_i^{\top} } = \dfrac{\partial \mathrm{Cost}}{\partial \boldsymbol{\boldsymbol{s}_{i+1}^{\top} }} \dfrac{\partial W_{i+1}f(\boldsymbol{s}_i ) }{\partial f(\boldsymbol{s}_i)^{\top} } \dfrac{\partial f(\boldsymbol{s}_i) }{\partial \boldsymbol{s}_i^{\top} } = \dfrac{\partial \mathrm{Cost}}{\partial \boldsymbol{\boldsymbol{s}_{i+1}^{\top} }} W_{i+1} \mathrm{diag}\{f^{\prime}(\boldsymbol{s}_i)\}  
$$
写成梯度的形式为
$$
\nabla_{\boldsymbol{s}_i} \mathrm{Cost} = \mathrm{diag}\{f^{\prime}(\boldsymbol{s}_i)\}\cdot W^{\prime}_{i+1} \cdot \nabla_{\boldsymbol{s}_{i+1}} \mathrm{Cost} = f^{\prime}(\boldsymbol{s}_i) \odot (W^{\prime}_{i+1} \cdot \nabla_{\boldsymbol{s}_{i+1}} \mathrm{Cost})
$$
将$W_i$进行向量化, 我们有
$$
\boldsymbol{s}_i = (\boldsymbol{z}_i^{\top} \otimes I)\mathrm{vec}(W)+\boldsymbol{b_i}
$$
$$
\dfrac{\partial \mathrm{Cost} }{\partial \mathrm{vec}^{\top} (W_i)} = \dfrac{\partial \mathrm{Cost} }{\partial \boldsymbol{s}_i^{\top} } (\boldsymbol{z}_i^{\top} \otimes I) =\boldsymbol{z}_i^{\top} \otimes \dfrac{\partial \mathrm{Cost} }{\partial \boldsymbol{s}_i^{\top} }  
$$
再进行矩阵化可以得到
$$
\nabla_{W_i} \mathrm{Cost} = \boldsymbol{z}_i^{\top} \otimes \nabla_{\boldsymbol{s}_i} \mathrm{Cost} = \nabla_{\boldsymbol{s}_i} \mathrm{Cost} \cdot \boldsymbol{z}_i^{\top}
$$
### 5.2. 卷积层和激活层的梯度计算
设$\boldsymbol{x}$是神经网络的输入, 第$i$层到第$i+1$层通过线性层和激活层的表达式为
$$
  \boldsymbol{s}_i = W_i\boldsymbol{z}_{i}+ b_i,\quad \boldsymbol{z}_{i+1} = f(\boldsymbol{s}_i) 
$$
  这里$\boldsymbol{z}_{ij}$是$k^2c\times1$的向量, 表示$c$个通道的$k\times k$个相邻像素点. 用$n=k^2c$记录卷积层的连接数, $W$是一个$d\times n$的矩阵, $d$表示滤波器的数量. 
