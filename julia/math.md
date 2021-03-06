---
title: "Julia数学运算和基本函数"
meta_title: ''
meta_description: ''
keywords: 
    - julia
sidebar: "julia"
permalink: "/julia/index.html"
---
# Julia 数学运算和基本函数

## 数学运算和基本函数

Julia 为它所有的基础数值类型，提供了整套的基础算术和位运算，也提供了一套高效、可移植的标准数学函数。

## 算术运算符

下面的[算术运算符](http://zh.wikipedia.org/zh-cn/算术#.E7.AE.97.E8.A1.93.E9.81.8B.E7.AE.97)适用于所有的基本数值类型：

| 表达式  | 名称     | 描述             |
| :------ | :------- | :--------------- |
| `+x`    | 一元加法 | x 本身           |
| `-x`    | 一元减法 | 相反数           |
| `x + y` | 二元加法 | 做加法           |
| `x - y` | 二元减法 | 做减法           |
| `x * y` | 乘法     | 做乘法           |
| `x / y` | 除法     | 做除法           |
| `x \ y` | 反除     | 等价于 y / x     |
| `x ^ y` | 乘方     | x 的 y 次幂      |
| `x % y` | 取余     | 等价于 rem(x, y) |

以及 `Bool` 类型的非运算：

| 表达式 | 名称 | 描述               |
| :----- | :--- | :----------------- |
| `!x`   | 非   | true 和 false 互换 |

Julia 的类型提升系统使得参数类型混杂的算术运算也很简单自然。详见类型转换和类型提升 

算术运算的例子：

```julia
1 + 2 + 3


1 - 2


3*2/12
```

（习惯上，优先级低的运算，前后多补些空格。这不是强制的。）

## 位运算符

下面的 位运算符 适用于所有整数类型：

| 表达式    | 名称                         |
| :-------- | :--------------------------- |
| `~x`      | 按位取反                     |
| `x & y`   | 按位与                       |
| `x \| y`  | 按位或                       |
| `x $ y`   | 按位异或                     |
| `x >>> y` | 向右 逻辑移位 （高位补 0 ）  |
| `x >> y`  | 向右 算术移位 （复制原高位） |
| `x << y`  | 向左逻辑/算术移位            |

位运算的例子：

```julia
~123

123 & 234

123 | 234

123 $ 234

~uint32(123)

~uint8(123)
```

## 复合赋值运算符

二元算术和位运算都有对应的复合赋值运算符，即运算的结果将会被赋值给左操作数。在操作符的后面直接加上 `=` 就组成了复合赋值运算符。例如, `x += 3` 相当于 `x = x + 3` ：

```julia
x = 1

x += 3

x
```

复合赋值运算符有：

`+=  -=  *=  /=  \=  %=  ^=  &=  |=  $=  >>>=  >>=  <<=`

## 数值比较

所有的基础数值类型都可以使用比较运算符：

| 运算符 | 名称     |
| :----- | :------- |
| `==`   | 等于     |
| `!=`   | 不等于   |
| `<`    | 小于     |
| `<=`   | 小于等于 |
| `>`    | 大于     |
| `>=`   | 大于等于 |

一些例子：

```julia
1 == 1

1 == 2

1 != 2

1 == 1.0

1 < 2

1.0 > 3

1 >= 1.0

-1 <= 1

-1 <= -1

-1 <= -2

3 < -0.5
```

整数是按位比较的。浮点数是 [IEEE 754](http://zh.wikipedia.org/zh-cn/IEEE_754) 标准 比较的：

- 有限数按照正常方式做比较。
- 正数的零等于但不大于负数的零。
- `Inf` 等于它本身，并且大于所有数, 除了 `NaN`。
- `-Inf` 等于它本身，并且小于所有数, 除了 `NaN`。
- `NaN` 不等于、不大于、不小于任何数，包括它本身。

上面最后一条是关于 `NaN` 的性质，值得留意：

```julia
NaN == NaN

NaN != NaN

NaN < NaN

NaN > NaN
```

`NaN` 在[*矩阵*]中使用时会带来些麻烦：

```julia
[1 NaN] == [1 NaN]
```

Julia 提供了附加函数, 用以测试这些特殊值，它们使用哈希值来比较：

| 函数            | 测试             |
| :-------------- | :--------------- |
| `isequal(x, y)` | x 是否等价于 y   |
| `isfinite(x)`   | x 是否为有限的数 |
| `isinf(x)`      | x 是否为无限的数 |
| `isnan(x)`      | x 是否不是数     |

`isequal` 函数，认为 `NaN` 等于它本身：

```julia
isequal(NaN,NaN)

isequal([1 NaN], [1 NaN])

isequal(NaN,NaN32)
```

`isequal` 也可以用来区分有符号的零：

```julia
-0.0 == 0.0

isequal(-0.0, 0.0)
```

## 链式比较

与大多数语言不同，Julia 支持 [Python链式比较](http://en.wikipedia.org/wiki/Python_syntax_and_semantics#Comparison_operators) ：

```julia
1 < 2 <= 2 < 3 == 3 > 2 >= 1 == 1 < 3 != 5
```

对标量的比较，链式比较使用 `&&` 运算符；对逐元素的比较使用 `&` 运算符，此运算符也可用于数组。例如， `0 .< A .< 1` 的结果是一个对应的布尔数组，满足条件的元素返回 `true` 。

操作符 `.<` 是特别针对数组的; 只有当 `A` 和 `B` 有着相同的大小时, `A .< B` 才是合法的。比较的结果是布尔型数组, 其大小同 `A` 和 `B` 相同. 这样的操作符被称为*按元素*操作符; Julia 提供了一整套的按元素操作符: `.*`, `.+`, 等等。 有的按元素操作符也可以接受纯量, 例如上一段的 `0 .< A .< B`. 这种表示法的意思是, 相应的纯量操作符会被施加到每一 个元素上去。

注意链式比较的比较顺序：

```julia
v(x) = (println(x); x)

v(1) < v(2) <= v(3)

v(1) > v(2) <= v(3)
```

中间的值只计算了一次，而不是像 `v(1) < v(2) && v(2) <= v(3)` 一样计算了两次。但是，链式比较的计算顺序是不确定的。不要在链式比较中使用带副作用（比如打印）的表达式。如果需要使用副作用表达式，推荐使用短路 `&&` 运算符（详见[短路求值])）。

### 运算优先级

Julia 运算优先级从高至低依次为：

| 类型 | 运算符                                                       |
| :--- | :----------------------------------------------------------- |
| 语法 | `.` 跟随 `::`                                                |
| 幂   | `^` 和 `.^` 等效                                             |
| 分数 | `//` 和 `.//`                                                |
| 乘除 | `/ % & \`和 `.* ./ .% .\`                                    |
| 位移 | `<< >> >>>` 和 `.<< .>> .>>>`                                |
| 加减 | `+ - | $` 和 `.+ .-`                                         |
| 语法 | `: ..` 跟随于 `|>`                                           |
| 比较 | `> < >= <= == === != !== <:` 和 `.> .< .>= .<= .== .!=`      |
| 逻辑 | `&&` 跟随于 `||` 跟随于 `?`                                  |
| 赋值 | `= += -= *= /= //= \= ^= %= \|= &= $= <<= >>= >>>=` 及 `.+= .-= .*= ./= .//= .\= .^= .%=` |

## 基本函数

Julia 提供了一系列数学函数和运算符：

### 舍入函数

| 函数        | 描述                  | 返回类型      |
| :---------- | :-------------------- | :------------ |
| `round(x)`  | 把 x 舍入到最近的整数 | FloatingPoint |
| `iround(x)` | 把 x 舍入到最近的整数 | Integer       |
| `floor(x)`  | 把 x 向 -Inf 取整     | FloatingPoint |
| `ifloor(x)` | 把 x 向 -Inf 取整     | Integer       |
| `ceil(x)`   | 把 x 向 +Inf 取整     | FloatingPoint |
| `iceil(x)`  | 把 x 向 +Inf 取整     | Integer       |
| `trunc(x)`  | 把 x 向 0 取整        | FloatingPoint |
| `itrunc(x)` | 把 x 向 0 取整        | Integer       |

### 除法函数

| 函数          | 描述                                                  |
| :------------ | :---------------------------------------------------- |
| `div(x,y)`    | 截断取整除法；商向 0 舍入                             |
| `fld(x,y)`    | 向下取整除法；商向 -Inf 舍入                          |
| `cld(x,y)`    | 向上取整除法; 商向 +Inf 舍入                          |
| `rem(x,y)`    | 除法余数；满足 x == div(x,y)*y + rem(x,y) ，与 x 同号 |
| `divrem(x,y)` | 返回 (div(x,y),rem(x,y))                              |
| `mod(x,y)`    | 取模余数；满足 x == fld(x,y)*y + mod(x,y) ，与 y 同号 |
| `mod2pi(x)`   | 对 2pi 取模余数； 0 <= mod2pi(x) < 2pi                |
| `gcd(x,y...)` | x, y, ... 的最大公约数，与 x 同号                     |
| `lcm(x,y...)` | x, y, ... 的最小公倍数，与 x 同号                     |

### 符号函数和绝对值函数

| 函数            | 描述                                       |
| :-------------- | :----------------------------------------- |
| `abs(x)`        | x 的幅值                                   |
| `abs2(x)`       | x 的幅值的平方                             |
| `sign(x)`       | x 的正负号，返回值为 -1, 0, 或 +1          |
| `signbit(x)`    | 是否有符号位，有 (true) 或者 无 (false)    |
| `copysign(x,y)` | 返回一个数，它具有 x 的幅值， y 的符号位   |
| `flipsign(x,y)` | 返回一个数，它具有 x 的幅值， x*y 的符号位 |

### 乘方，对数和开方

| 函数                                         | 描述                                                         |
| :------------------------------------------- | :----------------------------------------------------------- |
| `sqrt(x)`                                    | √x x 的平方根                                                |
| `cbrt(x)`                                    | ?x x 的立方根                                                |
| `hypot(x,y)`                                 | 误差较小的 sqrt(x^2 + y^2)                                   |
| `exp(x)`                                     | 自然指数 e 的 x 次幂                                         |
| `expm1(x)`                                   | 当 x 接近 0 时，精确计算 exp(x)-1                            |
| `ldexp(x,n)` |当 n 为整数时，高效计算`x*2^n` |                                                              |
| `log(x)`                                     | x 的自然对数                                                 |
| `log(b,x)`                                   | 以 b 为底 x 的对数                                           |
| `log2(x)`                                    | 以 2 为底 x 的对数                                           |
| `log10(x)`                                   | 以 10 为底 x 的对数                                          |
| `log1p(x)`                                   | 当 x 接近 0 时，精确计算 log(1+x)                            |
| `exponent(x)`                                | trunc(log2(x))                                               |
| `significand(x)`                             | returns the binary significand (a.k.a. mantissa) of a floating-point number x |

为什么要有 `hypot`, `expm1`, `log1p` 等函数，参见 John D. Cook 的博客： [expm1](http://www.johndcook.com/blog/2010/06/07/math-library-functions-that-seem-unnecessary/), [log1p](http://www.johndcook.com/blog/2010/06/07/math-library-functions-that-seem-unnecessary/), [erfc](http://www.johndcook.com/blog/2010/06/07/math-library-functions-that-seem-unnecessary/) 和 [hypot](http://www.johndcook.com/blog/2010/06/02/whats-so-hard-about-finding-a-hypotenuse/) 。

### 三角函数和双曲函数

Julia 内置了所有的标准三角函数和双曲函数

`sin    cos    tan    cot    sec    csc sinh   cosh   tanh   coth   sech   csch asin   acos   atan   acot   asec   acsc asinh  acosh  atanh  acoth  asech  acsch sinc   cosc   atan2
`

除了 [atan2](http://zh.wikipedia.org/zh-cn/Atan2) 之外，都是单参数函数。 `atan2` 给出了 `x` 轴，与由 `x` 、 `y` 确定的点之间的[弧度](http://zh.wikipedia.org/zh-cn/弧度) 。

另外，`sinpi(x)`和 `cospi(x)`各自被提供给更准确的 `sin(pi*x)`和 `cos(pi*x)`的计算。

如果想要以度，而非弧度，为单位计算三角函数，应使用带 d 后缀的函数。例如，sind(x) 计算 x 的正弦值，这里 x 的单位是度。以下的列表是全部的以度为单位的三角函数：

`sind   cosd   tand   cotd   secd   cscd asind  acosd  atand  acotd  asecd  acscd`

### 特殊函数

| 函数                                          | 描述                                                         |
| :-------------------------------------------- | :----------------------------------------------------------- |
| `erf(x)`                                      | x 处的 误差函数                                              |
| `erfc(x)`                                     | 补误差函数。当 x 较大时，精确计算 1-erf(x)                   |
| `erfinv(x)`                                   | erf 的反函数                                                 |
| `erfcinv(x)`                                  | erfc 的反函数                                                |
| `erfi(x)`                                     | 将误差函数定义为 -im *erf(x* im) ，其中 im 是虚数单位        |
| `erfcx(x)`                                    | 缩放的互补误差函数，即对较大的 x 值的准确的 exp（x ^ 2）* erfc（x） |
| `dawson(x)`                                   | 缩放虚误差函数，又名道森函数，即对较大的 x 值求精确的 exp(-x^2) *erfi(x)* sqrt(pi) / 2 |
| `gamma(x)`                                    | x 处的 gamma 函数                                            |
| `lgamma(x)`                                   | 当 x 较大时，精确计算 log(gamma(x))                          |
| `lfact(x)`                                    | 对较大的 x 求精确的 log(factorial(x)); 与对大于 1 的 x 值求 lgamma(x+1) 相等, 否则等于 0 |
| `digamma(x)`                                  | x 处的 digamma 函数，即导数的衍生                            |
| `beta(x,y)`                                   | 在（x,y）处的 beta 函数                                      |
| `lbeta(x,y)`                                  | 对较大的 x 或 y 值求准确的 log(beta(x,y))                    |
| `eta(x)`                                      | x 处的 Dirichlet eta 函数                                    |
| `zeta(x)`                                     | x 处的 Riemann zeta 函数                                     |
| `airy(z)`, `airyai(z)`, `airy(0,z)`           | z 处的 Airy Ai 函数                                          |
| `airyprime(z)`, `airyaiprime(z)`, `airy(1,z)` | Airy Ai 函数在 z 处的导数                                    |
| `airybi(z)`, `airy(2,z)`                      | z 处的 Airy Bi 函数                                          |
| `airybiprime(z)`, `airy(3,z)`                 | Airy Bi 函数在 z 处的导数                                    |
| `airyx(z)`, `airyx(k,z)`                      | 缩放 Airy Ai 函数 以及 k 对 z 的导数                         |
| `besselj(nu,z)`                               | 对 z 中一阶 nu 的贝塞尔函数                                  |
| `besselj0(z)`                                 | besselj(0,z)                                                 |
| `besselj1(z)`                                 | besselj(1,z)                                                 |
| `besseljx(nu,z)`                              | 对 z 中一阶 nu 的缩放贝塞尔函数                              |
| `bessely(nu,z)`                               | 对 z 中二阶 nu 的贝塞尔函数                                  |
| `bessely0(z)`                                 | bessely(0,z)                                                 |
| `bessely1(z)`                                 | bessely(1,z)                                                 |
| `besselyx(nu,z)`                              | 对 z 中二阶 nu 的缩放贝塞尔函数                              |
| `besselh(nu,k,z)`                             | 对 z 中三阶 nu （例如汉克尔函数）的贝塞尔函数； k 必须为 1 或 2 |
| `hankelh1(nu,z)`                              | besselh(nu, 1, z)                                            |
| `hankelh1x(nu,z)`                             | 缩放 besselh(nu, 1, z)                                       |
| `hankelh2(nu,z)`                              | besselh(nu, 2, z)                                            |
| `hankelh2x(nu,z)`                             | 缩放 besselh(nu, 2, z)                                       |
| `besseli(nu,z)`                               | 对 z 中一阶 nu 的修正贝塞尔函数                              |
| `besselix(nu,z)`                              | 对 z 中一阶 nu 的缩放修正贝塞尔函数                          |
| `besselk(nu,z)`                               | 对 z 中二阶 nu 的修正贝塞尔函数                              |
| `besselkx(nu,z)`                              | 对二阶 o 的缩放修正贝塞尔函数                                |
<code class=backend-type backend-type=free></code>
<code class=gatsby-kernelname data-language=julia></code>
<script type="text/javascript" src="https://cdn.freeaihub.com/asset/js/cell.js"></script>
