title: mysql useful command
date: 2016-05-16 18:22:23
tags:
---
title: mysql useful command
date: 2016-05-16 18:22:23
tags:
---

exception : mysql Unknown command ‘\”.
```bash
mysql -uroot -pxxxxxx --default-character-set=utf8

```
localhost 指本地
%指任意ip 不包括本地

```bash
GRANT ALL PRIVILEGES ON *.* TO 'haze_user'@'localhost' IDENTIFIED BY 'XXXX' WITH GRANT OPTION;

```

ser does not have access to metadata required to determine stored procedure parameter types. If rights can not be granted,

如果有存储过程需要赋予用户存储过程的权限
```bash
GRANT SELECT ON mysql.proc TO 'user'@'localhost';  

```
存储过程的一些操作
```bash
$ select db, name, definer from  mysql.proc where `definer` like '%xxxx%';
$ UPDATE mysql.proc set `definer`= 'xxxx' where `definer` = 'xxxxx'
 
```

添加索引
聚合索引 要注意字段间的先后关系

```bash
alter table partner add index
partner_index_id_type(partner_restaurant_id, partner_type);

drop index partner_index_id_type on partner;


```

time_format用法
 

```
select * from `table_name` 
  where date_format(create_date ,'%Y-%m-%d') > '2017-08-10' 

select * from `table_name` 
  where create_date >  date_format('2017-08-10 00:00:00','%Y-%m -%d %H:%i:%s')

```