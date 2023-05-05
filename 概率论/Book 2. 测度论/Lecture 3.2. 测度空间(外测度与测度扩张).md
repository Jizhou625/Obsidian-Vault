## 1. 外测度
### 1.1. 外测度的定义
由$X$的所有子集组成的集合系$\mathscr{T}$到$\overline{\mathbb{R}}$的函数$\tau$称为$X$上的外测度, 如果它满足

1. **空集测度为$\boldsymbol{0}$**: $\tau(\varnothing) = 0$
2. **单调性**: 对任何$A\subset B \subset X$有$\tau(A)\le \tau(B)$
3. **半可列可加性**: 对任何$\{A_n\in \mathscr{T}\}$有$\tau\left(\bigcup\limits_{n=1}^{\infty} A_n\right) \le \sum\limits_{n=1}^{\infty} \tau(A_n)$

### 1.2. 生成外测度
设$\mathscr{E}$是一个集合系且$\varnothing\in \mathscr{E}$, 如果$\mathscr{E}$上的非负集函数$\mu$满足$\mu(\varnothing)=0$. 对每个$A\in \mathscr{T}$, 设
$$
\tau(A) = \inf\left\{\sum\limits_{n=1}^{\infty} \mu(B_n)\mid B_n\in \mathscr{E}, \bigcup\limits_{n=1}^{\infty} B_n\supset A\right\}
$$
则$\tau$是一个外测度, 称为由$\mu$生成的外测度. 其中, 空集的下确界定义为$\infty$
___
##### Proof: 
不难验证, 生成的外测度$\tau$满足条件1和2. 下面证明其满足条件3. 我们只需要证明$\tau(A_n)<\infty$的情况. 取$\{B_{n,k}\in \mathscr{E}\}$使得$\bigcup\limits_{k=1}^{\infty} B_{n, k}\supset A_n$且
$$
\sum\limits_{k=1}^{\infty} \mu(B_{n, k}) < \tau(A_n)+ \dfrac{\varepsilon}{2^n}
$$
便有$\bigcup\limits_{n=1}^{\infty} \bigcup\limits_{k=1}^{\infty} B_{n, k}\supset \bigcup\limits_{n=1}^{\infty} A_n$, 从而
$$
\tau\left(\bigcup\limits_{n=1}^{\infty} A_n \right) \le \sum\limits_{n=1}^{\infty} \sum\limits_{k=1}^{\infty} \mu(B_{n,k})\le \sum\limits_{n=1}^{\infty} \tau(A_n) +\varepsilon
$$
由$\varepsilon$的任意性即得证
#####
___
### 1.3. $\tau$可测集和完全测度空间
**$\tau$可测集**: 设$\tau$是$X$上的外测度, $\mathscr{T}$是由$X$的所有子集组成的集合系, 我们把满足
$$
\tau(D) = \tau(D\cap A) + \tau(D\cap A^c), \quad \forall D\in \mathscr{T}
$$
的$X$的子集$A$称为$\tau$可测集, 把由全体$\tau$可测集组成的集合系记为$\mathscr{F}_{\tau}$. 

**完全测度空间**: 对于测度空间$(X, \mathscr{F}, \mu)$, 如果$\mu$的任意零测集合的子集还属于$\mathscr{F}$, 即
$$
A\in \mathscr{F}, \mu(A) = 0 \Longrightarrow B\subset \mathscr{F}, \forall B\subset A
$$
则称$(X, \mathscr{F}, \mu)$是完全测度空间. 

### 1.4. Caratheodory定理
如果$\tau$是外测度, $\mathscr{F}_{\tau}$是由全体$\tau$可测集组成的集合系, 则$\mathscr{F}_{\tau}$是一个$\sigma$代数, 且$(X, \mathscr{F}_{\tau}, \tau)$是完全测度空间. 
___
##### Proof: 
我们首先证明$\mathscr{F}_{\tau}$是一个$\sigma$-代数. 分为以下几个部分

