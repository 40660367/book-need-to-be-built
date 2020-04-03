---
title: "如何学习本课程  - FreeAIHub"
meta_title: ''
meta_description: ''
keywords: 
    - python3
    - 如何学习本课程 
    - index
sidebar: "python3"
permalink: "/python3/index.html"
---
# 如何学习本课程

## 课程信息
- 课程名称：《动手学Python》
- 课程编号：B3
- 所处层次：基础课程(B Level)
- 所需基础：无
- 学习周期：4周（以每天投入2小时左右时间进行学习估算）
- 学习形式：在线互动性学习，课程分为基础，应用和实战三个阶段。按顺序进行即可。
- 面向群体：想学习Python基础，并进行Python相关扩展，如机器学习，web开发的同学。
- 效果考核：能独立完成实战阶段作业
- 学习成果：对数据科学方向所需求的Python基础掌握，不扩展到Python Web等非AI领域
- 学习目的：为将来的Python数据科学方向（如可视化，各类机器学习包）打下语言基础

## 如何使用本课程

### 关于用户环境

该课程为每位浏览用户提供独立的在线学习环境，用户可安全，高效地进行学习。

本课程的后端是基于Jupyter Notebook构建的。

**说明：环境不保留用户任何个人数据，为安全考虑也请勿放置任何含有个人信息的敏感数据。**

### 关于代码框

本课程中的代码均可在线运行，帮助您提升学习效率。

**Python在线运行的简单示例**

```Python
#从Python中导入并显示Python之禅
import this
```

**注意**：代码框的执行请一定要按顺序执行。

### 关于代码框输出结果不全的问题：

通常当您需要在同一个代码框中输出多个结果时，代码框默认只返回最后一个结果。

如在执行下列代码框，通常会只有最后一行`2 /4 `的结果`0.5`输出。

```Python
5 + 4  # 加法
4.3 - 2 # 减法
3 * 7  # 乘法
2 / 4  # 除法，得到一个浮点数
```

**解决办法：**

- 使用`print()`函数将输出结果进行打印

- 使用魔法函数`%config ZMQInteractiveShell.ast_node_interactivity='all'`后，强制代码框返回所有的结果。

```Python
%config ZMQInteractiveShell.ast_node_interactivity='all'
```

```Python
5 + 4  # 加法
4.3 - 2 # 减法
3 * 7  # 乘法
2 / 4  # 除法，得到一个浮点数
```

### 关于魔法函数%

`%`开头的为魔法函数的标志，常用于执行普通Python代码不太方便执行的操作，如`%%writefile hello.py`为把代码框中的内容写入至文件`hello.py`这个文件中。``%%time``为计时该代码框运行时间。

```Python
%%writefile hello.py
print('Hello,Python')
```

`!`为调用操作系统命令的标志，如`!ls`为列出当前目录下所有的文件,`!pwd`为列出当前路径，`!python`为调用Python

使用`!ls`调用`ls`命令查看上一个代码框写入的文件

```Python
!ls
```

使用`!cat调用`cat`命令查看上一个代码框写入的文件的内容

```Python
!cat hello.py
```

使用`!python`调用`python`来执行这个文件

```Python
!python hello.py
```

关于更多的魔法函数可自行百度。

### 学习中其它常见问题

如果您在使用过程中遇到问题，请点击页面最底部的使用帮助，常见问题在那里均可得到解决。

如果还是没有解决，请加在线客服群，我们将尽快为您解决。

### 本课程专用微信学习交流群 

如果您还有学习过程中需要有交流，困惑，请加入下方互动学习微信群

![IR](./images/python-wechat.jpg)

### 相关资料推荐

| 类别     | 名称    |
| -- |   ---- |
| 视频     | [零基础入门学习Python](https://www.bilibili.com/video/av4050443) |
| 视频     | [黑马_600集Python从入门到精通教程](https://www.bilibili.com/video/av14184325) |
| 书籍     | [Python编程 从入门到实践](https://item.jd.com/11993134.html) |

## 使用协议

本课程为完全免费，内容为网络整理。

浏览本课程即视为同意相关用户使用协议。
<code class=backend-type backend-type=free></code>
<code class=gatsby-kernelname data-language=python></code>
<script type="text/javascript" src="https://cdn.freeaihub.com/asset/js/cell.js"></script>
