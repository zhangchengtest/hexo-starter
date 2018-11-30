title: aws mount block
date: 2016-05-24 17:23:17
tags:
---
title: aws mount block
tags:
---

reference link
[http://www.51ou.com/browse/xitongguanli/57802.html](http://www.51ou.com/browse/xitongguanli/57802.html)


创建volume 要注意是在实例的那个区
attach 到实例

注意他的警告信息， 一般默认的linux系统，
硬盘的显示都是 sda, sdf等等,
但是EC2的Linux AMI里面做了一个Symlink的映射，
表面看起来也是这样，但是真正的名字是 xvda，xvdf

我们执行  sudo fdisk -l 来查看加载后的磁盘， 
看见木有，真正的名字是xvda1和  xvdf


格式化
```sh
$sudo mkfs -t ext4 /dev/xvdf
```
挂在到某个文件夹
```sh
$sudo mkdir /ROOT
$sudo mount /dev/xvdf /ROOT
```

不过如果重启服务器，加载的硬盘就没了，所以我们还需要修改fstab文件，保证每次启动的时候都会自动加载这个新硬盘
```sh
$ sudo vi /etc/fstab
```
```shell
/dev/xvdf   /ROOT       ext4    defaults        0   0
```
先卸载
```shell
$ sudo umount /dev/xvdf
$ sudo df -h
```
再测试
```shell
$sudo mount -a
$ sudo df -h
```