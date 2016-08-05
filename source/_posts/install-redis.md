title: install redis
date: 2016-05-14 17:55:55
tags:
---
title: install redis on centos 6
tags:
---

```bash
$ rpm -Uvh http://download.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm

$ rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm

$ yum --enablerepo=remi,remi-test install redis
```
else to do :
Uncomment requirepass
Comment bind 127.0.0.1