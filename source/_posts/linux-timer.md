---
title: linux timer
date: 2016-05-17 18:06:03
tags:
---

编辑
crontab -e
查看
crontab -l
查看日志

看 /var/log/cron这个文件就可以，可以用tail -f /var/log/cron观察
对于aws ec2-user
```bash
tail -f /var/spool/mail/ec2-user 
```