1. $\mathscr{F}$是个域
   - $X \in \mathscr{F}_{\tau}$, 这是因为$\tau(D\cap X) +\tau(D\cap \varnothing) = \tau(D) +\tau(\varnothing) = \tau(D)$
   - 若$A\in \mathscr{F}_{\tau}$, 则$A^c\in \mathscr{F}_{\tau}$. 这是因为$\tau$可测集的定义关于$A$和$A^c$是对称的. 
   - 若$A_1, A_2\in \mathscr{F}_{\tau}$, 则有$A_1\cap A_2\in \mathscr{F}_{\tau}$. 这是因为   
     $$
     \begin{aligned}       
     \tau(D) &= \tau(D\cap A_1) + \tau(D\cap A_1^c) \\       
     & = \tau(D\cap A_1 \cap A_2) + \tau(D \cap A_1 \cap A_2^c) + \tau(D\cap A_1^c)\\       
     & = \tau(D\cap A_1 \cap A_2) + \tau(D \cap (A_1\cap A_2)^c \cap A_1) + \tau(D\cap (A_1\cap A_2)^c\cap A_1^c)\\       
     & = \tau(D\cap A_1 \cap A_2) + \tau(D\cap (A_1\cap A_2)^c)   
     \end{aligned}   
     $$
4. $\mathscr{F}$是个$\sigma$域
   - 如果$\{B_i\}$两两不交, 则对每个$D\in \mathscr{T}$, 有
     $$
     \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)\right) = \sum\limits_{i=1}^{n} \tau(D\cap B_i)
     $$
     这是因为对任意的$D\in \mathscr{T}$, 有
     $$
     \begin{aligned} 
         \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)\right) &= \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)\cap B_1\right) + \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)\cap B_1^c\right)\\ 
         & = \tau(D\cap B_1) + \tau\left(D\cap \left(\bigcup\limits_{i=2}^{n} B_i\right)\right)\\
         & = \sum\limits_{i=1}^n \tau(D\cap B_i)
     \end{aligned}
     $$
   - 如果$\{B_n\in \mathscr{F}_{\tau}\}$两两不交, 则对每个$D\in \mathscr{T}$. 
     $$
     \tau(D)\ge \sum\limits_{n=1}^{\infty} \tau(D\cap B_n) + \tau\left[D\cap \left(\bigcup\limits_{n=1}^{\infty} B_n\right)^c\right]
     $$
     这是因为
     $$
     \begin{aligned} 
         \tau(D) &= \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)\right) + \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)^c\right) \\ 
         & = \sum\limits_{i=1}^{n} \tau(D\cap B_i) + \tau\left(D\cap \left(\bigcup\limits_{i=1}^{n} B_i\right)^c\right)\\
         & \ge \sum\limits_{i=1}^{n} \tau(D\cap B_i) + \tau\left(D\cap \left(\bigcup\limits_{i=1}^{\infty} B_i\right)^c\right)
     \end{aligned}
     $$
     取$n\to\infty$即可得到结论成立. 
   - $\mathscr{F}_{\tau}$是一个$\sigma$域. 我们之前已经证明了$\mathscr{F}_{\tau}$是一个域, 下面只需要证明
     $$
     A_n\in \mathscr{F}_{\tau} \Longrightarrow \bigcup\limits_{n=1}^{\infty} A_n\in \mathscr{F}_{\tau}
     $$
     对每个$n=1,2,\cdots$, 令$B_n=A_n\backslash \bigcup\limits_{i=1}^{n-1} A_i$, 则$\{B_n\in \mathscr{F}_{\tau}\}$两两不交并且满足
     $$
       \bigcup\limits_{n=1}^{\infty} A_n = \bigcup\limits_{n=1}^{\infty} B_n
     $$
     因此对任意的$D\in \mathscr{T}$, 有
     $$
     \begin{aligned} 
         \tau(D) &\ge \sum\limits_{n=1}^{\infty} \tau(D\cap B_n) + \tau\left[D\cap \left(\bigcup\limits_{n=1}^{\infty} B_n\right)^c\right] \\ 
         & \ge  \tau\left(D\cap \left(\bigcup\limits_{n=1}^{\infty} B_n\right)\right) + \tau\left[D\cap \left(\bigcup\limits_{n=1}^{\infty} B_n\right)^c\right] \\ 
         & = \tau\left(D\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)\right) + \tau\left[D\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)^c\right] \\ 
     \end{aligned}
     $$
     但是, 根据$\tau$的半可列可加性我们有
     $$
     \tau(D) \le \tau\left(D\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)\right) + \tau\left[D\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)^c\right]
     $$
     于是我们证明了
     $$
     \tau(D) = \tau\left(D\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)\right) + \tau\left[D\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)^c\right]
     $$
     因此$\bigcup\limits_{n=1}^{\infty} A_n\in \mathscr{F}_{\tau}$. 这就证明了$\mathscr{F}_{\tau}$是一个$\sigma$域.
