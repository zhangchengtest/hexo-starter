title: 安装maven
date: 2016-03-26 23:46:26
tags:
---
title: 安装maven
tags:
---

```bash
$ wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo 
$ yum -y install apache-maven
```

需要在/root/.m2/路径下建立settings.xml文件

源码安装
[http://www.darrenfang.com/2013/12/install-maven-on-centos/](http://www.darrenfang.com/2013/12/install-maven-on-centos/)
```bash
$ cd /usr/local/src
$ wget https://archive.apache.org/dist/maven/maven-3/3.2.5/binaries/apache-maven-3.2.5-bin.tar.gz
$ tar zxvf apache-maven-3.2.5-bin.tar.gz
$ mv apache-maven-3.2.5 /usr/local/maven3
$ cd /etc/profile.d
$ vi /maven.sh
```
```sh
export M2_HOME=/usr/local/maven3
export PATH=$PATH:$JAVA_HOME/bin:$M2_HOME/bin
```
```bash
$ source /etc/profile
$ mvn -v
```
see it is work

