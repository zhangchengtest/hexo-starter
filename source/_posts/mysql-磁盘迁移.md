title: mysql 磁盘迁移
date: 2017-06-12 15:32:51
tags:
---
title: mysql 磁盘迁移
tags:
---

reference [http://blog.csdn.net/submorino/article/details/46411597](http://blog.csdn.net/submorino/article/details/46411597)

service mysqld stop

sudo mv /var/lib/mysql/ /ROOT/

sudo ln -s /ROOT/mysql /var/lib/

sudo chown -R mysql:mysql /ROOT/mysql/

sudo service mysqld start