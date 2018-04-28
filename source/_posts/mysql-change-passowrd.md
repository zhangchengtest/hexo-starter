title: mysql change passowrd
date: 2017-06-06 15:00:22
tags:
---
title: mysql change passowrd
tags:
---

ps -ef|grep mysql*
去查看mysqld_safe在哪里

```
/usr/bin/mysqld_safe --skip-grant-tables >/dev/null 2>&1 &

登陆
/usr/bin/mysql -u root mysql


update user set password = Password('abcd@1234') where User = 'root';

flush privileges;

ok， restart
```