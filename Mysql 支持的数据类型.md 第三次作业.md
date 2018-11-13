## HomeWork

- 创建一个收藏表单，要求功能：
  - 增加收藏
  - 取消搜藏
  - 搜藏物品的名称
  - 用户唯一id
- 将SQL语句和结果提交到GitHub
- Good Luck~~

crosoft Windows [版本 10.0.17134.285]
(c) 2018 Microsoft Corporation。保留所有权利。

C:\Users\赵文洋>mysql -u root -p
Enter password: **********
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 15
Server version: 8.0.12 MySQL Community Server - GPL

Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| shopping           |
| sys                |
| zuoye              |
+--------------------+
6 rows in set (0.29 sec)

mysql> use zuoye;
Database changed
mysql> create table shoucangbiao(id int primary key auto_increment,yonghu varchar(20));
Query OK, 0 rows affected (1.32 sec)

mysql> alter table shoucangbiao add shoucang varchar(20);
Query OK, 0 rows affected (0.66 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> select * from shoucangbiao;
Empty set (0.00 sec)

mysql> desc shoucangbiao;
+----------+-------------+------+-----+---------+----------------+
| Field    | Type        | Null | Key | Default | Extra          |
+----------+-------------+------+-----+---------+----------------+
| id       | int(11)     | NO   | PRI | NULL    | auto_increment |
| yonghu   | varchar(20) | YES  |     | NULL    |                |
| shoucang | varchar(20) | YES  |     | NULL    |                |
+----------+-------------+------+-----+---------+----------------+
3 rows in set (0.03 sec)

mysql> insert into shoucangbiao(id,yonghu)values(1,'j'),(2,'i');
Query OK, 2 rows affected (0.59 sec)
Records: 2  Duplicates: 0  Warnings: 0

mysql> select * from shoucangbiao;
+----+--------+----------+
| id | yonghu | shoucang |
+----+--------+----------+
|  1 | j      | NULL     |
|  2 | i      | NULL     |
+----+--------+----------+
2 rows in set (0.00 sec)

mysql> alter table shoucangbiao drop shoucang;
Query OK, 0 rows affected (3.06 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> select * from shoucangbiao;
+----+--------+
| id | yonghu |
+----+--------+
|  1 | j      |
|  2 | i      |
+----+--------+
2 rows in set (0.00 sec)

mysql>![屏幕截图(14)](C:\Users\赵文洋\Pictures\Screenshots\屏幕截图(14).png)