---
title: "Python3 基本数据类型-元组 - FreeAIHub"
meta_title: ''
meta_description: ''
keywords: 
    - python3
    - Python3 基本数据类型-元组
    - tuple
sidebar: "python3"
permalink: "/python3/tuple.html"
---
# Python3基础数据类型-元组

Python 的元组与列表类似，不同之处在于元组的元素不能修改。

元组使用小括号，列表使用方括号。

## 元组创建
元组创建很简单，只需要在括号中添加元素，并使用逗号隔开即可。

#### 练习:元组创建
```Python
tup1 = ('Google', 'Python', 1997, 2000)
tup2 = (1, 2, 3, 4, 5 )
tup3 = "a", "b", "c", "d"   #  不需要括号也可以
type(tup1),type(tup2),type(tup3)
```
创建空元组
```Python
tup1 = ()
tup1
```

元组中只包含一个元素时，需要在元素后面添加逗号，否则括号会被当作运算符使用：
```Python
tup1 = (50)
type(tup1)     # 不加逗号，类型为整型
 
tup1 = (50,)
type(tup1)     # 加上逗号，类型为元组
```
元组与字符串类似，下标索引从0开始，可以进行截取，组合等。

## 访问元组

元组可以使用下标索引来访问元组中的值。

#### 练习:元组访问
```Python
tup1 = ('Google', 'Python', 1997, 1984)
tup2 = (1, 2, 3, 4, 5, 6, 7 )
 
print("tup1[0]: ", tup1[0])
print("tup2[1:5]: ", tup2[1:5])
```

## 修改元组

元组中的元素值是不允许修改的，但我们可以对元组进行连接组合

#### 练习:修改元组

```Python
tup1 = (12, 34.56)
tup2 = ('abc', 'xyz')
 
# 以下修改元组元素操作是非法的。
# tup1[0] = 100
 
# 创建一个新的元组
tup3 = tup1 + tup2
print(tup3)
```

## 删除元组

元组中的元素值是不允许删除的，但我们可以使用`del`语句来删除整个元组。

#### 练习:
```Python
tup = ('Google', 'Python', 1997, 2000)
print(tup)
del tup[0]#'tuple' object doesn't support item deletion
```
以上实例元组被删除后，输出变量会有异常信息


## 元组运算符

与字符串一样，元组之间可以使用 + 号和 * 号进行运算。这就意味着他们可以组合和复制，运算后会生成一个新的元组。

| Python 表达式                  | 结果                         | 描述         |
| :----- | :--- | :----- |
| `len((1, 2, 3))`               | 3                            | 计算元素个数 |
| `(1, 2, 3) + (4, 5, 6)`        | (1, 2, 3, 4, 5, 6)           | 连接         |
| `('Hi!',) * 4`                 | ('Hi!', 'Hi!', 'Hi!', 'Hi!') | 复制         |
| `3 in (1, 2, 3)`               | True                         | 元素是否存在 |
| `for x in (1, 2, 3): print(x,)` | 1 2 3                        | 迭代         |

## 元组索引，截取

因为元组也是一个序列，所以我们可以访问元组中的指定位置的元素，也可以截取索引中的一段元素，

#### 练习：元组索引读取

```Python
L = ('Google', 'Taobao', 'Python')
print(L[2] )
print(L[-2])
print(L[1:])
```

| Python 表达式 | 结果                 | 描述                                 |
| : | :- | :----- |
| `L[2]`       | 'Python'             | 读取第三个元素                       |
| `L[-2]`       | 'Taobao'             | 反向读取，读取倒数第二个元素         |
| `L[1:]`       | ('Taobao', 'Python') | 截取元素，从第二个开始后的所有元素。 |

## 作业：

### 天气温度统计
气象局使用元组tuple记录了本市过去七天的最高温度与最低温度。最高温度分别为30,28,29,31,33,35,32，最低温度分别为23,19,19,22,18,24,22。请分别计算出：
- 过去七天每天的平均温度
- 本周的最高与最低温度
- 本周的平均温度

```Python
#作业在这里完成
```

<code class=backend-type backend-type=free></code>
<code class=gatsby-kernelname data-language=python></code>
<script type="text/javascript" src="https://cdn.freeaihub.com/asset/js/cell.js"></script>
