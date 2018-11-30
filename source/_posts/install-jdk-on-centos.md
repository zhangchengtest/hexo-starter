title: install jdk on centos
date: 2016-05-13 16:08:01
tags:
---
title: install jdk on centos
date: 2016-05-13 16:08:01
tags:
---

rpm -qa | grep java 

rpm -e  java-1.7.0-openjdk-1.7.0.45-2.4.3.3.el6.x86_64 --nodeps
rpm -e --nodeps tzdata-java-2013g-1.el6.noarch 
rpm -e --nodeps java-1.6.0-openjdk-1.6.0.0-1.66.1.13.0.el6.x86_64 


mkdir /usr/java 

cp /home/data/jdk-7u79-linux-x64.rpm  /usr/java/ 

```bash
$ mkdir /usr/java
$ wget --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie;" http://download.oracle.com/otn-pub/java/jdk/7u79-b15/jdk-7u79-linux-x64.rpm
$ rpm -ivh jdk-7u79-linux-x64.rpm rpm
```
在profile.d下面加一个jdk.sh 其中加入一下内容
```sh
export JAVA_HOME=/usr/java/jdk1.7.0_79 
export CLASSPATH=.:$JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar 
export PATH=$PATH:$JAVA_HOME/bin 
```
```bash
source /etc/profile
```
有些软件需要jdk8 这是没办法了

```bash
$  wget --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie;" http://download.oracle.com/otn-pub/java/jdk/8u91-b14/jdk-8u91-linux-x64.rpm
```