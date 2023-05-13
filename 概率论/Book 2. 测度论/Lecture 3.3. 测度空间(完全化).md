## 1. L-S测度
### 1.1. L-S测度
$\mathbb{R}$上非降右连续实值函数$F$在半环$\mathscr{Q}_{\mathbb{R}}$上定义了一个有限测度$\mu$
$$
\mu((a, b]) = \begin{cases}  F(b) - F(a) , \quad & a<b \\ 0, \quad & a\ge b \end{cases}
$$
$\mu$的外测度$\lambda_F$在由它的全体可测集$\lambda_F$组成的$\sigma$域$\mathscr{F}_{\lambda_F}$上也是一个测度. 我们把$\mathscr{F}_{\lambda_F}$中的集合叫做L-S可测集, 并把$(\mathbb{R}, \mathscr{F}_{\lambda_F})$上的可测函数叫做L-S可测函数. 把$\mathscr{F}_{\lambda_F}$上的测度$\lambda_F$叫做$\mathbb{R}$上的L-S测度.

### 1.2. L测度
特别地, 当$F(x)= x, \forall x\in \mathbb{R}$时, $\mathscr{F}_{\lambda_F}$中的集合叫做$\mathbb{R}$上的L可测集. $(\mathbb{R}, \mathscr{F}_{\lambda_F})$上的可测函数叫做L可测函数, $\mathscr{F}_{\lambda_F}$上的测度$\lambda_F$叫做$\mathbb{R}$上的L测度.

## 2. 测度空间的完全化
### 2.1. 每个测度空间都可以被完全化
对任意测度空间$(X, \mathscr{F}, \mu)$
$$
\widetilde{\mathscr{F}} = \{A\cup N\mid A\in \mathscr{F}; \exists B\in \mathscr{F}\supset N\ \mathrm{s.t.}\ \mu(B) =0\}
$$
是一个$\sigma$域, 如果对于每个$A\cup N\in \widetilde{\mathscr{F}}$, 令
$$
\widetilde{\mu}(A\cup N) = \mu(A)
$$
则$(X, \widetilde{\mathscr{F}}, \widetilde{\mu})$是一个完全测度空间并且对每个$A\in\mathscr{F}$有
$$
\widetilde{\mu}(A) = \mu(A)
$$
___
##### Proof:
我们的证明按照以下的步骤进行
1. $\widetilde{\mathscr{F}}$是$\sigma$域. 
   这是因为, 如果$A\cup N\in \widetilde{\mathscr{F}}$, 则$B^c\cap A^c\in \mathscr{F}$且$B\cap A^c\cap N^c\subset B$, 从而
   $$
   \begin{aligned} 
   (A\cup N)^c &= (B^c\cap (A\cup N)^c) \cup (B\cap (A\cup N)^c) \\ 
   & = (B^c\cap A^c) \cup (B\cap A^c\cap N^c) 
   \end{aligned}
   $$
   由定义可以得到$(A\cup N)^c\in \widetilde{\mathscr{F}}$. 如果对每个$n=1,2,\cdots$有$A_n\cup N_n\in \widetilde{\mathscr{F}}$, 则由
   $$
   A= \bigcup\limits_{n=1}^{\infty} A_n\in \mathscr{F}, \quad \mu\left(\bigcup\limits_{n=1}^{\infty} B_n\right) \le \sum\limits_{n=1}^{\infty} \mu(B_n) = 0, \quad B = \bigcup\limits_{n=1}^{\infty} B_n \supset \bigcup\limits_{n=1}^{\infty} N_n = N
   $$
   可以得到
   $$
   \bigcup\limits_{n=1}^{\infty} (A_n\cup N_n) = A\cup N\in \widetilde{\mathscr{F}}
   $$
2. 由$\widetilde{\mu}(A\cup N) = \mu(A)$是一意的. 这是因为如果
   $$
   A_1\cup N_1 = A_2\cup N_2\in \widetilde{\mathscr{F}}
   $$
   则
   $$
   \widetilde{\mu}(A_1\cup N_1) = \mu(A_1) = \mu(A_1\cup B_1\cup B_2) \ge \mu(A_2) = \widetilde{\mu}(A_2\cup N_2)
   $$
   同理可得, $\widetilde{\mu}(A_1\cup N_1) \le \widetilde{\mu}(A_2\cup N_2)$. 因此我们有
   $$
   \widetilde{\mu}(A_1\cup N_1) = \widetilde{\mu}(A_2\cup N_2)
   $$
