## Homework

- 创建一个电影列表
  - 列表中含有电影名字，年份，导演，评分
  - 功能要求：
    - 模糊查询电影名字
    - 模糊查询导演名字
    - 查询某年份的电影
    - 查询评高分电影

mysql> create table dinaying(mingzi varchar(20) not null,nianfen int(10) not null,daoyan varchar(20) not null,pingfen int(10));
Query OK, 0 rows affected (0.53 sec)

mysql> insert into dianying(mingzi,nianfen,daoyan,pingfen)values('shasheng',2013,'ninghao',8.9),('taijiong',2012,'xuzheng',9.0),('wurenqu',2012,'ninghao',8.8);
ERROR 1146 (42S02): Table 'zuoye.dianying' doesn't exist
mysql>
mysql> ^C
mysql> create table dianying(mingzi varchar(20) not null,nianfen int(10) not null,daoyan varchar(20) not null,pingfen int(10));
Query OK, 0 rows affected (0.66 sec)

mysql> insert into dianying(mingzi,nianfen,daoyan,pingfen)values('shasheng',2013,'ninghao',8.9),('taijiong',2012,'xuzheng',9.0),('wurenqu',2012,'ninghao',8.8);
Query OK, 3 rows affected (0.10 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> select * from dianying;
+----------+---------+---------+---------+
| mingzi   | nianfen | daoyan  | pingfen |
+----------+---------+---------+---------+
| shasheng |    2013 | ninghao |       9 |
| taijiong |    2012 | xuzheng |       9 |
| wurenqu  |    2012 | ninghao |       9 |
+----------+---------+---------+---------+
3 rows in set (0.00 sec)

mysql> select mingzi from dianying where mingzi like &wu;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '&wu' at line 1
mysql> select mingzi from dianying where mingzi like '&wu';
Empty set (0.07 sec)

mysql> select mingzi from dianying where mingzi like '%wu';
Empty set (0.00 sec)

mysql> select mingzi from dianying where mingzi like 'wu%';
+---------+
| mingzi  |
+---------+
| wurenqu |
+---------+
1 row in set (0.00 sec)

mysql> select daoyan from dianying where daoyan like 'ning%';
+---------+
| daoyan  |
+---------+
| ninghao |
| ninghao |
+---------+
2 rows in set (0.00 sec)

mysql> select * from dianying where nianfen=2012;
+----------+---------+---------+---------+
| mingzi   | nianfen | daoyan  | pingfen |
+----------+---------+---------+---------+
| taijiong |    2012 | xuzheng |       9 |
| wurenqu  |    2012 | ninghao |       9 |
+----------+---------+---------+---------+
2 rows in set (0.00 sec)

mysql> select mingzi,pingfen from dianying where pingfen=(select max(pingfen) from dianying);
+----------+---------+
| mingzi   | pingfen |
+----------+---------+
| shasheng |       9 |
| taijiong |       9 |
| wurenqu  |       9 |
+----------+---------+
3 rows in set (0.09 sec)

mysql>![屏幕截图(15)](C:\Users\赵文洋\Pictures\Screenshots\屏幕截图(15).png)

![屏幕截图(16)](C:\Users\赵文洋\Pictures\Screenshots\屏幕截图(16).png)