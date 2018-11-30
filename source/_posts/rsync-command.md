title: rsync command
date: 2016-12-14 14:42:58
tags:
---
title: rsync command
tags:
---

千万不能删除随便删除软连接
不要加／ 不要加／不要加／
重要的事情说三遍

```
rsync -vzrtopg  --exclude "syslog" --progress -e "ssh -i /home/ec2-user/HAZE_WEB.pem"  ec2-user@172.18.5.35:/data/logs/ /data/logs/



```