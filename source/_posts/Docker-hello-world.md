title: Docker hello world
date: 2016-03-27 18:56:09
tags:
---
title: Docker hello world
tags:
---
参考链接

[http://cloud.51cto.com/art/201412/460142.htm](http://cloud.51cto.com/art/201412/460142.htm)

[http://stackoverflow.com/questions/27216473/docker-1-3-fails-to-start-on-rhel6-5](http://stackoverflow.com/questions/27216473/docker-1-3-fails-to-start-on-rhel6-5)
需要跑
```bash
$ yum update -y device-mapper-libs
$ docker -d
```
才能成功
```bash
$ service start docker
```
登录

```bash
$ docker login --username=xxx --password=xxxx --email=xxxxx
$
```
[http://dockone.io/](http://dockone.io/)
[http://blog.csdn.net/we_shell/article/details/38445979](http://blog.csdn.net/we_shell/article/details/38445979)
[http://www.jb51.net/LINUXjishu/333176.html](http://www.jb51.net/LINUXjishu/333176.html)
[http://www.dev-garden.org/2014/12/27/setting-up-a-docker-container-with-centos6-and-tomcat7/](http://www.dev-garden.org/2014/12/27/setting-up-a-docker-container-with-centos6-and-tomcat7/)
[http://www.csdn.net/article/2015-07-21/2825266](http://www.csdn.net/article/2015-07-21/2825266)
[https://docs.docker.com/mac/step_six/](https://docs.docker.com/mac/step_six/)
[https://docs.docker.com/engine/reference/commandline/build/](https://docs.docker.com/engine/reference/commandline/build/)
更新docker-engine 1.91就好 不要docker-latest, docker都起不来了

```bash
$ yum -y update docker-io
$ wget https://get.docker.com/builds/Linux/x86_64/docker-1.91 -O /usr/bin/docker
```


```bash
$ docker run -d -p 5000:5000 --name registry registry
$ docker tag <image>  127.0.0.1:5000/<image>
$ docker push 127.0.0.1:5000/<image>
```
install docker-compose

[https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)

[http://www.mamicode.com/info-detail-847142.html](http://www.mamicode.com/info-detail-847142.html)

[http://www.pangxie.space/docker/364](http://www.pangxie.space/docker/364)