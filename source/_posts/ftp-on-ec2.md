title: ftp on ec2
date: 2016-05-20 11:55:04
tags:
---
title: ftp on ec2
tags:
---

referece linking 
[http://iqbon.iteye.com/blog/1896254](http://iqbon.iteye.com/blog/1896254)

同步日志
rsync -azv -e  "ssh -i /home/ec2-user/HAZE_WEB.pem"  ec2-user@172.18.5.35:/data/logs /data/
