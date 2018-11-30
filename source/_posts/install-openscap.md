title: install openscap
date: 2017-03-20 16:04:48
tags:
---
title: install openscap
tags:
---

yum install autoconf automake libtool


2.

yum install dbus-devel GConf2-devel libacl-devel libblkid-devel libcap-devel libcurl-devel libgcrypt-devel libselinux-devel libxml2-devel libxslt-devel make openldap-devel pcre-devel perl-XML-Parser perl-XML-XPath perl-devel python-devel rpm-devel swig bzip2-devel

./configure
make

make test

make install


$ cd scap-security-guide/ $ cd build/ $ cmake ../ $ make -j4


maybe
pip install lxml

openscap should install in /usr/share/

then install scap-security-guide


```
sed -i -e "s#<platform>Red Hat Enterprise Linux 6</platform>#<platform>CentOS 6</platform>##g" /usr/local/share/xml/scap/ssg/content/ssg-rhel6-cpe-oval.xml

sed -i -e "s#cpe:/o:redhat:enterprise_linux#cpe:/o:centos:centos##g" /usr/local/share/xml/scap/ssg/content/ssg-rhel6-xccdf.xml

```
