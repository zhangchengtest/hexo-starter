title: mongodb install on censtos
date: 2017-01-09 13:03:39
tags:
---
title: mongodb install on censtos
tags:
---

今天天气不错



```bash
vi /etc/yum.repos.d/10gen.repo
```

```bash
[10gen] 

name=10gen Repository 

baseurl=http://downloads-distro.mongodb.org/repo/redhat/os/x86_64 

gpgcheck=0 

```

```bash
yum install mongo-10gen-server

yum install mongo-10gen

```

```
service mongod start
```


