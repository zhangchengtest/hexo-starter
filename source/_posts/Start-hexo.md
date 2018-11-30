title: Start hexo
tags: []
categories: []
date: 2016-03-18 18:16:00
---
title: hexo 


安装hexo
npm install -g hexo

hexo init
安装依赖
npm install

安装theme next

git clone https://github.com/iissnan/hexo-theme-next themes/next

安装search


后台启动
``` bash
$ nohup hexo server > /var/log/blog.log &
```