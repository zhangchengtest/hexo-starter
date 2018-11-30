title: install nginx
date: 2016-05-18 19:10:34
tags:
---
title: install nginx
tags: nginx,linux
---

#yum install
rpm -ivh http://nginx.org/packages/centos/6/noarch/RPMS/nginx-release-centos-6-0.el6.ngx.noarch.rpm 

yum info nginx 
yum install nginx 

卸载nginx
yum remove nginx


#source  code

```shell
$ wget http://jaist.dl.sourceforge.net/project/pcre/pcre/8.33/pcre-8.33.tar.gz

$ tar zxvf pcre-8.33.tar.gz  
$ cd pcre-8.33/  
$ ./configure  
$ make && make install  

$ wget http://nginx.org/download/nginx-1.9.5.tar.gz


$ tar xvfz nginx-1.9.5.tar.gz
$ cd nginx-1.9.5

```
```shell
# vi auto/lib/openssl/conf
CORE_INCS="$CORE_INCS $OPENSSL/.openssl/include" 
CORE_DEPS="$CORE_DEPS $OPENSSL/.openssl/include/openssl/ssl.h" 
CORE_LIBS="$CORE_LIBS $OPENSSL/.openssl/lib/libssl.a" 
CORE_LIBS="$CORE_LIBS $OPENSSL/.openssl/lib/libcrypto.a"
改为：
CORE_INCS="$CORE_INCS $OPENSSL/include"
CORE_DEPS="$CORE_DEPS $OPENSSL/include/openssl/ssl.h"
CORE_LIBS="$CORE_LIBS $OPENSSL/lib/libssl.a"
CORE_LIBS="$CORE_LIBS $OPENSSL/lib/libcrypto.a"
```

```shell
$ ./configure --prefix=/usr/local/nginx --with-pcre=/usr/local/src/pcre-8.33/  --with-http_stub_status_module  --with-http_ssl_module --with-openssl=/usr/local/ssl --with-http_realip_module 


--error-log-path=/var/log/nginx/error.log --http-log-path=/var/log/nginx/access.log --pid-path=/var/run/nginx.pid 

can not be used , otherwise the logrotate will not work
$ make
$ sudo make install

```

to run

```bash
/usr/local/nginx/sbin/nginx

```
