title: 配置https证书
date: 2016-11-09 11:24:50
tags:
---
title: 配置https证书
tags:
---

nginx
1. in the http{} configuration block
不仅仅在server block中添加

ssl_protocols TLSv1 TLSv1.1 TLSv1.2;

升级openssl 到1.0.1t版本：
```bash
*** [c_zlib.o] 错误 1
```

yum -y install gcc gcc-c++ zlib-devel

```bash
# wget https://www.openssl.org/source/openssl-1.0.1t.tar.gz
# tar zvxf openssl-1.0.1t.tar.gz 
# cd openssl-1.0.1t
# ls
# ./config shared zlib
# make
# make install
# /usr/local/ssh/bin/openssl version
```
```bash
# mv /usr/bin/openssl /usr/bin/openssl-old
# mv /usr/include/openssl /usr/include/openssl-old
# ln -s /usr/local/ssl/bin/openssl /usr/bin/openssl
# ln -s /usr/local/ssl/include/openssl/ /usr/include/openssl
# echo "/usr/local/ssl/lib" >> /etc/ld.so.conf
# ldconfig 
# openssl version
```

验证ssl
[https://www.ssllabs.com/ssltest/analyze.html](
https://www.ssllabs.com/ssltest/analyze.html)

```error
This server supports weak Diffie-Hellman (DH) key exchange parameters. Grade capped to B
```
生成dhparam
```
openssl dhparam -out /etc/nginx/ssl/dhparam.pem 2048
```


