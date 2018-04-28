title: new user in linux
date: 2016-05-20 12:08:07
tags:
---
title: new user in linux
tags:
---

参考链接
[http://blog.csdn.net/beitiandijun/article/details/41678251](http://blog.csdn.net/beitiandijun/article/details/41678251)

```
sudo adduser newuser
sudo su - newuser
mkdir .ssh
chmod 700 .ssh
touch .ssh/authorized_keys
chmod 600 .ssh/authorized_keys


ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQClKsfkNkuSevGj3eYhCe53pcjqP3maAhDFcvBS7O6V
hz2ItxCih+PnDSUaw+WNQn/mZphTk/a/gU8jEzoOWbkM4yxyb/wB96xbiFveSFJuOp/d6RJhJOI0iBXr
lsLnBItntckiJ7FbtxJMXLvvwJryDUilBMTjYtwB+QhYXUMOzce5Pjz5/i8SeJtjnV3iAoG/cQk+0FzZ
qaeJAAHco+CY/5WrUBkrHmFJr6HcXkvJdWPkYQS3xqC0+FmUZofz221CBt5IMucxXPkX4rWi+z7wB3Rb
BQoQzd8v7yeb7OzlPnWOyN0qFU0XA246RA8QFYiCNYwI3f05p6KLxEXAMPLE

使用配置文件登录
ssh-keygen -y -f private_key1.pem > public_key1.pub
权限
sudo visudo
add in the bottom

<username> ALL=NOPASSWD: ALL

```