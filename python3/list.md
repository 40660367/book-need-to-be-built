---
title: "Python3 基本数据类型-列表 - FreeAIHub"
meta_title: ''
meta_description: ''
keywords: 
    - python3
    - Python3 基本数据类型-列表
    - list
sidebar: "python3"
permalink: "/python3/list.html"
---
# Python3基础数据类型-列表

列表是最常用的Python数据类型，它可以作为一个方括号内的逗号分隔值出现。**序列**也是Python中最基本的数据结构。**序列**中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是0，第二个索引是1，依此类推。

Python有6个序列的内置类型，但最常见的是列表和元组。序列都可以进行的操作包括索引，切片，加，乘，检查成员。列表的数据项不需要具有相同的类型

Python已经内置确定序列的长度以及确定最大和最小的元素的方法。

## 创建列表

创建一个列表，只要把逗号分隔的不同的数据项使用方括号括起来即可。

#### 练习：创建列表

```Python
list1 = ['Google', 'Python', 1997, 2000]; list2 = [1, 2, 3, 4, 5 ]; list3 = ["a", "b", "c", "d"];
print(list1)
print(list2)
print(list3)
```


与字符串的索引一样，列表索引从0开始。列表可以进行截取、组合等。

## 访问列表对象

使用下标索引来访问列表中的值，同样你也可以使用方括号的形式截取字符。

#### 练习:下标索引访问与切片访问列表对象

```Python
list1 = ['Google', 'Python', 1997, 2000];
list2 = [1, 2, 3, 4, 5, 6, 7 ];
 
print("list1[0]: ", list1[0])
print("list2[1:5]: ", list2[1:5])
```

## 更新列表

对列表的数据项进行修改或更新，可以使用`append()`方法来添加列表项。

#### 练习:更新列表

```Python
list = ['Google', 'Python', 1997, 2000]
 
print("第三个元素为 : ", list[2])
list[2] = 2001
print("更新后的第三个元素为 : ", list[2])
```

## 删除列表元素

可以使用`del`语句来删除列表的的元素。

#### 练习:删除列表元素

```Python
list = ['Google', 'Python', 1997, 2000]
 
print("原始列表 : ", list)
del list[2]
print("删除第三个元素 : ", list)
```

## Python列表脚本操作符

列表对`+` 和` *` 的操作符与字符串相似。`+ `号用于组合列表，`*` 号用于重复列表。

如下所示：

| Python 表达式                         | 结果                         | 描述                 |
| : | :--- | :- |
| `len([1, 2, 3])`                      | 3                            | 长度                 |
| `[1, 2, 3] + [4, 5, 6]`               | [1, 2, 3, 4, 5, 6]           | 组合                 |
| `['Hi!'] * 4`                         | ['Hi!', 'Hi!', 'Hi!', 'Hi!'] | 重复                 |
| `3 in [1, 2, 3]`                      | True                         | 元素是否存在于列表中 |
| `for x in [1, 2, 3]: print(x, end=" ")` | 1 2 3                        | 迭代                 |

## Python列表截取与拼接

#### 练习：Python的列表截取与字符串操作类型

```Python
L=['Google', 'Python', 'Taobao']
print(L[2])
print(L[-2])
print(L[1:])
```

| Python 表达式 | 结果                 | 描述                                               |
| : | :- | :- |
| L[2]          | 'Taobao'             | 读取第三个元素                                     |
| L[-2]         | 'Python'             | 从右侧开始读取倒数第二个元素: count from the right |
| L[1:]         | ['Python', 'Taobao'] | 输出从第二个元素开始后的所有元素                   |
#### 练习：列表拼接

```Python
squares = [1, 4, 9, 16, 25]
squares += [36, 49, 64, 81, 100]
squares
```

## 嵌套列表

使用嵌套列表即在列表里创建其它列表，

#### 练习:嵌套列表

```Python
a = ['a', 'b', 'c']
n = [1, 2, 3]
x = [a, n]
print(x)
print(x[0])
print(x[0][1])
```

## Python列表函数&方法

```Python
a = ['a', 'b', 'c']
dir(a)
```
<code class=backend-type backend-type=free></code>
<code class=gatsby-kernelname data-language=python></code>
<script type="text/javascript" src="https://cdn.freeaihub.com/asset/js/cell.js"></script>