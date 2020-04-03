---
title: "MySQL"
meta_title: ''
meta_description: ''
keywords: 
    - mysql
    - MySQL
    - setup
sidebar: "mysql"
---
# MySQL安装与连接

## MySQL 安装

所有平台的 Mysql 下载地址为： [MySQL 下载](https://www.mysql.com/cn/downloads/). 挑选你需要的 MySQL Community Server 版本及对应的平台。

> **注意：**安装过程我们需要通过开启管理员权限来安装，否则会由于权限不足导致无法安装。

### Linux / UNIX 上安装 MySQL

Linux 平台上推荐使用 RPM 包来安装 MySQL ，MySQL  提供了以下包的下载地址：

- **MySQL** - MySQL 服务器。如果不是只想连接运行在另一台机器上的 MySQL 服务器，请你选择该选项。
- **MySQL-client** - MySQL 客户端程序，用于连接并操作 Mysql 服务器。
- **MySQL-devel** - 库和包含文件，如果你想要编译其它如 Perl 模块等 MySQL 客户端，则需要安装该 RPM 包。
- **MySQL-shared** - 该软件包包含某些语言和应用程序需要动态装载的共享库(libmysqlclient.so*)，使用 MySQL。
- **MySQL-bench** - MySQL 数据库服务器的基准和性能测试工具。

以下安装 MySQL RMP 的实例是在 SuSE Linux 系统上进行，当然该安装步骤也适合应用于其他支持 RPM 的 Linux 系统，如: CentOS,Ubuntu

### Linux上安装MySQL 安装步骤(On Ubuntu)：

在右侧实验区,通过以下命令执行 MySQL安装

```shell
apt install mysql-server -y
```

以上安装MySQL服务器的过程会创建MySQL用户`root`，默认密码为空。

并创建一个MySQL配置文件`mysqld.cnf`，位于`/etc/mysql/mysql.conf.d/`

你可以在`/usr/bin`中找到所有与MySQL相关的二进制文件。

所有数据表和数据库将在`/var/lib/mysql`目录中创建。

### 验证MySQL安装

在成功安装MySQL后，一些基础表会表初始化，在服务器启动后，你可以通过简单的测试来验证MySQL是否工作正常。

使用 mysqladmin 工具来获取服务器状态：

使用 mysqladmin 命令俩检查服务器的版本,在linux上该二进制文件位于`/usr/bin/`

```shell
mysqladmin --version
```

linux上该命令将输出以下结果，该结果基于你的系统信息：

```
mysqladmin  Ver 8.42 Distrib 5.7.29, for Linux on x86_64
```

如果以上命令执行后未输入任何信息，说明你的MySQL未安装成功。

## 启动及关闭 MySQL 服务

首先，我们需要通过以下命令来检查MySQL服务器是否启动：

```shell
service mysql status
```

如果MySQL已经启动，以上命令将输出MySQL服务的状态。

如果MySQL未启动，你可以使用以下命令来启动MySQL服务器:

```shell
service mysql start
```

如果你想关闭目前运行的 MySQL 服务, 你可以执行以下命令:

```shell
service mysql stop 
```

## 使用MySQL客户端方式连接

您可以使用MySQL二进制方式进入到MySQL命令提示符下来连接MySQL数据库。

### 实例

以下是从命令行中连接MySQL服务器的简单实例：-u参数后边代表进行连接的用户是`root`，-p代表该用户的密码。默认为空

```Shell
mysql -u root -p
```

在出现 `Enter password: `直接按回车，即会出现 

```
Your MySQL connection id is 1
Server version: 5.7.29-0ubuntu0.18.04.1 (Ubuntu)

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> 
```

在登录成功后会出现 `mysql>` 命令提示窗口，你可以在上面执行任何 SQL 语句。

这说明你已经成功连接到 MySQL 服务器上，你可以在` mysql > `提示符后执行MySQL 命令,例如下方命令，来查询目前MySQL服务上存在的数据库。

在以上实例中，我们使用了root用户登录到MySQL服务器，当然你也可以使用其他MySQL用户登录。

如果用户权限足够，任何用户都可以在MySQL的命令提示窗口中进行SQL操作。

退出 `mysql>` 命令提示窗口可以使用 `exit` 命令，如下所示：

```Shell
exit
```

## 使用MySQL客户端 执行简单的SQL命令

你可以在 MySQL Client(MySQL客户端) 使用 MySQL 命令连接到MySQL服务器上

在上边的默认安装下，MySQL服务器的密码为空，所以本实例不需要输入密码。

```
mysql
```

```
SHOW DATABASES;
```


会出现 

```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0.00 sec)
```


<code class=backend-type backend-type=free></code>
