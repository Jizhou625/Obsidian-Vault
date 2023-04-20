## 1. 基础判别法
### 1.1. 比较判别法
当 $n$ 充分大时, 正项级数 $\sum a_n, \sum b_n$ 的通项满足不等式
$$
\frac{a_{n+1}}{a_n} \leq \frac{b_{n+1}}{b_n}
$$
则当 $\sum b_n$ 收敛时, $\sum a_n$ 也收敛; 当 $\sum a_n$ 发散时, $\sum b_n$ 也发散

### 1.2. Cauchy根值判别法
假设对于正项级数 $\sum a_n$, 有 $\varlimsup\limits_{n \rightarrow \infty} \sqrt[n]{a_n}=c$, 则当 $c<1$ 时级数发散, 当 $c>1$ 时级数收敛

### 1.3. Cauchy 凝聚判别法
设 $\left\{a_n\right\}$ 是单调递减的正项数列, 则正项级数 $\sum\limits_{n=1}^{\infty} a_n$收敛的充分必要条件是: 凝聚项级数$\sum\limits_{n=1}^{\infty} 2^n a_{2^n}$收敛

### 1.4. Sapagof判别法
设正数数列 $\left\{a_n\right\}$ 单调减少, 则 $\lim\limits _{n \rightarrow \infty} a_n=0$ 的充分必要条件是正项级数 $\sum\limits_{n=1}^{\infty}\left(1-\dfrac{a_{n+1}}{a_n}\right)$ 发散


## 2. 基于前后项比值的判别法
### 2.1. Gauss判别法
设对于正项级数 $\sum a_n$, 有 $\dfrac{a_n}{a_{n+1}}=1+\dfrac{\mu}{n}+O\left(\dfrac{1}{n^{1+\varepsilon}}\right), \varepsilon>0$, 则当 $\mu>1$ 时, 级数收敛, 当 $\mu \leq 1$ 时, 级数发散

### 2.2. Bertrand判别法
设对于正项级数 $\sum a_n$, 有 $\lim\limits _{n \rightarrow \infty} \ln n\left[n\left(\dfrac{a_n}{a_{n+1}}-1\right)-1\right]=b$, 则当 $b>1$ 时级数收敛, 当 $b<1$ 时级数发散. 
___
**Note**: Bertrand判别法是Gauss判别法的推广, 当
$$
\dfrac{a_n}{a_{n+1}}=1+\dfrac{\mu}{n}+O\left(\dfrac{1}{n^{1+\varepsilon}}\right), \varepsilon>0 , \mu >1
$$
时, 有
$$
\lim\limits _{n \rightarrow \infty} \ln n\left[n\left(\dfrac{a_n}{a_{n+1}}-1\right)-1\right] = \infty
$$
而当
$$
\dfrac{a_n}{a_{n+1}}=1+\dfrac{\mu}{n}+O\left(\dfrac{1}{n^{1+\varepsilon}}\right), \varepsilon>0 , \mu \le 1
$$
时, 有
$$
\lim\limits _{n \rightarrow \infty} \ln n\left[n\left(\dfrac{a_n}{a_{n+1}}-1\right)-1\right] =  0
$$
因此Bertrand判别法是比Gauss判别法更强的判别法. 


### 2.3. Kummer判别法
正项级数 $\sum\limits_{n=1}^{\infty} a_n$ 收敛的充分必要条件是: 存在正项数列 $\left\{b_n\right\}$ 和正数 $\delta$, 使得当 $n$ 充分大时, 有
$$
b_n \frac{a_n}{a_{n+1}}-b_{n+1} \geq \delta>0
$$
正项级数 $\sum\limits_{n=1}^{\infty} a_n$ 发散的充分必要条件是, 存在正项数列 $q_k$ 使得 $\sum\limits_{k=1}^{\infty} \dfrac{1}{q_k}$ 发散, 使得当$n$充分大时, 有
$$
q_k \frac{a_k}{a_{k+1}}-q_{k+1} \leq 0
$$
___
**Note**: Kummer判别法是Bertrand判别法的推广, 我们有, 当
$$
\lim\limits _{n \rightarrow \infty} \ln n\left[n\left(\dfrac{a_n}{a_{n+1}}-1\right)-1\right]=1 +2\delta, \quad \delta>0
$$
时, 取$N$充分大使得当$n> N$时, 有
$$
\ln n\left[n\left(\dfrac{a_n}{a_{n+1}}-1\right)-1\right] \ge  1 + \delta
$$
又$(n+1)\ln\left(1 - \dfrac{1}{n+1}\right)< 1$. 因此我们可以得到
$$
n\ln n \cdot \dfrac{a_n}{a_{n+1}} - (n+1)\ln (n+1) \ge  \delta
$$
这对应着$b_n = n\ln n$

同样地, 当
$$
\lim\limits _{n \rightarrow \infty} \ln n\left[n\left(\dfrac{a_n}{a_{n+1}}-1\right)-1\right]=1 -2\delta, \quad \delta>0
$$
时, 取$N_0$充分大使得当$n> N_0$时, 有
$$
\ln n\left[n\left(\dfrac{a_n}{a_{n+1}}-1\right)-1\right]<1 -\delta, \quad \delta>0
$$
又可以取$N_1$充分大, 使得当$n>N_1$时, 有$(n+1)\ln\left(1 - \dfrac{1}{n+1}\right)> 1-\delta$, 因此
$$
\ln n\left[n\left(\dfrac{a_n}{a_{n+1}}-1\right)-1\right]\le 0
$$
这对应着$b_n = n\ln n$. 综上所述, 我们证明了Bertrand判别法是Kummer判别法在$b_n = n\ln n$时的特例. 

## 3. 基于分解的判别法
### 3.1. Dirichelet判别法
若 $\sum\limits_{n=1}^{\infty} a_n$ 的部分和数列有界, 数列 $\left\{b_n\right\}$ 单调收敛于 0 , 则 $\sum\limits_{n=1}^{\infty} a_n b_n$ 收敛

### 3.2. Abel判别法
若 $\sum\limits_{n=1}^{\infty} a_n$ 收敛, 数列 $\left\{b_n\right\}$ 单调有界, 则 $\sum\limits_{n=1}^{\infty} a_n b_n$ 收敛
