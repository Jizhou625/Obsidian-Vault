## 3. 积分的变数替换
### 2.4. 积分的变数替换
设$g$是测度空间$(X, \mathscr{F}, \mu)$到可测空间$(Y, \mathscr{S})$的可测映射
1. 对每个$B \in \mathscr{S}$, 令$\nu(B) = \mu(g^{-1}(B))$, 则$(Y, \mathscr{S}, \nu)$还是一个测度空间
2. 对$(Y, \mathscr{S}, \nu)$上的任何可测函数$f$, 只要等式
   $$
   \int_Y f\mathrm{d}\nu = \int_X f\circ g \mathrm{d}\mu 
   $$
   的一端有意义, 就一定成立. 