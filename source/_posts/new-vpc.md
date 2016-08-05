title: new vpc
date: 2016-05-14 14:40:27
tags:
---
title: new vpc
date: 2016-05-14 14:40:27
tags:
---
参考链接
[http://heylinux.com/archives/3620.html](http://heylinux.com/archives/3620.html)

16 24
A类地址：10.0.0.0～10.255.255.255 
B类地址：172.16.0.0～172.31.255.255 
C类地址：192.168.0.0～192.168.255.255

security group 
参考链接
[http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Appendix_NACLs.html#VPC_Appendix_NACLs_Scenario_1](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Appendix_NACLs.html#VPC_Appendix_NACLs_Scenario_1)

1.创建VPC
![http://images.zhangcheng.club/images/2016/05/14/Ay3.png](http://images.zhangcheng.club/images/2016/05/14/Ay3.png)
1.1更改dns
![http://images.zhangcheng.club/images/2016/05/14/W0W.png](http://images.zhangcheng.club/images/2016/05/14/W0W.png)
2.创建subnet
![http://images.zhangcheng.club/images/2016/05/14/LyR.png](http://images.zhangcheng.club/images/2016/05/14/LyR.png)
3.选择Route Tables，点击Create Route Table，创建一个新的路由表public_local_igw，并将这个路由表绑定到Public Subnet上
![http://images.zhangcheng.club/images/2016/05/14/4KA.png](http://images.zhangcheng.club/images/2016/05/14/4KA.png)
4.选择Internet Gateways，点击Create Internet Gateway创建一个互联网网关，作为Public Subnet的公网出口；
![http://images.zhangcheng.club/images/2016/05/14/l6w.png](http://images.zhangcheng.club/images/2016/05/14/l6w.png)
5.选择Route Tables，点击public_local_igw，增加一条路由，设置新增的Internet Gateway为Public Subnet的默认公网出口网关；
![剪贴板.png](http://images.zhangcheng.club/images/2016/05/20/8RB.png)
