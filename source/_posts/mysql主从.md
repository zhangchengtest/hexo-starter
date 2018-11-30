title: mysql主从
date: 2016-05-20 14:21:01
tags:
---
title: mysql主从
tags:
---

参考链接
[http://www.linuxidc.com/Linux/2014-06/103752.htm](http://www.linuxidc.com/Linux/2014-06/103752.htm)

master
```bash
show master status
```

修改my.cnf(主)
```file
log-bin 
 
server-id=1 
binlog-do-db=haze
 
character-set-server=utf8
collation-server=utf8_general_ci
wait_timeout=100
interactive_timeout=100
 
[mysqld_safe]
character-set-server=utf8
collation-server=utf8_general_ci
```
创建同步用户
```bash
主机器中创建从机用户
GRANT replication slave ON *.* TO 'slave_user'@'172.18.9.53' IDENTIFIED BY 'abcd@1111'
FLUSH privileges;

```

修改my.cnf(从)
```file
server-id=2 
binlog_format=MIXED

character-set-server=utf8
collation-server=utf8_general_ci
wait_timeout=100
interactive_timeout=100

# Disabling symbolic-links is recommended to prevent assorted security risks
symbolic-links=0

# Recommended in standard MySQL setup
sql_mode=NO_ENGINE_SUBSTITUTION,STRICT_TRANS_TABLES 

[mysqld_safe]
log-error=/var/log/mysqld.log
pid-file=/var/run/mysqld/mysqld.pid

character-set-server=utf8
collation-server=utf8_general_ci

```
从数据库服务器上设置主数据库服务器向从数据库服务器同步
``` bash
change master to master_host = '172.18.8.52', master_user = 'slave_user', master_password = 'abcd@1111',master_log_file = 'mysqld-bin.000002',master_log_pos = 120;
```
mysql控制台中启动slave
```bash
start slave;
```
查看状态
slave
```bash
show slave status
```







