title: apache ssl config
date: 2016-11-17 14:34:36
tags:
---
title: apache ssl config
tags:
---

需要的证书
cicada.crt cicada.key

需要将domain_validated.ca-bundle这个文件cat >> cicada.crt

找到
ssl验证url:
[https://cryptoreport.websecurity.symantec.com/checker/views/certCheck.jsp](
https://cryptoreport.websecurity.symantec.com/checker/views/certCheck.jsp)

[https://www.chinassl.net/ssltools/ssl-checker.html](https://www.chinassl.net/ssltools/ssl-checker.html)

ubuntu解压zip
unzip XXX.zip
ubuntu apache重启
service apache2 restart
如果重启没用
得stop掉用
sudo /etc/init.d/apache2 start 再次启动

apache2 强制跳转ssl
```ssl

NameVirtualHost *:80
<VirtualHost *:80>
   ServerName mysite.example.com
   DocumentRoot /usr/local/apache2/htdocs 
   Redirect permanent / https://mysite.example.com/
</VirtualHost>

<VirtualHost _default_:443>
   ServerName mysite.example.com
  DocumentRoot /usr/local/apache2/htdocs
  SSLEngine On
 # etc...
</VirtualHost>

或者这样

<VirtualHost *:80>
    RewriteEngine On
    RewriteCond %{HTTPS} off
    RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI}
</VirtualHost>


```

```bash
sudo a2enmod rewrite
sudo a2enmod ssl

```