3. $\tau$限制在$\mathscr{F}_{\tau}$上是测度. 这是因为$\{B_n\in \mathscr{F}_{\tau}\}$两两不交. 取$D = \bigcup\limits_{n=1}^{\infty} B_n$, 我们可以得到
   $$
   \tau\left(\bigcup\limits_{n=1}^{\infty} B_n\right) \ge \sum\limits_{n=1}^{\infty} \tau(B_n)
   $$
   再由$\tau$的半可列可加性, 可以得到$\tau$的可列可加性. 这表明$\tau$是一个测度
4. $(X, \mathscr{F}_{\tau}, \tau)$是完全测度空间. 这是因为对任意的$A\in \mathscr{T}$, 当$\tau(A)=0$时, $\forall D\in \mathscr{T}$, 我们有$\tau(D\cap A) = 0$, 因此
   $$
   \tau(D)  \ge \tau(D\cap A^c)  = \tau(D\cap A) + \tau(D\cap A^c)
   $$
   再根据$\tau$的半可列可加性, 我们得到了
   $$
   \tau(D) = \tau(D\cap A) + \tau(D\cap A^c)
   $$
   这就表明了$A\in \mathscr{\mathscr{F}_{\tau}}$. 因此所有的零测集都属于$\mathscr{F}_{\tau}$. 这就证明了$(X, \mathscr{F}_{\tau}, \tau)$是完全测度空间.
#####
___

