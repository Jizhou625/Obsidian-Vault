## 1. 基本概念
### 1.1. 反常积分
设$f(x)$在$[a,+\infty)$上有定义, 且对任意$A: a<A$, 均有$f \in R([a,A])$, 若存在极限
$$
\lim\limits_{A\to +\infty}\int_a^Af(x)\mathrm{d}x
$$ 
则称$f(x)$在$[a,+\infty)$的(反常)积分存在或收敛, 记作
$$
\int_a^{+\infty}f(x)\mathrm{d}x\overset{\Delta}{=}\lim\limits_{A\to +\infty}\int_a^Af(x)\mathrm{d}x
$$
当定义域为$(-\infty,+\infty)$时, 当且仅当右边的两个极限均存在时, 反常积分收敛
$$
\int_{-\infty}^{+\infty}f(x)\mathrm{d}x\overset{\Delta}{=}\lim\limits_{B\to -\infty}\int_B^Cf(x)\mathrm{d}x+\lim\limits_{A\to +\infty}\int_C^Af(x)\mathrm{d}x
$$

### 1.2. 瑕积分
设$f(x)$在$[a,b)$上有定义, 且对任意$\varepsilon>0,\ f\in R([a,b-\varepsilon])$, 点$x=b$是$f(x)$的瑕点, 若存在极限
$$
\lim\limits_{\varepsilon\to 0}\int_a^{b-\varepsilon}f(x)\mathrm{d}x
$$ 
则称$f(x)$在$[a,b]$上关于$b$的瑕积分收敛或存在, 记作
$$
\int_a^b f(x)\mathrm{d}x\overset{\Delta }{=}\lim\limits_{\varepsilon\to 0}\int_a^{b-\varepsilon}f(x)\mathrm{d}x
$$
如果$a<c<b$且积分
$$
\int_a^cf(x)\mathrm{d}x,\quad \int_c^bf(x)\mathrm{d}x
$$
均为瑕积分时, 当且仅当右边的两个瑕积分均存在时, 瑕积分收敛
$$
\int_a^b f(x)\mathrm{d}x\overset{\Delta }{=}\int_a^c f(x)\mathrm{d}x+\int_c^b f(x)\mathrm{d}x
$$

### 1.3. 广义积分统一定义
称$b$为函数$f(x)$在定义域区间$[a,b)$上的奇点, 如果$b=+\infty$或$f(x)$在点$b$左侧邻近无界. 假如$f(x)$在区间$[a,b)$上内闭可积, $b$为$f(x)$在$[a,b)$上的奇点, 则定义广义积分
$$
\int_a^bf(x)\mathrm{d}x=\lim\limits_{b'\to b}\int_a^{b'}f(x)\mathrm{d}x
$$
其中$f$在$I$上内闭可积的定义为: $I$为区间, 函数$f$在$I$上有定义, 如果对任意有界闭区间$[a,b]\subseteq I$, 均有$f\in R([a,b])$, 则称$f$在$I$上内闭可积.

### 1.4. 可积性总结
对不定积分,定积分和广义积分, 可积的含义是不同的. 
1. 不定积分的可积是指其原函数为初等函数族
2. 定积分的可积是指其Riemann可积, 
3. 而广义积分可积是指广义积分收敛. 
   
## 2. 广义积分敛散性判定法则
### 2.1. 有界性条件
 $f(x)$在定义域区间$[a,b)$上满足$f(x)\ge 0$, $b$为$f(x)$在$[a,b)$上的奇点, 则广义积分
$$
I=\int_a^bf(x)\mathrm{d}x
$$
收敛的充分必要条件是: 存在正数$M$, 使得对$\forall b'>a$, 均有
$$
\int_a^{b'}f(x)\mathrm{d}x\le M
$$
### 2.2. 比较判别法
设$f(x)$在区间$[a,b)$上内闭可积, $b$为$f(x)$在$[a,b)$上的奇点, 若存在$g(x), x\in [a,b)$, 使得存在极限$\lim\limits_{x\to b^-}\dfrac{f(x)}{g(x)}=l$, 记
$$
I=\int_a^bf(x)\mathrm{d}x,\quad J=\int_a^bg(x)\mathrm{d}x
$$
1. 当$l=0$时, 若$J$收敛, 则$I$收敛
2. 当$l>0$时, 广义积分$I, J$同收敛或发散
3. 当$l=+\infty$时, 若$J$发散, 则$I$发散

### 2.3. Cauchy收敛准则
设$f(x)$在区间$[a,b)$上内闭可积, $b$为$f(x)$在$[a,b)$上的奇点, 广义积分
$$
I=\int_a^bf(x)\mathrm{d}x
$$
收敛的充分必要条件是存在$x>a$, 使得对任意满足$x<x'<x''<b$的$x',x''$, 均有
$$
\left|\int_{x'}^{x''}f(x)\mathrm{d}x\right|<\varepsilon
$$

### 2.4. Dirichlet 判别法
设$f(x)$在区间$[a,b)$上内闭可积, $b$为$f(x)$在$[a,b)$上的奇点, 广义积分
$$
I = \int_a^bf(x)\mathrm{d}x
$$
收敛的充分必要条件是存在分解$f = uv$, 使得
1. 函数 $u$ 在 $[a, b)$ 上单调, 且 $\lim\limits_{x \rightarrow b^{-}} u(x)=0$
2. 对任何 $b^{\prime}>a$, 积分 $\int_a^{b^{\prime}} v(x) \mathrm{d} x$ 存在且有界

### 2.5. Abel判别法
Abel 判别法: 设 $f(x)$ 在区间 $[a, b)$ 上内闭可积, $b$ 为 $f(x)$ 在 $[a, b)$ 上的奇点, 广义积分
$$
I=\int_a^b f(x) \mathrm{d} x
$$
收敛的充分必要条件是存在分解 $f=u v$, 使得
1. 函数 $u$ 在 $[a, b)$ 上单调有界
2. 积分 $\int_a^b v(x) \mathrm{d} x$ 收敛


### 3. 几个著名的广义积分
### 3.1. Euler积分
$$
\int_0^{\frac{\pi}{2}} \ln \sin x \mathrm{~d} x=-\frac{\pi}{2} \ln 2
$$

### 3.2. Froullani积分
设函数 $f(x)$ 在 $[0, \infty)$ 上连续, 极限 $f(+\infty)$ 存在且有限, 实数 $a, b>0$, 则
$$
\int_0^{+\infty} \frac{f(a x)-f(b x)}{x} \mathrm{~d} x=[f(0)-f(+\infty)] \ln \frac{b}{a}
$$

### 3.3. Dirichlet积分
$$
\int_0^{+\infty} \frac{\sin x}{x} \mathrm{~d} x=\frac{\pi}{2}
$$

### 3.4. Euler-Possion积分
$$
\int_0^{+\infty} e^{-t^2} \mathrm{~d} t=\frac{\sqrt{\pi}}{2}
$$