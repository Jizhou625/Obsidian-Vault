## 1. 常见收敛方式
### 1.1. 依概率收敛
设$\boldsymbol{x}^{(n)}, n\in \mathbb{N}$是一列随机向量，$\boldsymbol{x}$是一个随机向量，如果对于任意的$\varepsilon>0$，有
$$
\lim _{n \rightarrow \infty} \mathbb{P}\left(\left\|\boldsymbol{x}^{(n)}-\boldsymbol{x}\right\| \geq \varepsilon\right)=0
$$
则称$\boldsymbol{x}^{(n)}$依概率收敛于$\boldsymbol{x}$, 记为$\boldsymbol{x}^{(n)} \stackrel{p}{\rightarrow} \boldsymbol{x}$

### 1.2. 几乎必然收敛
设$\boldsymbol{x}^{(n)}, n\in \mathbb{N}$是一列随机向量，$\boldsymbol{x}$是一个随机向量，如果
$$
\mathbb{P}\left(\lim _{n \rightarrow \infty}\left\|\boldsymbol{x}^{(n)}-\boldsymbol{x}\right\|=0\right)=1
$$
则称$\boldsymbol{x}^{(n)}$几乎必然收敛(以概率1收敛)于$\boldsymbol{x}$, 记为$\boldsymbol{x}^{(n)} \stackrel{\text { a.s. }}{\rightarrow} \boldsymbol{x}$. 这里$\lim\limits _{n \rightarrow \infty}\left\|\boldsymbol{x}^{(n)}-\boldsymbol{x}\right\|=0$代表了事件
$$
\left\{w: \lim _{n \rightarrow \infty}\left\|\boldsymbol{x}^{(n)}(w)-\boldsymbol{x}(w)\right\|=0\right\} \subset \Omega
$$

### 1.3. 依分布收敛
设$\boldsymbol{x}^{(n)}, n\in \mathbb{N}$是一列随机向量，$\boldsymbol{x}$是一个随机向量，如果对于所有使得$F_{\boldsymbol{x}}(\boldsymbol{t})$连续的点$\boldsymbol{t}$, 都有
$$
\lim _{n \rightarrow \infty} F_{\boldsymbol{x}^{(n)}}(\boldsymbol{t})=F_{\boldsymbol{x}}(\boldsymbol{t})
$$
则称$\boldsymbol{x}^{(n)}$依分布收敛于$\boldsymbol{x}$, 记为$\boldsymbol{x}^{(n)} \stackrel{d}{\rightarrow} \boldsymbol{x}$

## 2. 几种收敛模式的关系
### 2.1. 几乎必然收敛 $\to$ 依概率收敛