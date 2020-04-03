---
title: "R语言平均值，中位数和模式"
meta_title: ''
meta_description: ''
keywords: 
    - r
    - R语言平均值，中位数和模式
    - mean-median-mode
sidebar: "r"
---
# R语言平均值，中位数和模式

R中的统计分析通过使用许多内置函数来执行。 这些函数大多数是R基础包的一部分。 这些函数将R向量作为输入和参数，并给出结果。

我们在本章中讨论的功能是平均值，中位数和模式。

## Mean平均值

通过求出数据集的和再除以求和数的总量得到平均值

函数`mean()`用于在R语言中计算平均值。

### 语法

用于计算R中的平均值的基本语法是 `mean(x, trim = 0, na.rm = FALSE, ...)`

以下是所使用的参数的描述 - 

- **x**是输入向量。
- **trim**用于从排序向量的两端丢弃一些观察结果。
- **na.rm**用于从输入向量中删除缺失值。

#### 练习：

```R
# Create a vector. 
x <- c(12,7,3,4.2,18,2,54,-21,8,-5)

# Find Mean.
result.mean <- mean(x)
print(result.mean)
```

## 应用修剪选项

当提供trim参数时，向量中的值被排序，然后从计算平均值中减去所需的观察值。

当trim = 0.3时，来自每端的3个值将从计算中减去以找到均值。

在这种情况下，排序的向量是（-21，-5,2,3,4.2,7,8,12,18,54），并且从用于计算平均值的向量中移除的值是（-21，-5,2） 从左边和（12,18,54）从右边。

#### 练习：应用修剪选项

```R
# Create a vector.
x <- c(12,7,3,4.2,18,2,54,-21,8,-5)

# Find Mean.
result.mean <-  mean(x,trim = 0.3)
print(result.mean)
```

## 应用NA选项

如果有缺失值，则平均函数返回NA。

要从计算中删除缺少的值，请使用na.rm = TRUE。 这意味着去除NA值。

#### 练习：应用NA选项

```R
# Create a vector. 
x <- c(12,7,3,4.2,18,2,54,-21,8,-5,NA)

# Find mean.
result.mean <-  mean(x)
print(result.mean)

# Find mean dropping NA values.
result.mean <-  mean(x,na.rm = TRUE)
print(result.mean)
```

## Median中位数
数据系列中的最中间值称为中值。 在R语言中使用`median()`函数来计算此值。

### 语法

计算R语言中位数的基本语法是:`median(x, na.rm = FALSE)`

以下是所使用的参数的描述 - 

- **x**是输入向量。
- **na.rm**用于从输入向量中删除缺失值。

#### 练习：应用NA选项

```R
# Create the vector.
x <- c(12,7,3,4.2,18,2,54,-21,8,-5)

# Find the median.
median.result <- median(x)
print(median.result)
```

## Mode模式

模式是一组数据中出现次数最多的值。 Unike平均值和中位数，模式可以同时包含数字和字符数据。

R语言没有标准的内置函数来计算模式。 因此，我们创建一个用户函数来计算R语言中的数据集的模式。该函数将向量作为输入，并将模式值作为输出。

#### 练习：Mode模式

```R
# Create the function.
getmode <- function(v) {
   uniqv <- unique(v)
   uniqv[which.max(tabulate(match(v, uniqv)))]
}

# Create the vector with numbers.
v <- c(2,1,2,3,1,2,3,4,1,5,5,3,2,3)

# Calculate the mode using the user function.
result <- getmode(v)
print(result)

# Create the vector with characters.
charv <- c("o","it","the","it","it")

# Calculate the mode using the user function.
result <- getmode(charv)
print(result)
```

<code class=backend-type backend-type=free></code>
<code class=gatsby-kernelname data-language=r></code>
<script type="text/javascript" src="https://cdn.freeaihub.com/asset/js/cell.js"></script>
