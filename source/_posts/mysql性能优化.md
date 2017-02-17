---
title: mysql性能优化基础篇
date: 2017-01-25 11:47
tags: mysql
---

在高i/o的系统中，数据库的性能往往是系统的瓶颈，但mysql的运行环境复杂，运行状况各异，所以，简单的依照网上的优化方法有时候并不能达到理想的效果

### 列出mysql服务器运行状态

```
mysql> show global status;
```

### 列出mysql服务器配置信息

```
mysql> show variables;
```

### 查看满查询配置信息

```
mysql> show variables like 'slow%';
```

### 列出慢查询语句

```
mysql> show global status like 'slow%';
```
