title: linux时区更改
date: 2017-02-15 15:52:22
tags:
---
title: linux时区更改
tags:
---

```sh

cp /usr/share/zoneinfo/UTC /etc/localtime 

vi /etc/sysconfig/clock

ZONE="UTC"
UTC=true

date -s 08:00:10

```

```sh
修改mysql时区

show variables like '%time_zone%';  

in the my.cnf add words below

default_time_zone='+00:00'


```

修改jdk时区
```sh
import java.util.TimeZone;  
import java.util.Calendar;  
public class Test{  
    public static void main(String[] args) throws Exception {  
        Calendar calendar = Calendar.getInstance();        
        System.out.println("目前时间：" + calendar.getTime());  
        System.out.println("Calendar时区：：" + calendar.getTimeZone().getID());  
        System.out.println("user.timezone：" + System.getProperty("user.timezone"));  
        System.out.println("user.country：" + System.getProperty("user.country"));  
        System.out.println("默认时区：" + TimeZone.getDefault().getID());  
    }  
}  
```

```sh
vi /etc/profile

export TZ=UTC

```