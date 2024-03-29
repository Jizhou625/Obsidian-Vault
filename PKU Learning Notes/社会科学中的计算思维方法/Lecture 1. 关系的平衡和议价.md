## 1. 网络的平衡
### 1.1. 完全图的平衡
我们称一个三节点的完全图是平衡的, 当且仅当在这个节点组中, 要么三条边都被标记为$+$, 要么只有一条边被标记为$+$. 

我们称一个完全图是平衡的, 当且仅当它其中的每一个三节点的节点组都是平衡的. 这个条件可以规约为以下两种情形之一: 
1. 完全图中的任意一条边都是$+$
2. 完全图的节点集可以被分成两组, 组内的所有边都被标记为$+$, 组间的所有边都被标记为$-$.


### 1.2. 一般网络的平衡
一个非完全图, 如果通过增加一些边可以形成平衡的完全图, 则称该图是平衡的. 

一般网络的平衡问题可以被规约为: 标注图图$G$的节点集可以被划分为两组, 组内的所有边都被标记为$+$, 组间的所有边都被标记为$-$.


### 1.3. 平衡网络的刻画
一个标注图是平衡的, 当且仅当它不包含有奇数条负关系边的圈. 
___
##### Proof
对于一个平衡的标注图, 假设其存在一个圈$v_1v_2\cdots v_k v_1$含有奇数条负关系边. 由于平衡的标注图的节点集可以被划分为两组, 组内所有边都是正关系边, 组间所有边都是负关系边. 因此负关系边连接的两个端点属于不同的组. 沿着圈走下去就得到了$v_1$和$v_1$应该属于不同的组, 矛盾!

假设一个标注图不含有包含奇数条负关系边的圈. 那么从任何一个节点$v$出发. 将正关系边连接的两个端点放入同一组, 将负关系边连接的两个端点放入不同组. 最后得到了标注图节点集合的一个划分. 这个划分满足组内的所有边都被标记为$+$, 组间的所有边都被标记为$-$, 因此是平衡的. 
#####
___

### 1.4. 近似平衡的网络
设定$\varepsilon\in \left[0, \dfrac{1}{8}\right)$为任意数, 定义$\delta = \sqrt[3]{\varepsilon}$. 如果在完全图中至少有$1-\varepsilon$占比的三角形是平衡的, 那么有下面两种情形之一成立
1. 至少存在$1-\delta$占比的节点, 其中至少$1-\delta$占比的节点对都互为朋友
2. 可以将节点划分为两个集合, 满足集合内部至少有$1-\delta$占比的节点对互为朋友, 而集合间至少有$1-\delta$占比的节点对互为敌人.

这里$\delta$和$\varepsilon$的关系无法再改进. 
___
##### Proof
对于有$N$个节点的完全图, 三角形的总数为$\dfrac{N(N-1)(N-2)}{6}$. 不平衡三角形的总数最多为$\varepsilon\dfrac{N(N-1)(N-2)}{6}$, 定义节点的不平衡量为其所涉及的不平衡三角形数, 记为$\mathrm{ub}(v)$. 则
$$
\sum\limits_{v}^{} \mathrm{ub}(v) = \varepsilon\dfrac{N(N-1)(N-2)}{6} \le \varepsilon\dfrac{N^3}{6}
$$
根据鸽笼原理, 至少存在一个节点$A$, $\mathrm{ub}(A)\le \varepsilon\dfrac{N^2}{2}$. 我们将图分成两个集合, 集合$X$包含节点$A$和它的所有朋友, 集合$Y$包含$A$的所有敌人. 

集合$X$中的两个节点之间的负关系边, 对应一个包含节点$A$的不平衡三角形, 由于最多有$\dfrac{\varepsilon N^2}{2}$个不平衡三角形包含节点$A$, 所以在集合$X$中最多有$\dfrac{\varepsilon N^2}{2}$个负关系边. 同理, 集合$Y$中也最多有$\dfrac{\varepsilon N^2}{2}$个负关系边. $X$和$Y$之间最多有$\dfrac{\varepsilon N^2}{2}$个正关系边. 

设$x$为集合$X$中的节点数, $y$为集合$Y$中的节点数. 如果$x\ge (1-\delta)N> \dfrac{1}{2}N$. 此时$X$中的负关系边占比至多为
$$
\mathrm{prop}(\mathrm{neg}) \le \dfrac{\varepsilon N^2 / 2}{x(x-1)/2} <\delta 
$$
符合情形1的情况. 同理,  如果$y\ge (1-\delta)N> \dfrac{1}{2}N$, 也符合情形1的情况.

当$X$和$Y$都含有少于$(1-\delta) N$个节点时. 对于$X$和$Y$之间的边, 正关系边的占比至多为
$$
\mathrm{prop}(\mathrm{pos}) = \dfrac{\varepsilon N^2 / 2}{x y} <\dfrac{\varepsilon N^2 / 2}{\delta(1-\delta)N^2} < \delta
$$
对$X$和$Y$内部的边, 负关系边的占比至多为
$$
\mathrm{prop}(\mathrm{neg}) = \dfrac{\varepsilon N^2 / 2}{x(x-1)/2} < \dfrac{\varepsilon N^2 / 2}{\delta^2N^2/2} = \delta
$$
这就证明了其符合情形2的情况. 
#####
___

## 2. 网络中的议价与权力
### 2.1. 网络中的位置权力
1. **依赖性(dependence)**: 某些节点社会关系的价值完全来源于另一个节点的存在. 例如下图中的节点$A$和$C$完全依赖于$B$而存在, 但对于$B$来说, 它有多种选择
2. **排他性(exclusion)**: 某个节点可以单方面任意选择一个节点，但被选择的节点没有其他选择的权力. 例如下图中的节点$B$对$A$和$C$有排他性的权力, 但$B$对$D$不具有排他性的权力. 
3. **饱和性(satiation)**: 对于一个足够有权力的节点而言, 建立新的关系的边际收益递减
4. **介数(betweenness)**: 一个具有高介数的节点应该出现在许多其他节点对的路径上, 一般而言介数是中心性测度的反映. 例如下图中的节点$B$具有高介数. 但是介数高的点在某些情况下未必拥有很大的权力。

![1cd5851e450a43280906274ab434387](./Lecture%201.%20%E5%85%B3%E7%B3%BB%E7%9A%84%E5%B9%B3%E8%A1%A1%E5%92%8C%E8%AE%AE%E4%BB%B7.assets/1cd5851e450a43280906274ab434387.png)

### 2.2. 纳什议价解

当$A$和$B$就如何划分$\$1$进行谈判时, 若$A$有外部选项$x$, $B$有外部选项$y$, 且$x+y\le 1$. 则$A, B$两人等分$1-x-y$的剩余, 我们把这种情形下$A$和$B$获得的最终钱数称为纳什议价解. 

### 2.3. 稳定结果
给定一组匹配和节点价值, 不稳定性是指对于任意不在匹配中的边, 其两个端点$X$和$Y$的价值之和小于$1$. 一个网络交换的结果是稳定的, 当且仅当它不包含任何不稳定性. 

### 2.4. 平衡结果
给定一组匹配和节点价值, 网络中其余部分为每个节点提供了最好的外部选项. 一个交换结果称为平衡的条件是, 对于匹配中的每条边来说, 价值的划分体现了这两个节点的纳什议价解结果. 

![image-20230710135620824](./Lecture%201.%20%E5%85%B3%E7%B3%BB%E7%9A%84%E5%B9%B3%E8%A1%A1%E5%92%8C%E8%AE%AE%E4%BB%B7.assets/image-20230710135620824.png)

