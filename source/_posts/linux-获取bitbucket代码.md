title: linux 获取bitbucket代码
date: 2016-05-23 10:54:02
tags:
---
title: linux 获取bitbucket代码
tags:
---

1.在终端中运行ssh-keygen。 
2.然后一路enter，直接到结束。不要理会中间的输入。 
3 打开用户目录下.ssh/id_rsa.pub文件，复制其内容。 
4.Bitbucket上点右上角的小头像，然后选择Manage account. 
5.左边目录选择SSH Keys， 然后选择add key。将刚才复制的内容粘贴进去，保存。 

这时才能克隆 

git clone