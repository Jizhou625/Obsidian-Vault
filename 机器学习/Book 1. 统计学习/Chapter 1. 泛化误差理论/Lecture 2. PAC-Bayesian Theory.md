## 1. 贝叶斯学派和频率学派的对比

|  |<center>频率学派</center>|<center>贝叶斯学派</center>|
|-------------------|:---------------------:|--------------------|
|Views of Probability|Laws of Large Number|Degree of Belief|
|Hypothesis Space| $\mathcal{H}$ | Prior Distribution $\mathcal{P}(h)$ |
|Output of Learning| $h\in \mathcal{H}$ | Posterior Distribution $\mathcal{Q}(h)$ |
|Performance Evaluation| $\mathrm{Err}_D(h)=\mathbb{P}_D(y\neq h(x))$ | $\mathrm{Err}_D(\mathcal{Q})=\mathbb{E}_{h\sim\mathcal{Q}}[\mathbb{P}_{D}[y\neq h(x)]]$ |
|Generalization Theory| For all $h\in \mathcal{H}$, $\mathrm{Err}_D(h)\leq \mathrm{Err}_S(h)+O\left(\sqrt{\dfrac{d\ln n+ \ln (1/\delta)}{n}}\right)$ | For all $\mathcal{Q}$, $\mathrm{Err}_D(\mathcal{Q})\leq \mathrm{Err}_S(\mathcal{Q})+\sqrt{\dfrac{\mathrm{KL}(Q\mid \mid P)+\ln (3/\delta)}{n}}$|

## 2. PAC-Bayesian Theory
### 2.1. 测度变换
设$\mathcal{H}$是所有分类器组成的集合, 对任意的泛函$f:\mathcal{H}\rightarrow \mathbb{R}$和任意$\mathcal{H}$上的概率分布$\mathcal{P}$, $\mathcal{Q}$, 我们有
$$
\mathbb{E}_{h\sim \mathcal{Q}}[f(h)] \le  \ln \mathbb{E}_{h\sim \mathcal{P}}\left[e^{f(h)}\right]  + \mathrm{KL}(\mathcal{Q}\mid \mid \mathcal{P})
$$
___
##### Proof
$$
\begin{aligned} 
     \ln \mathbb{E}_{h\sim \mathcal{P}}\left[e^{f(h)}\right]  + \mathrm{KL}(\mathcal{Q}\mid \mid \mathcal{P})  - \mathbb{E}_{h\sim \mathcal{Q}}[f(h)] & = \mathbb{E}_{h\sim \mathcal{Q}}\left[\ln \mathbb{E}_{h\sim \mathcal{P}}\left[e^{f(h)}\right] + \ln \dfrac{\mathcal{Q}(h)}{\mathcal{P}(h)} - f(h)\right] \\ 
     & = \mathbb{E}_{h\sim \mathcal{Q}}\left[\ln\dfrac{\mathcal{Q}(h)}{\frac{\mathcal{P}(h)e^{f(h)}}{\mathbb{E}_{h\sim \mathcal{P}} \left[e^{f(h)}\right]}}\right] \\
     & = D_{\mathrm{KL}}\left(\mathcal{Q} \mid\mid \frac{\mathcal{P}(h)e^{f(h)}}{\mathbb{E}_{h\sim \mathcal{P}} \left[e^{f(h)}\right]} \right) \\ 
    & \ge 0
\end{aligned}
$$
因此
$$
\mathbb{E}_{h\sim \mathcal{Q}}[f(h)] \le  \ln \mathbb{E}_{h\sim \mathcal{P}}\left[e^{f(h)}\right]  + \mathrm{KL}(\mathcal{Q}\mid \mid \mathcal{P})
$$
#####
___

