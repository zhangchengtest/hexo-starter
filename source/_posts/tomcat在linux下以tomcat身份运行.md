title: tomcat在linux下以tomcat身份运行
date: 2016-05-11 16:54:17
tags:
---
title: tomcat在linux下以tomcat身份运行
tags:
---

参考链接

[http://blog.csdn.net/headman/article/details/24392463](http://blog.csdn.net/headman/article/details/24392463)

日志的输出为catalina-deamon.out
它不会做切割 会越来越大
可以参考链接
[http://www.bubuko.com/infodetail-603906.html](http://www.bubuko.com/infodetail-603906.html)

以上是以daemon方式运行 显然还是过于复杂
考链接
[http://www.davidghedini.com/pg/entry/install_tomcat_6_on_centos](http://www.davidghedini.com/pg/entry/install_tomcat_6_on_centos)

#将tomcat加入到linux服务中去
chkconfig --add tomcat 
chkconfig --del tomcat1 


chmod  -R 777 /home/tomcats/*/*/startup.sh 
chmod  -R 777 /home/tomcats/*/*/catalina.sh 
chmod  -R 777 /home/tomcats/*/*/shutdown.sh



