title: php install in centos6
date: 2016-04-07 09:19:17
tags:
---
title: php install in centos6
tags:
---

参考链接
[http://www.blogjava.net/nkjava/archive/2015/01/20/422289.html](http://www.blogjava.net/nkjava/archive/2015/01/20/422289.html)

检查是否已经安装， 如果有删除
```bash
$ yum list installed | grep php
$ yum remove
```
安装源
```bash
$ rpm -Uvh http://mirror.webtatic.com/yum/el6/latest.rpm
```
安装php5.6
```bash
$ yum install php56w.x86_64 php56w-cli.x86_64 php56w-common.x86_64 php56w-gd.x86_64 php56w-ldap.x86_64 php56w-mbstring.x86_64 php56w-mcrypt.x86_64 php56w-mysql.x86_64 php56w-pdo.x86_64
```
安装php fpm
```bash
$ yum install php56w-fpm 
```
启动fpm
```bash
$ cd /etc/init.d
$ ./php-fpm start
```

2.源码安装
更加好升级



