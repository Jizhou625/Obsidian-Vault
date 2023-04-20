## 1. 指向变量的指针    
### 1.1. 数组与指针
**数组被隐式转化为指针**: 考虑指向数组首个元素的指针的初始化
```cpp
int* p{&a[0]};
```
这个过程可以简化为：

```cpp
int* p{a};
```
这是因为数组可以隐式转换到指向其首元素的指针。也就是，数组 `a` 可以转换为 `&a[0]`。在各种期望指针的语境下，如果传入一个数组，那么 C++ 就会自动执行这个隐式转换。比如：
```cpp
int a[5]{};
cout << a << endl;
```
当把数组放在 `cout <<` 后面时，因为 `cout` 不能输出一个数组，但能输出一个指针的值，所以会发生数组到指针的转换。此时，输出的结果就是一个地址：
```io
0x62fe00
```
此外, 默认的下标表达式 `a[b]` 总是会解析为 `*(a + b)` 来运算(这是一个语法糖)。因此如果想获取数组的第四个元素，不仅可以写 `a[3]`，也可以写 `3[a]`

**数组的地址**: 字面上，`&a` 就是取数组 `a` 的地址
```cpp codemo(show)
#include <iostream>
using namespace std;
int main() {
    int a[5]{};
    cout << &a << endl;
    cout << a << endl;
}
```
它们的输出是一样的：
```io
0x62fe00
0x62fe00
```
但是, `a` 被转换为指向 `int` 的指针类型；而 `&a` 则是指向 `int[5]` 的指针类型。所以有了下面的结果：
```cpp codemo(show)
#include <iostream>
using namespace std;
int main() {
    int a[5]{};
    cout << sizeof(*(&a)) << endl;
    cout << sizeof(*( a)) << endl;
}
```
```io
20
4
```

### 1.2. 指向int[N]的指针类型
考虑一个二维数组
```cpp
int a[4][5]{};
cout << a << endl;
```
这时，`a` 是一个二维数组，即由 4 个 `int[5]` 构成的数组。当它被输出时，会隐式转换成指向首元素 `a[0]` 的指针。然而首元素 `a[0]` 是 `int[5]` 类型的数组，所以这时输出的也是一个指向 `int[5]` 的指针. 对于这样的指针, 正确的声明写法应该是
```cpp
int (*p)[5]{nullptr};
```
其中`(*p)`的括号是不能省的，一旦省略就变成由 5 个 `int*` 构成的数组了，而非一个指针

### 1.3. 指针的只读性
如果要声明一个只读的指针，需要把 `const` 放在 `*` 的右边。
```cpp
int a;
int* const p{&a}; // p 是指向 int 的只读指针
```
这时，`*p` 是 `int` 类型可以更改，但是 `p` 只读不能更改——也就是说，`p` 自始至终只能指向一个确定的变量
```cpp codemo(show)
#include <iostream>
using namespace std;
int main() {
    int a{42};
    int* const p{&a};
    *p = 56;     // OK，*p 是 int 类型
    p = nullptr; // 错误, p 是只读的
}
```

### 1.4. 字符数组的特殊性和void指针
如果 `cout <<` 后面接的是一个字符数组，那么可以做到输出一个字符串。然而这里应当发生数组到指针的隐式转换，所以 `cout <<` 实际上是对 `char*` 类型的输出做了特殊的处理。这也就是为什么我们不能直接通过 `cout` 输出指向 `char` 类型的指针：
```cpp
char a{};
char* p{&a};
cout << p << endl; // 输出空字符串，而非地址
```
要输出 `char*` 指针的值, 我们可以用void指针进行类型转换. 
```cpp
void printPtr(void* p) {
    cout << p << endl;
}
```
通过这个函数，可以输出 `char*` 指针的值（而非输出字符串）。这是因为发生了从 `char*` 到 `void*` 的转换

## 2. 指向函数的指针
### 2.1. 函数指针的声明
C/C++ 还提供了指向函数的指针，俗称为函数指针。它的声明如下：
```sdsc
返回值类型 (*指针名)([参数列表]){初始化器};
```
比如：
```cpp
int (*ptr)(int, int){nullptr};
```
它是一个基类型为函数的指针。其中这个函数必须接收参数列表所规定的数量、类型的参数，且返回值类型为返回值类型。例如
```cpp
int (*ptr)(int, int){nullptr};
int max(int, int);
int main() {
    ptr = &max; // ptr 存储了函数 max 的地址，即指向 max
}
```
可以通过函数指针的解地址运算符来调用其所指向的函数：
```cpp
int (*ptr)(int, int){&max};
(*ptr)(3, 5); // 调用了 max 函数
```

除此之外，C/C++ 提供了一些“快捷方式”：
1. 所有的函数都可以隐式转换到指向自身的指针；
2. 函数指针可以不经过解地址运算符，直接调用其所指向的函数。

具体说就是：
```cpp codemo(show)
int (*ptr)(int, int){nullptr};
int max(int a, int b) {
    return a > b ? a : b;
}
int main() {
    ptr = &max;   // 正常的赋值
    ptr = max;    // 亦可：max 先隐式转换为 &max，随后赋值

    (*ptr)(3, 5); // 先解地址，然后调用
    ptr(3, 5);    // 亦可：允许不解地址，直接调用其所指向的函数
}
```
