title: zookeeper
date: 2018-01-16 10:00:21
tags:
---
title: zookeeper
tags:
---

download link
[http://www.apache.org/dyn/closer.cgi/zookeeper](http://www.apache.org/dyn/closer.cgi/zookeeper)


在“conf”目录下，新建一个名为“zoo.cfg”的文件，其中内容如下：

tickTime=2000  
dataDir= /data/zookeeper/data
dataLogDir=/data/zookeeper/logs  
clientPort=2181

然后
./bin/zkServer.sh start