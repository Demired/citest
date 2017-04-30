---
title: 用阿里云镜像给Docker加速
date: 2017-04-27 10:59:27
tags: docker
categories: 技术
description: 深陷高墙，看我如何从容面对
---

[docker hub](https://hub.docker.com)远在高墙之外，即使身处硅谷第二，镜像拉去速度也实在不敢恭维，不过国内云计算公司都提供了简单的解决方案，个人比较偏爱阿里云的服务，在阿里云官方文档中并没有提供针 dokcer for mac 设置镜像加速的方法，下面是设置方法

# 获取加速地址

[https://cr.console.aliyun.com/#/accelerator](https://cr.console.aliyun.com/#/accelerator)

# Mac

docker mac版有两个版本，mac os 10.10.3之后都可以使用Docker for Mac，之前的Docker Toolbox用起来很不习惯

## Docker for Mac

状态栏左键docker

Docker - Preferences - Daemon - Basic - Registry mirrors

粘贴你的个人专属地址

Apply & Restart

## Docker Tookbox

打开终端

创建一个装有docker服务的linux虚拟机，命名为default
```
docker-machine create --engine-registry-mirror={专属地址} -d virtualbox default
```
将虚拟机的配置拷贝一份到本地
```
docker-machine env default
eval "$(docker-machine env default)"
docker info
```

# Windows

同mac

# Linux

配置文件地址/etc/docker/daemon.json

```
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://lnurb9cf.mirror.aliyuncs.com"]
}
EOF
sudo systemctl daemon-reload
sudo systemctl restart docker
```
