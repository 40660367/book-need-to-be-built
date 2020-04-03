---
title: "导入MySQL示例数据库"
meta_title: ''
meta_description: ''
keywords: 
    - mysql
    - 导入MySQL示例数据库
    - import-sample-database
sidebar: "mysql"
---
# 导入MySQL示例数据库		

在本MySQL教程中，大部分操作是基于`classicmodels`这个数据库作为学习MySQL示例数据库，这样的话有助于您快速有效地使用MySQL。`classicmodels`数据库是一个典型汽车零售商数据库模型。它包含典型的业务数据，如客户，产品，销售订单，销售订单等。

我们在MySQL教程中使用此示例数据库来演示从简单查询到复杂存储过程的许多MySQL功能。

```shell
#用户名默认为root,密码为空，登陆本地MySQL
mysql
```

```shell
#创建一个空的数据库并使用它
CREATE DATABASE IF NOT EXISTS classicmodels DEFAULT CHARSET utf8;
USE classicmodels;
```


```shell
#导入数据
source /share/datasets/mysql-classicmodels.sql;
```

```shell
#查询导入数据库classicmodels中的表offices
select city,phone,country from `offices`;
```

上面语句首先将当前数据库切换到`classicmodels`数据库下，并从`office`表查询数据。

如果您看到返回的客户数据，说明已成功将示例数据库(`classicmodels`)导入MySQL数据库服务器了。

## MySQL示例数据库结构

MySQL示例数据库模式由以下表组成：

- `customers`: 存储客户的数据。
- `products`: 存储汽车的数据。
- `productLines`: 存储产品类别数据。
- `orders`: 存储客户订购的销售订单。
- `orderDetails`: 存储每个销售订单的订单产品数据项。
- `payments`: 存储客户订单的付款数据信息。
- `employees`: 存储所有员工信息以及组织结构，例如，直接上级(谁向谁报告工作)。
- `offices`: 存储销售处数据，类似于各个分公司。

表与表之间的关系，请参考以下ER图 - 

![img](./images/sample.png)
<code class=backend-type backend-type=free></code>
