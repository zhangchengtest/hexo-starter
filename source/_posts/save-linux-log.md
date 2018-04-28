title: save linux log
date: 2017-03-30 16:44:51
tags:
---
title: save linux log
tags:
---

```
mv /etc/audit/audit.rules /etc/audit/audit.rules.bak
vi /etc/audit/rules.d/audit.rules

开启rsyslog等
vi /etc/rsyslog.conf

去掉以下的注释 ＃
$ModLoad imudp
$UDPServerRun 514
$ModLoad imtcp
$InputTCPServerRun 514

$WorkDirectory /var/lib/rsyslog # where to place spool files
$ActionQueueFileName fwdRule1 # unique name prefix for spool files
$ActionQueueMaxDiskSpace 1g   # 1gb space limit (use as much as possible)
$ActionQueueSaveOnShutdown on # save messages to disk on shutdown
$ActionQueueType LinkedList   # run asynchronously
$ActionResumeRetryCount -1    # infinite retries if host is down


添加
*.info                 @@log.haze.com:514

service rsyslog restart
service auditd restart
tail -f /var/log/messages

rsyslog

日志级别:
——————————————————————
debug       –有调式信息的，日志信息最多
info        –一般信息的日志，最常用
notice      –最具有重要性的普通条件的信息
warning     –警告级别
err         –错误级别，阻止某个功能或者模块不能正常工作的信息
crit        –严重级别，阻止整个系统或者整个软件不能正常工作的信息
alert       –需要立刻修改的信息
emerg       –内核崩溃等严重信息
none        –什么都不记录
从上到下，级别从低到高，记录的信息越来越少

邮件的所有信息存放在/var/log/maillog; 这里有一个-符号, 表示是使用异步的方式记录, 因为日志一般会比较大



添加 audit=1 到kernel行的末尾
 vi /boot/grub/menu.lst
 
 modify the /etc/pam.d/system-auth and /etc/pam.d/password-auth files using the disable and enable options in the following format:

vi /etc/pam.d/system-auth
vi /etc/pam.d/password-auth 
 
session  required pam_tty_audit.so disable=ec2-user enable=root log_passwd
$ aureport --tty -ts today | tail

```