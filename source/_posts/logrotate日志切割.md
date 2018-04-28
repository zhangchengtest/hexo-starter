title: logrotate日志切割
date: 2016-08-04 14:35:09
tags:
---
title: logrotate日志切割
tags:
---
参考链接
[http://blog.csdn.net/cjwid/article/details/1690101](http://blog.csdn.net/cjwid/article/details/1690101)

sudo yum install -y logrotate


run logrotate mannnly 

logrotate --force $CONFIG_FILE

-d debug it is fake


vi /etc/logrotate.d/nginx

```
/var/log/nginx/*log {
    create 0644 nginx nginx
    daily
    rotate 10
    missingok
    notifempty
    compress
    sharedscripts
    postrotate
        /etc/init.d/nginx reopen_logs
    endscript
}

[ ! -f /usr/local/nginx/logs/nginx.pid ] || kill -USR1 `cat /usr/local/nginx/logs/nginx.pid`



```

/ROOT/log/syslog_original/*log {
    daily
    rotate 10
    missingok
    notifempty
    compress
    sharedscripts
}

/ROOT/log/syslog/*log {
    daily
    rotate 10
    missingok
    notifempty
    compress
    sharedscripts
    postrotate
        /etc/init.d/rsyslog restart
        /usr/local/bin/supervisorctl restart 'python_tail:*'
        /etc/init.d/logstash restart
    endscript
}