## 2. 测度的扩张
### 2.1. 扩张的定义
设$\mu$和$\tau$分别为集合系$\mathscr{E}$和集合系$\overline{\mathscr{E}}$上的测度, 而且$\mathscr{E}\subset \overline{\mathscr{E}}$. 如果对每个$A\subset \mathscr{E}$都有
$$
\tau(A) = \mu(A)
$$
则称$\tau$为$\mu$在$\overline{\mathscr{E}}$上的扩张. 
___
##### 利用外测度的扩张
如果在集合系$\mathscr{E}$上有测度$\mu$, 就可以利用[[#3.2. 生成外测度]]在$X$上生成一个外测度$\tau$. 而根据[[#3.4. Caratheodory定理]], 把这个外测度限制在$\sigma$域$\mathscr{F}_{\tau}$上就得到了一个测度. 

但是, $\mathscr{F}_{\tau}$未必比$\mathscr{E}$更大, 例如下面的例子: 

设$X = \{a, b, c\}$, $\mathscr{E}=\{\varnothing, \{a, b\}, \{b, c\}, X\}$ 和
$$
\mu(\varnothing) = 0, \quad \mu(\{a, b\}) = \mu(\{b, c\}) = 1, \quad \mu(X) = 2
$$
显然$\mu$是$\mathscr{E}$上的测度. 根据生成外测度的算法, 我们有
$$
\tau(\varnothing) = 0, \quad \tau(X) = \tau(\{a, c\}) = 2, \tau(\{a\}) = \tau(\{b\}) = \tau(\{c\}) = \tau(\{a, b\}) = \tau(\{b, c\}) = 1
$$
再根据$\tau$可测集的性质可以得到$\mathscr{F}_{\tau}=\{\varnothing, X\}$. 

这意味着如果想要利用外测度对测度进行扩张, 必须对集合系$\mathscr{E}$做出一定的限制.
#####
___

### 2.2. 测度扩张定理
对于半环$\mathscr{Q}$上的测度$\mu$, 存在$\sigma(\mathscr{Q})$上的测度$\tau$使得对每个$A\in \mathscr{Q}$有
$$
\tau(A) = \mu(A)
$$
如果存在两两不交的$\{A_n\in \mathscr{Q}\}$使得$\bigcup\limits_{n=1}^{\infty} A_n = X$且$\mu(A_n)<\infty$, 则使得$\tau(A) = \mu(A)$的$\tau$唯一. 
___
##### Proof: 
设$\tau$为$\mu$通过[[#3.2. 生成外测度]]产生的外测度. 我们按照下面的顺序来进行证明
1. 首先证明对每个$A\in \mathscr{Q}$, 有$\tau(A) = \mu(A)$. 设$A\in \mathscr{Q}$, 对任何满足$\bigcup\limits_{n=1}^{\infty} A_n \supset A$的$\{A_n\in \mathscr{Q}\}$, 均有
   $$
   \mu(A) = \mu\left(\bigcup\limits_{n=1}^{\infty} (A\cap A_n)\right) \le \sum\limits_{n=1}^{\infty} \mu(A\cap A_n) \le \sum\limits_{n=1}^{\infty} \mu(A_n)
   $$
   根据生成外测度的定义
   $$
   \tau(A) = \inf\left\{\sum\limits_{n=1}^{\infty} \mu(A_n)\ \Big|\ A_n\in \mathscr{Q}, \bigcup\limits_{n=1}^{\infty} A_n\supset A\right\}
   $$
   因此
   $$
   \mu(A) = \tau(A)
   $$
2. 对任意的$A, D\in \mathscr{Q}$, 有
   $$
   \tau(D)\ge \tau(D\cap A) + \tau(D\cap A^c)
   $$
   这是因为$D\cap A^c = D\backslash A = \bigcup\limits_{i=1}^{n} B_i$, 其中$\{B_i\in \mathscr{Q}\}$两两不交. 则
   $$
   \begin{aligned} 
      \tau(D) & = \mu(D) \\ 
      & = \mu(D\cap A) + \mu(D\cap A^c) \\ 
      & = \mu(D\cap A) + \sum\limits_{i=1}^{n} \mu(B_i) \\ 
      & \ge \mu(D\cap A) + \tau(D\cap A^c) \\
      & \ge \tau(D\cap A) + \tau(D\cap A^c) 
   \end{aligned}
   $$
3. $\mathscr{Q}\subset \mathscr{F}_{\tau}$. 即对任意$A\in \mathscr{Q}$和$D\in \mathscr{T}$, 有
   $$
   \tau(D) = \tau(D\cap A) + \tau(D\cap A^c)
   $$
   这是因为当$\tau(D) = \infty$时, 显然成立. 当$\tau(D)<\infty$时, 对任意给定的$\varepsilon>0$, 取$\{B_n\in \mathscr{Q}\}$使得$\bigcup\limits_{n=1}^{\infty} B_n\supset D$. 
   $$
   \begin{aligned} 
   \tau(D) + \varepsilon &\ge \sum\limits_{n=1}^{\infty} \mu(B_n) = \sum\limits_{n=1}^{\infty} \tau(B_n) \\ 
   &\ge \sum\limits_{n=1}^{\infty} \left[\tau(B_n\cap A) + \tau(B_n\cap A^c)\right] \\ 
   & \ge  \tau\left(\bigcup\limits_{n=1}^{\infty} B_n\cap A\right)+  \tau\left(\bigcup\limits_{n=1}^{\infty} B_n\cap A^c\right) \\ 
   &\ge \tau(D\cap A) + \tau(D\cap A^c)
   \end{aligned}
   $$
   令$\varepsilon\to 0$, 即可得到
   $$
   \tau(D) \ge \tau(D\cap A) + \tau(D\cap A^c)
   $$
   再根据$\tau$的半可列可加性可以得到
   $$
   \tau(D) = \tau(D\cap A) + \tau(D\cap A^c)
   $$
4. $\tau$是$\sigma(\mathscr{Q})$上的测度. 这是因为$\mathscr{F}_{\tau}$是$\sigma$域, 故$\mathscr{Q}\subset \mathscr{F}_{\tau}\Longrightarrow \sigma(\mathscr{Q})\subset\mathscr{F}_{\tau}$. 但$\tau$限制在$\mathscr{F}_{\tau}$上是测度, 因此$\tau$是$\sigma(\mathscr{Q})$上的测度. 
5. 如果存在两两不交的$\{A_n\in \mathscr{Q}\}$使得$\bigcup\limits_{n=1}^{\infty} A_n = X$且$\mu(A_n)<\infty$, 则使得$\tau(A) = \mu(A)$的$\tau$唯一. 这是我们有因为下面的引理成立(半环也是一个$\pi$系)
___
**引理**: 设$\mathscr{P}$是一个$\pi$系, 如果$\sigma(\mathscr{P})$上的测度$\mu, \nu$满足
1. 对每个$A\in \mathscr{P}$, 有$\mu(A) = \nu(A)$
2. 存在两两不交的$\{A_n\in \mathscr{P}\}$使得$\bigcup\limits_{n=1}^{\infty} A_n=X$且$\mu(A_n)<\infty$对每个$n=1,2,\cdots$成立
   
则对任何$A\in \sigma(\mathscr{P})$有
$$
\mu(A) = \nu(A)
$$
___
**Proof**: 设
$$
\mathscr{S} = \{A\in \sigma(\mathscr{P})\mid \mu(A\cap B) = \nu(A\cap B), \forall B\in \mathscr{P}, \mu(B)<\infty\}
$$
根据$\pi$系的性质, 显然有$\mathscr{P}\subset \mathscr{S}$. 下面证明$\mathscr{S}$是一个$\lambda$系, 这是因为
1. $X\in \mathscr{S}$
2. 对于$A_1, A_2\in \mathscr{S}$且$A_1\supset A_2$, 根据可列可加性, 我们有
   $$
   \mu(A_1\cap B) = \mu(A_2\cap B) + \mu((A_1\backslash A_2)\cap B)
   $$
   $$
   \nu(A_1\cap B) = \nu(A_2\cap B) + \nu((A_1\backslash A_2)\cap B) 
   $$
   这样, 我们有
   $$
   \mu((A_1\backslash A_2)\cap B) = \nu((A_1\backslash A_2)\cap B) 
   $$
   这表明$A_1\backslash A_2\in \mathscr{S}$
3. 对于$A_n \in \mathscr{L}$ 且 $A_n \uparrow$, 根据条件2我们有
   $$
   \begin{aligned} 
   \mu\left(\left(\bigcup\limits_{n=1}^{\infty} A_n\right)\cap B\right) &= \mu\left(\left(\bigcup\limits_{n=1}^{\infty} (A_n\backslash A_{n-1})\right)\cap B\right) \\ 
   & = \sum\limits_{n=1}^{\infty} \mu\left((A_n\backslash A_{n-1})\cap B\right) \\
   & = \sum\limits_{n=1}^{\infty}\nu\left((A_n\backslash A_{n-1})\cap B\right) \\
   & = \nu\left(\left(\bigcup\limits_{n=1}^{\infty} (A_n\backslash A_{n-1})\right)\cap B\right) \\ 
   & =  \nu\left(\left(\bigcup\limits_{n=1}^{\infty} A_n\right)\cap B\right)
   \end{aligned}
   $$

因为$\mathscr{L}$是$\lambda$系且$\mathscr{L}\supset \mathscr{P}$, [[Lecture 1. 可测空间#4.4 $ pi$系的生成$ lambda$系是$ sigma$域]], 这说明 $\mathscr{L}\supset \sigma(\mathscr{P})$.  即对每个$A\in \sigma(\mathscr{P})$和满足$\mu(B)<\infty$的$B\in \mathscr{P}$有
$$
\mu(A\cap B) = \nu(A\cap B)
$$
于是, 取$\{A_n\in\mathscr{P}\}$使得$\bigcup\limits_{n=1}^{\infty} A_n = X$, 对任意的$A\in \sigma(\mathscr{P})$有
$$
\begin{aligned} 
\mu(A) &= \mu\left(A\cap\left(\bigcup\limits_{n=1}^{\infty} A_n\right)\right) \\ 
    & = \sum\limits_{n=1}^{\infty} \mu(A\cap A_n) \\
    & = \sum\limits_{n=1}^{\infty} \nu(A\cap A_n) \\ 
    & = \nu\left(A\cap \left(\bigcup\limits_{n=1}^{\infty} A_n\right)\right) \\
    & = \nu(A)
\end{aligned}
$$
#####
___

### 2.3. $\sigma(\mathscr{Q})$上的测度$\tau$和$\mathscr{F}_{\tau}$上的测度$\tau$的关系
设$\tau$是半环$\mathscr{Q}$上测度$\mu$生成的外测度
1. 对每个$A\in \mathscr{F}_{\tau}$, 存在$B\in \sigma(\mathscr{Q})$使得$B\supset A$且$\tau(A) = \tau(B)$
2. 如果存在两两不交的$\{A_n\in \mathscr{Q}\}$使得$\bigcup\limits_{n=1}^{\infty} A_n = X$且$\mu(A_n)<\infty$, 则对每个$A\in \mathscr{F}_{\tau}$存在$B\in \sigma(\mathscr{Q})$使得$B\supset A$且$\tau(B\backslash A) = 0$

___
##### Proof: 
1. 当$\tau(A)=\infty$时, 只要取$B=X$即可. 下设$\tau(A)<\infty$. 对每个$n=1,2,\cdots$, 取$\{B_{n, k}\in\mathscr{Q}\mid k=1,2,\cdots\}$使得$\bigcup\limits_{k=1}^{\infty} B_{n, k}\supset A$并且
   $$
   \sum\limits_{k=1}^{\infty} \mu(B_{n, k}) < \tau(A) + \frac{1}{n} 
   $$
   设$B = \bigcap\limits_{n=1}^{\infty} \bigcup\limits_{k=1}^{\infty} B_{n, k}$, 则$B\in \sigma(\mathscr{Q})$且
   $$
   B\supset A\Longrightarrow \tau(B)\geq \tau(A)
   $$
   此外, 我们还有对任意的$n>0$, 都有
   $$
   \tau(B)\le \tau(A) + \dfrac{1}{n}
   $$
   因此, 取$n\to\infty$, 我们可以得到
   $$
   \tau(B) = \tau(A)
   $$
2. 对于任意给定的$A\in \mathscr{F}_{\tau}$, 根据1可以得到存在$B_n\in \mathscr{\sigma}(\mathscr{Q})$使得$B_n\supset A\cap A_n$且
   $$
   \tau(B_n) = \tau(A\cap A_n)<\infty \Longrightarrow \tau(B_n\backslash (A\cap A_n)) = 0
   $$
   设$B = \bigcup\limits_{n=1}^{\infty} B_n$, 则根据$\{B_n\}$的取法, 我们知道$B \supset A$且$B\in \sigma(\mathscr{Q})$. 这样
   $$
   \tau(B\backslash A) = \tau\left(\bigcup\limits_{n=1}^{\infty} B_n\backslash (A\cap A_n)\right) \le \sum\limits_{n=1}^{\infty} \tau(B_n\backslash (A\cap A_n)) = 0
   $$
#####
___

### 2.4. 域$\mathscr{A}$上的测度对$\sigma(\mathscr{A})$上测度的逼近
设$\mathscr{A}$是一个域, $\mu$是$\sigma(\mathscr{A})$上的测度且在$\mathscr{A}$上$\sigma$有限. 如果$A\in \sigma(\mathscr{A})$且$\mu(A)<\infty$, 则对任意的$\varepsilon>0$,  存在$B\in \mathscr{A}$使得$\mu(A\Delta B)<\varepsilon$
___
##### Proof: 
设$\tau$是$\mathscr{A}$上测度$\mu$产生的外测度, 根据$\mu$在$\mathscr{A}$上$\sigma$有限, 可以得到对于每个$C\in\sigma(\mathscr{A})$, 都有$\tau(C) = \mu(C)$. 于是我们只要证明, 对于任意的$\varepsilon>0$, 存在$B\in \mathscr{A}$, 使得
$$
\tau(A\Delta B)<\varepsilon
$$
我们有以下的引理成立.

___
**引理**: 设$\mu$是域$\mathscr{A}$上的测度, $\tau$为$\mu$生成的外测度. 如果$A\in\sigma(\mathscr{A})$且$\tau(A)<\infty$, 则对于任意给定的$\varepsilon>0$, 存在$B\in \mathscr{A}$使得$\tau(A\Delta B)<\varepsilon$
___

对于任意给定的$\varepsilon>0$, 取$\{B_n\in \mathscr{A}\}$, 使得$\bigcup\limits_{n=1}^{\infty} B_n\supset A$且
$$
\sum\limits_{n=1}^{\infty} \mu(B_n) < \tau(A) + \dfrac{\varepsilon}{2}
$$
易见
1. 对任何正整数$N$有
   $$
   \begin{aligned}
   \tau\left(\bigcup\limits_{n=1}^{N} B_n \backslash A\right) &\le \tau\left(\bigcup\limits_{n=1}^{\infty} B_n\backslash A\right) \\
   & = \tau\left(\bigcup\limits_{n=1}^{\infty} B_n\right) - \tau(A) \\ 
   & \le \sum\limits_{n=1}^{\infty} \mu(B_n) - \tau(A) \\
   & < \dfrac{\varepsilon}{2}
   \end{aligned}
   $$
2. 存在充分大的$N$使得$\sum\limits_{n=N+1}^{\infty} \mu(B_n)<\dfrac{\varepsilon}{2}$, 从而   
   $$
   \begin{aligned} 
      \tau\left(A\backslash \left(\bigcup\limits_{n=1}^{N} B_n\right)\right) &\le  \tau\left(\left(\bigcup\limits_{n=1}^{\infty} B_n\right)\backslash \left(\bigcup\limits_{n=1}^{N} B_n\right)\right) \\ 
      & \le \tau\left(\bigcup\limits_{n=1}^{\infty} B_n\right) - \tau\left(\bigcup\limits_{i=1}^{N} B_n\right) \\ 
      & \le \tau\left(\bigcup\limits_{n=N+1}^{\infty} B_n\right) \\ 
      & \le \sum\limits_{n=N+1}^{\infty} \mu(B_n) \\
      & < \dfrac{\varepsilon}{2}
   \end{aligned}
   $$

设$B = \bigcup\limits_{n=1}^{N} B_n$, 则$B\in \mathscr{A}$, 根据上面的1和2可以得到
$$
\tau(A\Delta B) \le \tau(A\backslash B) + \tau(B\backslash A) \le  \varepsilon
$$
#####
___

