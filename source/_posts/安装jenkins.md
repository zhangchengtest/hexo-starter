title: 安装jenkins
date: 2016-03-26 20:14:02
tags:
---
title: 安装jenkins
tags:
---

```bash
$ wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo 
$ rpm --import http://pkg.jenkins-ci.org/redhat/jenkins-ci.org.key
$ yum install jenkins

```
配置权限
![Imgur](http://i.imgur.com/Ddm5Wh4.png?1)
当注册后
![Imgur](http://i.imgur.com/1GvbJHj.png?1)

如果需要用到maven 请先安装maven
如果在jenkins中使用的默认的maven配置，jenkins需要以root用户启动
[http://www.php230.com/jenkins-modify-default-user.html](http://www.php230.com/jenkins-modify-default-user.html)
不然找不到maven配置文件，因为maven的配置文件在/root/.m2/下

如果项目使用github或者bitbucket
需要安装git插件
如果不能下载代码 可能需要升级git版本
[http://www.tuicool.com/articles/7buQNv](http://www.tuicool.com/articles/7buQNv)

如果需要远程部署，请安装Publish Over SSH


jenkins home 默认路径
/var/lib/jenkins
配置文件config.xml

useSecurity节点代表是否使用用户权限
authorizationStrategy节点代表用户权限
删除即可重新配置