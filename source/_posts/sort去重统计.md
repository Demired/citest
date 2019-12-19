---
title: sort去重统计
date: 2017-05-14 11:21:27
tags: 英语
categories: 常识
description: sort用法记录
---

# sort

## 去除重复

```
sort file |uniq
```
 
## 查找非重复

```
sort file | uniq -u
```

## 查找重复

```
sort file | uniq -d
```

## 统计

```
sort file | uniq -c
```
