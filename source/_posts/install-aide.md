title: install aide
date: 2017-03-28 14:07:14
tags:
---
title: install aide
tags:
---
reference link
[https://www.vultr.com/docs/setting-up-aide-advanced-intrusion-detection-on-centos-6](https://www.vultr.com/docs/setting-up-aide-advanced-intrusion-detection-on-centos-6)

```

yum install -y aide

aide --init

cd /var/lib/aide
mv aide.db.new.gz aide.db.gz

aide --check
aide --update

rm -f aide.db.gz
mv aide.db.new.gz aide.db.gz

crontab -e
MAILTO=nihaopay2016@163.com
0 8 * * * /usr/sbin/aide --check

```