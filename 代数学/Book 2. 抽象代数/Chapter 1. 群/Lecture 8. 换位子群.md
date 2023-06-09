## 1. 换位子群
### 1.1. 换位子
设$G$为群, $a, b\in G$, 定义$[a, b]= aba^{-1}b^{-1}$, 并称之为$a$和$b$的换位子(commutator). 显然$a$与$b$可交换当且仅当$[a, b]=e$

### 1.2. 换位子群
群$G$的所有换位子生成的子群称为$G$的换位子群, 或者导群, 记为$[G, G]$或者$G^{\prime}$. 即
$$
G^{\prime} = \langle aba^{-1}b^{-1}\mid a, b\in G \rangle
$$
显然, $G$为交换群当且仅当$G^{\prime} = \{e\}$, 因此, 从某种意义上来将, $G^{\prime}$是$G$的非交换性的一种度量. 

不难得到, $G^{\prime}\trianglelefteq G$. 


### 1.3. 可交换性的判定
设 $N \trianglelefteq G$, 则 $G / N$ 是交换群当且仅当 $G^{\prime} \subseteq N$. 特别地, $G / G^{\prime}$可交换.


### 1.4. $n$阶导群
递归地定义群 $G$ 的 $n$ 级导群 $G^{(n)}$ 如下: $G^{(1)}=G^{\prime}$, 对 $n>1$, $G^{(n)}=\left(G^{(n-1)}\right)^{\prime}$


## 2. 可解群
### 2.1. 可解群的定义
设 $G$ 为群, 如果存在某个正整数 $n$ 使得 $G^{(n)}=\{e\}$, 则称 $G$ 为可解群.

### 2.2. 可解群的判定
设 $G$ 为群, 则 $G$ 是可解群的充分必要条件是存在 $G$ 的子群列 $G=G_0 \unrhd G_1 \unrhd \cdots \unrhd G_s=\{e\}$, 使得对任意 $0 \leq i \leq s-1, G_i / G_{i+1}$ 都是交换群. (满足如上性质的 $G$ 的子群列称为 $G$ 的一个可解群列)

### 2.3. 可解群的封闭性
1. **对子群, 商群封闭**: 可解群的子群和商群仍为可解群. 若 $H \leq G, N \unlhd G$, $n \geq 1$, 则 
   $$
   H^{(n)} \leq G^{(n)},\quad (G / N)^{(n)}=G^{(n)} N / N
   $$  
2. **对(正规子群)直积封闭**: 设 $N \unlhd G$, 若 $N$ 和 $G / N$ 均可解, 则 $G$ 可解.