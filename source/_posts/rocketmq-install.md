title: rocketmq install
date: 2017-05-05 16:16:02
tags:
---
title: rocketmq install
tags:
---


reference
[http://blog.csdn.net/zknxx/article/details/52974189](http://blog.csdn.net/zknxx/article/details/52974189)

```
wget https://github.com/alibaba/RocketMQ/archive/v3.5.8.tar.gz

tar zxvf ....


sh install

mv alibaba-rocketmq-broker/alibaba-rocketmq/ /usr/local/


chmod -R 775 ./bin

vi runserver.sh 
vi runbroker.sh

JAVA_OPT="${JAVA_OPT} -server -Xms256m -Xmx256m -Xmn128m -XX:PermSize=128m -XX:MaxPermSize=320m"

 进入bin目录
   运行 nohup ./mqnamesrv -n 192.168.27.68:9876 & 启动nameserver服务。
   运行 nohup ./mqbroker -n 192.168.27.68:9876 启动broker服务
```

延迟等级

messageDelayLevel=1s 5s 10s 30s 1m 2m 3m 4m 5m 6m 7m 8m 9m 10m 20m 30m 1h 2h


rocketmq console install

git clone https://github.com/apache/incubator-rocketmq-externals.git
cd incubator-rocketmq-externals
cd rocketmq-console
mvn clean package -Dmaven.test.skip=true

start
java -jar rocketmq-console-ng-1.0.0.jar

8080端口访问