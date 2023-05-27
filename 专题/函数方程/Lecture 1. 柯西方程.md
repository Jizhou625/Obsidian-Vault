## 1. 标准柯西方程
### 1.1. 加性柯西方程
设$f:\mathbb{R}\to \mathbb{R}$, 满足对任意的实数$x, y$, 均有
$$
f(x+y)  = f(x) + f(y)
$$
则如果$f(x)$满足下列三个条件之一: 
1. $f$在某一区间单调
2. $f$在某一区间有界
3. $f$在某一点处连续

我们就可以确定$f(x)$的解析式为
$$
f(x) = cx
$$
___
##### Proof
首先可以证明$f(x)$在有理数上是线性函数. 对于正整数的情形, 显然$f(n) = nf(1)$. 对于所有整数的情形, 显然有$f(0) = 0$, $f(-n) = -f(n) = -nf(1)$. 对于有理数的情形, 根据类似的方法, 我们有$f\left(\dfrac{p}{q}\right) = \dfrac{p}{q} f(1)$. 下面考虑实数的情形
1. 不妨设$f$在区间$(a, b)$上单调递增, 此时容易得到$f(1)>0$, 对于$x_0\in (a, b)$, 若$f(x_0)\neq x_0 f(1)$, 则
   - 若$f(x_0)< x_0f(1)$, 我们取有理数$q$, 使得
     $$
     f(x_0)< f(q)  = qf(1)< x_0f(1)
     $$
     这与单调性矛盾
   - 若$f(x_0)> x_0f(1)$, 我们取有理数$q$, 使得
     $$
     f(x_0) > f(q)  = qf(1)> x_0f(1)
     $$
     这与单调性矛盾
    
    因此$f(x_0) = x_0f(1)$. 对于$x_1\neq (a, b)$, 取有理数$q$, 使得$x_1+ q\in (a, b)$, 则
    $$
    f(x_1) + qf(1) = f(x_1) + f(q) = f(x_1+q) = (x_1+q)f(1)
    $$
    这就证明了$f(x_1) = x_1f(1)$
2. 不妨设$f$在区间$(a, b)$上有界$M$, 即对任意$x\in (a, b)$, 有$f(x)\le M$. 
   令$g(x) = f(x) - xf(1)$, 则对于任意的有理数$q$. 有$g(q) = 0$, 且对于任意的$x\in (a, b)$, 有
   $$
   g(x) \le M + b|f(1)|
   $$
   即$g$在$(a, b)$上有上界. 对任意的$x\in \mathbb{R}$, 取有理数$q_1$, 使得$x+q_1\in (a, b)$, 则有
   $$
   g(x) = g(x+q_1) - g(q_1) = g(x+q_1)
   $$
   因此$g$在$\mathbb{R}$上有界. 因此, $g(x)=0$. 即$f(x) = xf(1)$. 
3. 在某一点的连续性意味着在某一小区间上的有界性. 因此, 由2, 我们可以得到$f(x) = xf(1)$
#####
___

### 1.2. $f(x+y) = f(x)f(y)$
设函数$f: \mathbb{R}\to \mathbb{R}$, 满足对任意的实数$x, y$, 均有$f(x+y)= f(x)f(y)$. 则当上述三个条件中的任何一个成立时, 有
$$
f(x)\equiv 0,\quad  f(x)\equiv 1, \quad \exists a\in (0,1 )\cup (1, \infty), f(x) = a^x
$$
事实上, 取$g(x) = \ln f(x)$, 有$g(x+y) = g(x)+g(y)$是一个加性柯西方程. 

### 1.3. $f(xy) = f(x)+ f(y)$
设函数$f: \mathbb{R}^+\to \mathbb{R}$, 满足对任意的正实数$x, y$, 均有$f(xy)= f(x)+f(y)$. 则当上述三个条件中的任何一个成立时, 有
$$
f(x)\equiv 0,\quad  \exists a\in (0,1 )\cup (1, \infty), f(x) = \log_a x
$$
事实上, 取$g(x) = f(e^x)$, 有$g(x+y) = g(x)+g(y)$是一个加性柯西方程. 

