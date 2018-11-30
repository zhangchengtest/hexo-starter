title: mysql 慢查询
date: 2016-10-31 17:27:29
tags:
---
title: mysql 慢查询
tags:
---
add this in your /etc/my.cnf

```sql

log-slow-queries=/var/lib/mysql/slowquery.log
long_query_time=2

```
reference link
[http://blog.csdn.net/haiqiao_2010/article/details/25138099](http://blog.csdn.net/haiqiao_2010/article/details/25138099)