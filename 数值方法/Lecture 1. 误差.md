## 1. 误差分析
### 1.1. 前向误差和后向误差
设 $f$ 是一个函数, $r$ 是 $f(r)=0$ 的一个根, 假设 $x_a$ 是 $r$ 的近似值, 对于根求解问题
1. 前向误差是 $\left|r-x_a\right|$, 前向误差是指值的修正量
2. 后向误差是 $\left|f\left(x_a\right)\right|$, 后向误差是指函数的改变量

### 1.2. 威尔金森(Wilkinson)多项式
一个难以进行数值求解的多项式为威尔金森多项式 
$$
W(x)=(x-1)(x-2) \cdots(x-20)
$$
当我们将所有乘法展开进行求值运算时, 由于近似相等和大数字的消去, 求根结果会产生一定的误差. 


用下面的代码和scipy.optimize库来求解Wilkinson不等式, 即使给定正确的初值19, 也会得到不正确的结果19.000003
    
```python
x = sympy.symbols('x')
def f(x: float)->float:
    '''
    Calculates the value of (x-1)(x-2)...(x-20)
    '''
    res = 1
    for i in range(1, 21):
        res *= (x - i)
    return res
func = sympy.expand(f(x))
display(func)
func = sympy.lambdify(x, func, "numpy")
fsolve(func, 19)
```

