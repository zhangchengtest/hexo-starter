title: upgrade openssh
date: 2017-05-10 14:04:29
tags:
---
title: upgrade openssh
tags:
---

refenrencce
[http://sun-ao.github.io/2016/06/13/update-openssh-to-7-2p2/](http://sun-ao.github.io/2016/06/13/update-openssh-to-7-2p2/)

wget https://mirrors.evowise.com/pub/OpenBSD/OpenSSH/portable/openssh-7.5p1.tar.gz

tar zxvf ..

1.删除旧版openssh

rpm -qa|grep openssh

上面的旧版删掉

2.mv /etc/ssh /etc/ssh_bak

```

yum install gcc openssl-devel pam-devel rpm-build


./configure --prefix=/usr --sysconfdir=/etc/ssh --with-pam --with-zlib --with-md5-passwords

make

make install

service sshd reload 
service sshd restart

ssh -V

```



