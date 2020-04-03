---
title: "Redis命令"
meta_title: ''
meta_description: ''
keywords: 
    - redis
    - Redis命令
    - command
sidebar: "redis"
---
# Redis命令 			

Redis命令是用于在Redis服务器上执行一些操作。

要在Redis服务器上运行命令，需要一个Redis客户端。Redis客户端在Redis包中有提供，这个包在我们前面的安装教程中就有安装过了。

**语法**
以下是Redis客户端的基本语法。

```
redis-cli
```

**示例**
以下示例说明了如何启动Redis客户端。

要启动Redis客户端，请打开终端并键入命令`redis-cli`。 这将连接到您的本地Redis服务器，现在可以运行任何的Redis命令了。

```shell
redis-cli
```
```shell
ping
```

在上面的示例中，连接到到在本地机器上运行的Redis服务器并执行`PING`命令，该命令检查服务器是否正在运行。

## 在远程服务器上运行命令

要在Redis远程服务器上运行命令，需要通过客户端`redis-cli`连接到服务器

**语法**

```
redis-cli -h host -p port -a password
```

**示例**
以下示例显示如何连接到Redis远程服务器，在主机(host)`127.0.0.1`，端口(port)`6379`上运行，并使用密码为 `mypass`。

```shell
redis-cli -h 127.0.0.1 -p 6379
```

```shell
ping
```


<code class=backend-type backend-type=free></code>
