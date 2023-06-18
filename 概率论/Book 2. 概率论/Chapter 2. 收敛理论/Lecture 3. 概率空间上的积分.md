## 1. 数学期望
### 1.1. 数学期望的定义
如果概率空间$(X, \mathscr{F}, \mathbb{P})$上的可测函数$f$的积分存在, 则说它的数学期望存在并且把
$$
\mathbb{E} f = \int_X f\mathrm{d}\mathbb{P}
$$
叫做它的数学期望. 如果随机变量$f$是可积的, 则说它的数学期望是有限的. 

### 1.2. 数学期望的计算
设$f$是概率空间$(X, \mathscr{F}, \mathbb{P})$上的随机变量, 其分布函数为$F$, 则对任意的$(\mathbb{R}, \mathscr{B}_{\mathbb{R}})$上的可测函数$g$, $g\circ f$是$(X, \mathscr{F}, \mathbb{P})$上的可测函数, 而且只要
$$
\mathbb{E} g\circ f = \int_{\mathbb{R}}g \mathrm{d}F
$$
的一端有意义, 另一端也就有意义并且等式成立