title: activemq install
date: 2017-05-04 17:01:30
tags:
---
title: activemq install
tags:
---


reference 
[http://chenzhou123520.iteye.com/blog/1915287](http://chenzhou123520.iteye.com/blog/1915287)


[http://forum.spring.io/forum/spring-projects/integration/104004-spring-integration-and-activemq-s-amq-scheduled-delay-property](http://forum.spring.io/forum/spring-projects/integration/104004-spring-integration-and-activemq-s-amq-scheduled-delay-property)
```

wget http://html.zhangcheng.club/apache-activemq-5.14.5-bin.tar.gz

cd /usr/local/apache-activemq-5.8.0/bin  
chmod 775 activemq  

bin/activemq setup ~/.activemqrc


nohup bin/activemq start > /tmp/smlog 2>&1 &  

if start have problem run command below to see the problem
 ./activemq console 
 
 user and password
 
 admin admin
 
 
 


```

```

netstat -an|grep 5672
lsof -i:5672
kill -9 
```
