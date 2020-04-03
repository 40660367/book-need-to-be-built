# Redis环境安装配置 			

在本章中，您将了解和学习Redis的环境安装设置。

## 在Ubuntu上安装Redis

要在Ubuntu上安装Redis，打开终端并键入以下命令 -

```shell
apt-get update && apt-get install redis-server -y
```

这将在Ubuntu机器上安装Redis。

**启动redis**

```shell
#加&是让redis-server运行在后台，按enter按后，即可不阻塞当前终端。
redis-server &
```

**使用redis自带客户自带客户端连接Redis-server**

```shell
redis-cli
```

这将打开一个**redis**提示，如下所示 - 

```
127.0.0.1:6379>
```

在上面的提示中，`127.0.0.1`是计算机的IP地址，`6379`是运行**Redis**服务器的默认端口。 现在键入以下`PING`命令。

```shell
ping
```
如返回为`PONG`

这表明**Redis**已在当前学习环境成功安装运行，并返回了客户端的请求。

### 在Ubuntu上安装**Redis桌面管理**

要在Ubuntu上安装**Redis**桌面管理器，可从 http://redisdesktop.com/download 下载该软件包，安装即可。