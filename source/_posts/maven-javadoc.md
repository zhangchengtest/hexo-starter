title: maven javadoc
date: 2016-05-23 11:52:53
tags:
---
title: maven javadoc
tags:
---

reference link
[http://blog.csdn.net/jianxin1009/article/details/35269501](http://blog.csdn.net/jianxin1009/article/details/35269501)

```
$mvn javadoc:javadoc
```
多模块 输出到一个模块里

<plugin>  
    <groupId>org.apache.maven.plugins</groupId>  
    <artifactId>maven-javadoc-plugin</artifactId>  
    <version>2.9.1</version>  
    <configuration>  
        <aggregate>true</aggregate>  
    </configuration>  
</plugin>  
