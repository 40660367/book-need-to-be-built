---
title: "Redis性能测试"
meta_title: ''
meta_description: ''
keywords: 
    - redis
    - Redis性能测试
    - benchmark
sidebar: "redis"
---
# Redis基准 			

Redis基准测试是通过同时运行`n`个命令来检查Redis的性能的实用程序。

## 语法

以下是基准测试命令的基本语法。

```
redis-benchmark [option] [option value]
```

## 示例

以下示例通过调用`100000`个命令检查Redis。

```
redis-server &
```

```shell
redis-benchmark -n 100000  
```

以下是Redis基准测试中可用选项的列表。

| 序号 | 选项    | 说明                                     | 默认值    |
| ---- | ------- | ---------------------------------------- | --------- |
| 1    | `-h`    | 指定服务器主机名                         | 127.0.0.1 |
| 2    | `-p`    | 指定服务器端口                           | 6379      |
| 3    | `-s`    | 指定服务器套接字                         |           |
| 4    | `-c`    | 指定并行连接的数量                       | 50        |
| 5    | `-n`    | 指定请求的总数                           | 10000     |
| 6    | `-d`    | 指定`SET/GET`值的数据大小(以字节为单位)  | 2         |
| 7    | `-k`    | 1=keep alive, 0=reconnect                | 1         |
| 8    | `-r`    | 使用`SET/GET/INCR`的随机键，SADD的随机值 |           |
| 9    | `-p`    | 管道``请求                               | 1         |
| 10   | `-h`    | 指定服务器主机名                         |           |
| 11   | `-q`    | 强制让Redis安装。 只显示`query/sec`值    |           |
| 12   | `--csv` | 以CSV格式输出                            |           |
| 13   | `-l`    | 生成循环，永久运行测试                   |           |
| 14   | `-t`    | 只运行逗号分隔的测试列表                 |           |
| 15   | `-I`    | 空闲模式。 只打开N个空闲连接并等待       |           |

## 示例

下面的示例显示了Redis基准实用程序中多个选项的使用。

```shell
redis-benchmark -h 127.0.0.1 -p 6379 -t set,lpush -n 100000 -q  
```
<code class=backend-type backend-type=free></code>
