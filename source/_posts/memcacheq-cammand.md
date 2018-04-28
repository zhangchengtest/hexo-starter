title: memcacheq cammand
date: 2016-05-20 10:17:22
tags:
---
title: memcacheq cammand
tags:
---

参考链接
[http://haoyun.blog.51cto.com/2038762/1133345](http://haoyun.blog.51cto.com/2038762/1133345)

set testq 0 0 8
然后enter 换行
再输入
zhangsan
启动的命令
memcacheq -d -r -u nobody -H /data/memcacheq -N -R -v -L 1024 -B 2048 &> /var/log/mq_error.log