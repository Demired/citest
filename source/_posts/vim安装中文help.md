---
title: vim安装中文help
date: 2017-02-17 14:15:00
tags: vim
categories: 技术
description: vim自带的帮助手册是英文的，对平时敲代码的同学来说使用起来难度不大，即使遇到不会的单词，也可以借助翻译软件来理解，不失为一个学习英文的好机会
---

vim自带的帮助手册是英文的，对平时敲代码的同学来说使用起来难度不大，即使遇到不会的单词，也可以借助翻译软件来理解，不失为一个学习英文的好机会

但是如果是为了工作，我建议还是安装一个sourceforge上的中文help比较稳妥

### 简介

Vimcdoc is an attempt to translate the wonderful Vim online documentation into Chinese, allowing more people to get to know and make use of this great tool. After installing vimcdoc, You will be able to do :help and read documentation in Chinese.

### 下载

下载地址：

[http://vimcdoc.sourceforge.net/](http://vimcdoc.sourceforge.net/)

根据使用的操作系统选择对应的版本

### 解压

```
tar -xzvf vimcdoc-1.9.0.tar.gz
```

### 目录结构

```
AUTHORS		LICENSE		VERSION		guides.txt	vimcdoc.vim
ChangeLog	README		dict.txt	help_cn.vim
INSTALL		TODO		doc		vimcdoc.sh
```
### 安装

在目录下有一个vimcdoc.sh文件，打开注释便可看到，脚本介绍，使用方法和作者信息

```
vimcdoc.sh: vimcdoc Linux install/uninstall script

Usage: (run it as root)
    './vimcdoc.sh -i' to install vimcdoc and set helplang
    './vimcdoc.sh -I' to install vimcdoc only
    './vimcdoc.sh -u' to uninstall vimcdoc
Author: wandys	(wandys@users.sf.net)
        lang2	(lang2@users.sf.net)
```

### 测试

开个新终端，在vim输入:help

（完）
