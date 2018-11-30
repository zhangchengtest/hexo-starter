title: vsftp install
date: 2016-12-14 13:53:50
tags:
---
title: vsftp install
tags:
---

modify name
```
yum install vsftpd

vi /etc/vsftpd/vsftpd.conf
 
```
清空文件 再写入
```
#禁止匿名访问
anonymous_enable=NO
#允许本地帐户访问
local_enable=YES
#允许写入(上传)
write_enable=YES
local_umask=022
#允许弹出目录信息
dirmessage_enable=YES
#不需要日志xferlog_enable=NO
connect_from_port_20=YES
#使用本地时间
use_localtime=YES
#认证文件名(默认为此值)
pam_service_name=vsftpd
#开启侦听
listen=YES
#开启tcp访问控制项
tcp_wrappers=YES
#只有写入vsftpd.user_list内的帐户允许访问
local_root=/ROOT
userlist_enable=YES
userlist_deny=NO
userlist_file=/etc/vsftpd/user_list
#只有写入vsftpd.chroot_list的帐户不被chroot
chroot_local_user=YES
chroot_list_enable=YES
#vsftpd.chroot_list需要手动建立
chroot_list_file=/etc/vsftpd/chroot_list
#允许文本模式下载
ascii_download_enable=YES
#允许文本模式上传
ascii_upload_enable=YES
#启用被动模式
pasv_enable=YES
pasv_promiscuous=YES
pasv_min_port=60000
pasv_max_port=60020

```


```



service vsftpd restart

 useradd hao32 -d /home/hao32 -s /sbin/nologin

sudo passwd XXX

将你的用户添加到


203 error

vi /etc/vsftpd/chroot_list
空的的可以


```