### 2.2. PAC-Bayesian 泛化界
考虑数据集$D$上的二分类问题, 对任意的prior distribution $\mathcal{P}$和任意学习到的posterior distribution $\mathcal{Q}$, 至少以$1-\delta$的概率, 我们有
$$
\mathbb{E}_{h\sim \mathcal{Q}}[\mathrm{Err}_D(h)] \leq \mathbb{E}_{h\sim \mathcal{Q}}[\mathrm{Err}_S(h)] + \sqrt{\dfrac{\mathrm{KL}(\mathcal{Q}\mid \mid \mathcal{P})+\ln (3/\delta)}{n}}
$$
___
##### Proof
设$\Delta = \left|\mathrm{Err}_D(h) - \mathrm{Err}_S(h) \right|$. 则我们需要证明的是
$$
\mathbb{E}_{h\sim \mathcal{Q}} \left[\Delta\right] \leq \sqrt{\dfrac{\mathrm{KL}(\mathcal{Q}\mid \mid \mathcal{P})+\ln (3/\delta)}{n}} 
$$
根据Jensen不等式, 我们有
$$
\begin{aligned} 
\left(\mathbb{E}_{h\sim \mathcal{Q}} \left[\Delta\right]\right)^2 &\le \dfrac{1}{n} \mathbb{E}_{h\sim \mathcal{Q}} \left[n \Delta^2\right]     \\ 
& = \dfrac{1}{n} \left(\ln \mathbb{E}_{h\sim \mathcal{P}} \left[e^{n\Delta^2}\right] + D_{\mathrm{KL}} (\mathcal{Q}\mid \mid \mathcal{P}) \right)    \\
\end{aligned}
$$
这意味着我们只要证明, 对任意的$\delta>0$, 
$$
\mathbb{P}_{S\sim D^n}\left[\mathbb{E}_{h\sim \mathcal{P}} \left[e^{n\Delta^2}\right] \ge \dfrac{3}{\delta} \right] \le \delta \tag{1}
$$
使用[[../../../概率论/Book 2. 概率论/Chapter 1. 概率不等式/Lecture 2. Hoeffding Type Bounds#2. Hoeffding Inequality|Lecture 2. Hoeffding Inequality]], 我们可以得到
$$
\mathbb{P}_{S\sim D^n} [\Delta \ge \varepsilon] \le 2\exp(-2n\varepsilon^2)
$$
则我们可以得到
$$
\begin{aligned} 
\mathbb{E}_{S\sim D^n} [e^{n\Delta^2}] &= \int_{0}^{\infty} \mathbb{P}_{S\sim D^n} \left[e^{n\Delta^2} \ge t\right] \mathrm{d}t \\ 
& = \int_{0}^{1} \mathbb{P}_{S\sim D^n} \left[e^{n\Delta^2} \ge t\right] \mathrm{d}t  + \int_{1}^{\infty} \mathbb{P}_{S\sim D^n} \left[e^{n\Delta^2} \ge t\right] \mathrm{d}t \\ 
& \le 1 + \int_{1}^{\infty} \mathbb{P}_{S\sim D^n} \left[\Delta \ge \sqrt{\dfrac{\ln t}{n}}\right] \mathrm{d}t \\
& \le 1 + \int_{1}^{\infty} 2\exp(-2\ln t) \mathrm{d}t \\
& =3
\end{aligned}
$$
于是我们有
$$
\begin{aligned} 
\mathbb{P}_{S\sim D^n}\left[\mathbb{E}_{h\sim \mathcal{P}} \left[e^{n\Delta^2}\right] \ge \dfrac{3}{\delta} \right] & = \mathbb{P}_{S\sim D^n}\left[\mathbb{E}_{h\sim \mathcal{P}}\left[e^{n\Delta^2}\right] \ge \dfrac{3}{\delta}\right] \\ 
& \le  \dfrac{\mathbb{E}_{S\sim D^n}\left[\mathbb{E}_{h\sim \mathcal{P}}\left[e^{n\Delta^2}\right] \right]}{3/\delta}\\
& = \dfrac{\mathbb{E}_{h\sim \mathcal{P}}\left[\mathbb{E}_{S\sim D^n}\left[e^{n\Delta^2}\right] \right]}{3/\delta} \\ 
& \le \delta 
\end{aligned}
$$
这就证明了$(1)$
#####
___