### 1.4. $f(xy) = f(x)f(y)$
设函数$f: \mathbb{R}^+\to \mathbb{R}$, 满足对任意的正实数$x, y$, 均有$f(xy)= f(x)f(y)$. 则当上述三个条件中的任何一个成立时, 有
$$
f(x)\equiv 0,\quad  \exists a\in \mathbb{R}, f(x) = x^a
$$
事实上, 取$g(x) = \ln f(e^x)$, 有$g(x+y) = g(x)+g(y)$是一个加性柯西方程. 

## 2. $f(mn) = f(m)+ f(n)$限制在整数上
### 2.1. $f(n)$单调
设函数$f: \mathbb{Z}^+\to \mathbb{R}$, 满足
1. 对任意的正整数$m, n$, 均有$f(mn)= f(m)+f(n)$
2. $f(n)$单调关于$n$单调
3. $f(2)=1$

则$f(m) = \log_2m$
___
##### Proof
很容易证明$f(2^k) = k$. 对任意的正整数$m$, 设$r$是一个充分大的正整数, 并且$2^k\le m^r < 2^{k+1}$. 则根据$f$的单调性, 有
$$
k \le r f(m) < k+1
$$
因此
$$
\left|f(m) - {\log_2 m}\right| < \dfrac{1}{r}
$$
因为$r$是任意充分大的正整数, 因此有$f(m) = \log_2 m$
#####
___

### 2.2. $\lim\limits_{n\to\infty} f(n+1) - f(n) =0$
设函数$f: \mathbb{Z}^+\to \mathbb{R}$, 满足
1. 对任意的正整数$m, n$, 均有$f(mn)= f(m)+f(n)$
2. $\lim\limits_{n\to\infty} f(n+1) - f(n) =0$
3. $f(2)=1$

则$f(m) = \log_2m$
___
##### Proof
设$p$是任意的素数, 设
$$
g(n) = f(n) - \dfrac{f(p) \log_2 n}{\log_2 p}
$$
显然, $g(n)$满足$g(mn) = g(m)+ g(n)$. 并且$g(p)=0$. 另外, 设
$$
\alpha_n = g(n+1) - g(n) = f(n+1) - f(n) + \dfrac{f(p)}{\log_2 p} \log_2\dfrac{n}{n+1}
$$
我们有$\lim\limits_{n\to\infty} \alpha_n = 0$. 对任意的$n$, 使用带余除法, 可以得到
$$
n = n^{(1)} p + r_n, \quad 0\le r_n < p
$$
因此
$$
g(n) = g( n^{(1)}) + g(n) - g( n^{(1)} p) = g( n^{(1)}) + \sum\limits_{i= n^{(1)} p}^{n-1} \alpha_i 
$$
继续对$n^{(1)}$使用带余除法, 记为$n^{(2)}$, 直到$1\le n^{(k)}< p$, 显然, $k < \left\lfloor\dfrac{\log n}{\log p}\right\rfloor + 1$
$$
g(n)=g\left(n^{(k)}\right)+\sum_{j=1}^k\left(\sum_{i= n^{(i)} p}^{n^{(i-1)}-1} \alpha_i\right)
$$ 
设$\alpha_i$共有$b_n$项. 则
$$
b_n \le (p-1)\left(\dfrac{\log_2 n}{\log_2 p} + 1\right) 
$$
因为$\alpha_n\to 0$, 我们有$\dfrac{g(n)}{\log_2 n}\to 0$. 因此
$$
\lim\limits_{n\to\infty} \dfrac{f(n)}{\log_2 n} - \dfrac{f(p)}{\log_2 p} = \lim\limits_{n\to\infty}\dfrac{g(n)}{\log_2 n} = 0
$$
因为$p$是任意的, 于是对所有的$p$为素数, 都有$\dfrac{f(p)}{\log_2 p} = 1$. 有因为所有的数都可以表示为若干个素数的乘积, 因为我们有
$$
f(N) = \sum f(p_i) = \sum \log_2 p_i = \log_2 N
$$

#####
____