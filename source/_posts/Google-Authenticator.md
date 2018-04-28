title: ' Google Authenticator'
date: 2017-05-22 11:02:55
tags:
---
title: ' Google Authenticator'
tags:
---

reference 
[https://aws.amazon.com/cn/blogs/startups/securing-ssh-to-amazon-ec2-linux-hosts/](https://aws.amazon.com/cn/blogs/startups/securing-ssh-to-amazon-ec2-linux-hosts/)

10. Now edit the SSH configuration file so that Google Authenticator is called as a second factor of authentication. First, change the following option to “yes”:

ChallengeResponseAuthentication yes

vi /etc/ssh/sshd_config

not ssh_config


11. Next, add a new line to the bottom of the file as follows:

AuthenticationMethods publickey,keyboard-interactive


sudo /etc/init.d/sshd restart