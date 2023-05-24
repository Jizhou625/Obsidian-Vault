## 1. $L_p$空间中的不等式
### 1.1. Young不等式
若$a, b\ge 0$, $p, q>0$且$\dfrac{1}{p} + \dfrac{1}{q}=1$, 则
$$
ab\le \dfrac{a^p}{p} + \dfrac{b^q}{q}
$$
等号成立当且仅当$a=b$
___
##### Proof: 
当$ab=0$时, 结论显然成立, 故不妨设$a, b>0$. 考虑函数$f(x)=\ln x$, 容易得到$f^{\prime\prime}(x) = -\dfrac{1}{x^2}< 0$. 于是我们有$f(x)$在$(0, +\infty)$上concave, 利用Jensen不等式, 我们有
$$
\ln \left(\frac{1}{p} a^p+\frac{1}{q} b^q\right) \geq \frac{1}{p} \ln a^p+\frac{1}{q} \ln b^q=\ln a b
$$
等号成立当且仅当$a=b$
#####
___

### 1.2. Holder不等式
为了简便起见, 定义$\|f\|_p = \left(\displaystyle{\int_X}|f|^p\mathrm{d}\mu\right)^{\frac{1}{p}}(1\le p<\infty)$. 如果$1<p, q <\infty$满足$\dfrac{1}{p}+ \dfrac{1}{q}=1$, 则对任意$f, g\in L_p$有
$$
\|fg\| \le \|f\|_p\|g\|_q
$$
等号成立的充分必要条件时存在不全为$0$的$\alpha, \beta\ge 0$使得
$$
\alpha|f|^p = \beta|g|^q \text{ a.e.}
$$
___
##### Proof:
不难看出, 如果$f=0$ a.e. 或者$g=0$ a.e., 等号显然成立. 因此可以不妨设$0< \|f\|_p, \|g\|_q<\infty$, 设
$$
a = \left(\dfrac{f}{\|f\|_p}\right)^p, \quad b = \left(\dfrac{g}{\|g\|_q}\right)^q
$$
根据[[#1.1. Young不等式]]
$$
a^{\frac{1}{p}} b^{\frac{1}{q}} \le \dfrac{a}{p} + \dfrac{b}{q}
$$ 
我们可以得到
$$
\dfrac{|fg|}{\|f\|_p\|g\|_q} \le \dfrac{1}{p} \dfrac{|p|^p}{\|f\|_p^p} + \dfrac{1}{q} \dfrac{|g|^q}{\|g\|_q^q} \text{ a.e.}
$$
两边同时取积分, 可以得到
$$
\dfrac{\|fg\|}{\|f\|_p\|g\|_q} \le 1
$$
因此, 等号成立的充分必要条件是
$$
\|g\|_q^q |f|^p = \|f\|_p^p |g|^q \text{ a.e.}
$$
#####
___
##### 离散Holder不等式
如果$x_{i, j}\ge 0$对任意$1\le i\le n, 1\le j\le m$成立, 则我们有
$$
\prod\limits_{i=1}^{n} \left(\sum\limits_{j=1}^{m} x_{i, j}\right) \ge \left(\sum\limits_{j=1}^{m} \prod\limits_{i=1}^{n} x^{\frac{1}{n}}_{i, j}\right)^n
$$
事实上, 我们采用数学归纳法, 对$n$进行归纳, 当$n=2$时显然成立, 假设当$n=k$时结论成立, 则当$n=k+1$时, 由Holder不等式, 我们有
$$
\left(\sum\limits_{j=1}^{m} \prod\limits_{i=1}^{k} \left(x_{i, j}^{\frac{1}{k+1}}\right)^{\frac{k+1}{k}}\right)^{\frac{k}{k+1}}\left(\sum\limits_{j=1}^{m} \left(x_{k+1, j}^{\frac{1}{k+1}}\right)^{k+1}\right)^{\frac{1}{k+1}} \ge \sum\limits_{j=1}^{m} \prod\limits_{i=1}^{k+1} x_{i, j}
$$
也就是说
$$
\left(\sum\limits_{j=1}^{m} \prod\limits_{i=1}^{k} x_{i, j}^{\frac{1}{k}}\right)^{\frac{k}{k+1}}\left(\sum\limits_{j=1}^{m} x_{k+1, j}\right)^{\frac{1}{k+1}} \ge \sum\limits_{j=1}^{m} \prod\limits_{i=1}^{k+1} x_{i, j}
$$
再由归纳假设
$$
\prod\limits_{i=1}^{k} \left(\sum\limits_{j=1}^{m} x_{i, j}\right) \ge \left(\sum\limits_{j=1}^{m} \prod\limits_{i=1}^{k} x^{\frac{1}{k}}_{i, j}\right)^k
$$
于是我们可以证明
$$
\prod\limits_{i=1}^{k+1} \left(\sum\limits_{j=1}^{m} x_{i, j}\right) \ge \left(\sum\limits_{j=1}^{m} \prod\limits_{i=1}^{k+1} x^{\frac{1}{k+1}}_{i, j}\right)^{k+1}
$$
因此结果也对$n=k+1$成立. 这就证明了离散Holder不等式.
___

### 1.3. Minkowski不等式($1\le p<\infty$)
设$1\le p<\infty$, 对任何$f, g\in L_p$, 有
$$
\|f+g\|_p \le \|f\|_p + \|g\|_p
$$
而且等号成立的充分必要条件是
1. 当$p=1$时, $fg\ge 0$ a.e.
2. 当$1<p<\infty$时, 存在不全为$0$的$\alpha, \beta\ge 0$使得$\alpha f = \beta g$ a.e.

___
##### Proof:
当$p=1$时, 对任意的$a, b\in\mathbb{R}$时, 有
$$
|a+b| \le |a| + |b|
$$
其中等号成立当且仅当$ab\ge 0$, 也就是说$fg\ge 0$ a.e. 以下设$1<p<\infty$, 令$q = \dfrac{p}{p-1}$, 因此我们有
$$
\begin{aligned} 
\|f+g\|_p^p &= \int_X |f+g|^p \mathrm{d}\mu \\ 
& \le \int_X |f| |f+g|^{p-1} \mathrm{d}\mu + \int_X |g| |f+g|^{p-1} \mathrm{d}\mu \\
& \le \|f\|_p \||f+g|^{p-1}\|_{q} + \|g\|_p \||f+g|^{p-1}\|_{q}\\
& = (\|f\|_p + \|g\|_p) \|f+g\|_{p}^{p-1}
\end{aligned}
$$
当$\|f+g\|_p = 0$时, 结论显然成立, 否则我们可以除以$\|f+g\|_p^{p-1}$, 于是我们有
$$
\|f+g\|_p \le \|f\|_p + \|g\|_p
$$
容易验证等号成立的充分必要条件. 
#####
___

### 1.4. Minkowski不等式($0 < p < 1$)
为简便起见, 定义$\|f\|_p=\displaystyle{\int_X}|f|^p\mathrm{d}\mu (0<p<1)$, 则我们有当$0<p<1$时, 有
$$
\|f+g\|_p \le \|f\|_p + \|g\|_p
$$
___
##### Proof:
当$0<p<1$时, 不难证明对任意的$a, b\in\mathbb{R}$, 有
$$
|a+b|^p \le |a|^p + |b|^p
$$
于是我们有
$$
|f+g|^p \le |f|^p + |g|^p \text{ a.e.}
$$
因此有
$$
\|f+g\|_p \le \|f\|_p + \|g\|_p
$$
#####
___


## 2. 对数相关的不等式
### 2.1. 对数和不等式
对于非负数$a_1, a_2, \cdots, a_n$和$b_1, b_2, \cdots, b_n$. 则有
$$
\sum\limits_{i=1}^{n} a_i \log \dfrac{a_i}{b_i} \ge \left(\sum\limits_{i=1}^{n} a_i\right) \log \dfrac{\sum\limits_{i=1}^{n} a_i}{\sum\limits_{i=1}^{n} b_i}
$$
当且仅当$\dfrac{a_i}{b_i} = c$是个常数时, 等号成立. 
___
##### Proof
考虑函数$f(t) = t\log t$, 则$f''(t) = \dfrac{1}{t} > 0$, 因此$f(t)$是严格凸函数. 于是根据Jensen不等式, 我们有
$$
\sum\limits_{i=1}^{n} \alpha_i f(t_i) \ge f\left(\sum\limits_{i=1}^{n} \alpha_i t_i\right)
$$
其中$\alpha_i\ge 0$, $\sum\limits_{i=1}^{n} \alpha_i = 1$, $t_i\ge 0$. 令$\alpha_i = \dfrac{b_i}{\sum\limits_{j=1}^{n} b_j}$, $t_i = \dfrac{a_i}{b_i}$, 则有
$$
\sum\limits_{i=1}^{n} \dfrac{b_i}{\sum\limits_{j=1}^{n} b_j} \left(\dfrac{a_i}{b_i}\log \dfrac{a_i}{b_i}\right) \ge \left(\sum\limits_{i=1}^{n} \dfrac{b_i}{\sum\limits_{j=1}^{n} b_j} \dfrac{b_i}{a_i}\right) \log \left(\sum\limits_{i=1}^{n} \dfrac{b_i}{\sum\limits_{j=1}^{n} b_j} \dfrac{b_i}{a_i}\right)
$$
于是我们有
$$
\sum\limits_{i=1}^{n} a_i \log \dfrac{a_i}{b_i} \ge \left(\sum\limits_{i=1}^{n} a_i\right) \log \dfrac{\sum\limits_{i=1}^{n} a_i}{\sum\limits_{i=1}^{n} b_i}
$$
等号成立当且仅当$\dfrac{a_i}{b_i} = c$是个常数
##### 
___