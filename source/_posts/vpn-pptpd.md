title: 阿里云搭建VPN
date: 2016-03-19 00:00:11
tags:
---
title: aaaaaa
tags:nihao
---
参考链接[http://blog.csdn.net/johnnycode/article/details/45543157](http://blog.csdn.net/johnnycode/article/details/45543157)

### 安装 ppp pptpd iptables

ppp 数据链路层协议

pptpd VPN服务类型之一

iptables 防火墙,用来消息转发
```bash
$ yum install -y ppp pptpd iptables   
```
```bash
$ vi /etc/ppp/options.pptpd  
```
作如下修改
```shell
#ms-dns 10.0.0.1  
#ms-dns 10.0.0.2  
# 找到上面两行 换成下面两行
ms-dns 8.8.8.8  
ms-dns 8.8.4.4 
```
添加用户名和密码
```bash
$ vi /etc/ppp/chap-secrets  
```
```shell
#在文件下面添加
zhangcheng pptpd 123456 * 
```

```bash
$ vi /etc/pptpd.conf 
```
把下面两行注释去掉（即#键）
```shell
#localip 192.168.0.1  
#remoteip 192.168.0.234-238,192.168.0.245  
```

```bash
vi /etc/sysctl.conf
```
```shell
net.ipv4.ip_forward = 0  
应该改成
net.ipv4.ip_forward = 1
```
需要重新加载
```bash
$ sysctl -p  
```

```bash
$ iptables -t nat -A POSTROUTING -s 192.168.0.0/24 -o eth1 -jMASQUERADE 

$ service iptables save 
$ service iptables start
$ service pptpd restart #重新启动 pptpd  
```