3. $\widetilde{\mu}$是$\widetilde{\mathscr{F}}$上满足$\widetilde{\mu}(A) = \mu(A)$的测度. 这是因为, 如果$\{A_n\cup N_n\}$两两不交, 则$\{A_n\in \mathscr{F}\}$也两两不交, 从而我们有
   $$
   \widetilde{\mu}\left(\bigcup\limits_{n=1}^{\infty} (A_n\cup N_n)\right) = \mu\left(\bigcup\limits_{n=1}^{\infty} A_n\right) = \sum\limits_{n=1}^{\infty} \mu(A_n) = \sum\limits_{n=1}^{\infty} \widetilde{\mu}(A_n\cup N_n)
   $$
   从而$\widetilde{\mu}$是一个测度
4. $(X, \widetilde{\mathscr{F}}, \widetilde{\mu})$是完全测度空间. 这是因为, 如果$A\cup N\in\widetilde{\mathscr{F}}, \widetilde{\mu}(A\cup N)=0$且$C\subset A\cup N$, 则
   $$
   \mu(A\cup B) \le \widetilde{\mu}(A\cup N) + \mu(B) = 0, \quad C\subset A\cup B
   $$
   可以得到$C = \varnothing\cup C\in \widetilde{\mathscr{F}}$
   
#####
___

### 2.2. 半环扩张测度空间的完全化
设$\tau$是半环$\mathscr{Q}$上$\sigma$有限测度$\mu$生成的外测度, 则$(X, \mathscr{F}_{\tau}, \tau)$是$(X, \sigma(\mathscr{Q}), \tau)$的完全化. 

特别地, 测度空间$(\mathbb{R}, \mathscr{F}_{\lambda_F}, \lambda_F)$是测度空间$(\mathbb{R}, \mathscr{B}_{\mathbb{R}}, \lambda_F)$的完全化. 
___
##### Proof:
根据[[#2.1. 每个测度空间都可以被完全化]], 设$\mathscr{F} = \sigma(\mathscr{Q})$, 只需要证明$\widetilde{\mathscr{F}} = \mathscr{F}_{\tau}$. 

设$A\in \mathscr{F}_{\tau}$, 根据[[Lecture 3.2. 测度空间(外测度与测度扩张)#2.3. $ sigma( mathscr{Q})$上的测度$ tau$和$ mathscr{F}_{ tau}$上的测度$ tau$的关系|sigma域上的测度和tau可测集上的测度的关系]]知道, 存在 $C\in\mathscr{F}$使得$C\supset A$且$\tau(C\backslash A) =0$. 对$C\backslash A\in \mathscr{F}_{\tau}$, 同样有, 存在 $B\in \mathscr{F}$ 使得$B\supset C\backslash A$且$\tau(B) = \tau(C\backslash A)=0$. 从而
$$
\begin{aligned} 
    A &= (A\cap B^c) \cup (A\cap B) \\ 
    & = \left([(C\backslash A)\cup A]\cap B^c\right) \cup (A\cap B) \\ 
    & = (C\cap B^c)\cup (A\cap B)
\end{aligned}
$$
注意到$C\cap B^c\in \mathscr{F}$, $A\cap B\subset B\in \mathscr{F}$且$\tau(B)=0$, 于是得到了$A\in \widetilde{\mathscr{F}}$, 这表明$\mathscr{F}_{\tau}\subset \widetilde{\mathscr{F}}$. 

设$A\in \widetilde{\mathscr{F}}$, $A = A_0\cup N$, 其中$A_0\in \mathscr{F}$, $N\subset B\in \mathscr{F}$且$\tau(B) = 0$. 因为$(X, \mathscr{F}_{\tau}, \tau)$是完全测度空间, 故一定有$N\in \mathscr{F}_{\tau}$, 从而$A\in \mathscr{F}_{\tau}$, 这又证明了$\mathscr{F}_{\tau}\subset \widetilde{\mathscr{F}}$.

#####
___