---
title: "Pyhon3 环境搭建及运行 - FreeAIHub"
meta_title: ''
meta_description: ''
keywords: 
    - python3
    - Pyhon3 环境搭建及运行
    - setup
sidebar: "python3"
permalink: "/python3/setup.html"
---
# Pyhon3环境搭建及运行

### 搭建编程环境

#### Windows环境

可以在[Python官方网站](https://www.python.org)下载到Python的Windows安装程序（exe文件），需要注意的是如果在Windows 7环境下安装Python 3.x，需要先安装Service Pack 1补丁包（可以通过一些工具软件自动安装系统补丁的功能来安装），安装过程建议勾选“Add Python 3.6 to PATH”（将Python 3.6添加到PATH环境变量）并选择自定义安装，在设置“Optional Features”界面最好将“pip”、“tcl/tk”、“Python test suite”等项全部勾选上。强烈建议使用自定义的安装路径并保证路径中没有中文。安装完成会看到“Setup was successful”的提示。如果稍后运行Python程序时，出现因为缺失一些动态链接库文件而导致Python解释器无法工作的问题，可以按照后面说的方法加以解决。如果系统显示api-ms-win-crt\*.dll文件缺失，可以参照[《api-ms-win-crt\*.dll缺失原因分析和解决方法》]()一文讲解的方法进行处理或者直接在[微软官网](https://www.microsoft.com/zh-cn/download/details.aspx?id=48145)下载Visual C++ Redistributable for Visual Studio 2015文件进行修复；如果是因为更新Windows的DirectX之后导致某些动态链接库文件缺失问题，可以下载一个DirectX修复工具进行修复。

#### Linux环境

Linux环境自带了Python 2.x版本，但是如果要更新到3.x的版本，可以在[Python的官方网站](https://www.python.org)下载Python的源代码并通过源代码构建安装的方式进行安装，具体的步骤如下所示。

安装依赖库（因为没有这些依赖库可能在源代码构件安装时因为缺失底层依赖库而失败）。

`yum -y install wget gcc zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel libffi-devel`

下载Python源代码并解压缩到指定目录。

>wget https://www.python.org/ftp/python/3.7.3/Python-3.7.3.tgz
>xz -d Python-3.7.3.tar.xz
>tar -xvf Python-3.7.3.tar


切换至Python源代码目录并执行下面的命令进行配置和安装。

>cd Python-3.7.3
>./configure --prefix=/usr/local/python37 --enable-optimizations
>make && make install

修改用户主目录下名为.bash_profile的文件，配置PATH环境变量并使其生效。
>cd ~
>vim .bash_profile


>export PATH=$PATH:/usr/local/python37/bin
>source .bash_profile


#### macOS环境

macOS也自带了Python 2.x版本，可以通过[Python的官网](https://www.python.org)提供的安装文件（pkg文件）安装Python 3.x的版本。默认安装完成后，可以通过在终端执行python命令来启动2.x版本的Python解释器，可以通过执行python3命令来启动3.x版本的Python解释器。

## 其他工具介绍

### IDLE - 自带的集成开发工具

IDLE是安装Python环境时自带的集成开发工具，如下图所示。但是由于IDLE的用户体验并不是那么好所以很少在实际开发中被采用。

### Jupyter Notebook - 更好的交互式编程工具

当然，我们可以通过安装Jupyter工具并运行名为notebook的程序在浏览器窗口中进行交互式代码编写操作。

`pip install jupyter`，然后执行`jupyter notebook`。实际上本课程的后端也是基于Jupyter Notebook构建的。

## 交互式运行Python程序

在您本地环境的命令行后，输入python或python3进入Python交互式环境。

在《动手学Python》课程网页上已经默认进入交互式环境。

#### 练习确认Python的版本

```Python
import sys

print(sys.version_info)
print(sys.version)
```

### 解释式运行Python程序 

#### 练习：在命令行确认Python的版本

```Shell
!python --version
```

#### 练习：使用Python帮助

```Python
!python -h
```

#### 练习：编写并运行Python源码

可以用文本编辑工具（如使用VS Code）编写Python源代码并用py作为后缀名保存文件。

也可以在《动手学Python》课程网页上直接将源码写入文件。

```Python
%%writefile hello.py
print('hello, Python!')
```
使用`!cat`查看刚刚写入的文件的内容

```Python
!cat hello.py
```

执行Python源码。看看是否输出了"hello, Python!"。

```Python
!python hello.py
```



<code class=backend-type backend-type=free></code>
<code class=gatsby-kernelname data-language=python></code>
<script type="text/javascript" src="https://cdn.freeaihub.com/asset/js/cell.js"></script>
