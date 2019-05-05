# 常用sql

### 1、查询session连接数

_select count\(\*\) from v$session;_

### 2、查询并发/活动的session连接数

_select count\(\*\) from v$session where status='ACTIVE';_

### 3、查询最大连接数

_show parameter processes;_

### 4、查询不同用户的连接状态

_select username,count\(username\),status from v$session where username is not null group by username,status;_

### 5、设置默认的idle\_time时间\(单位:min\)

_alter profile default limit idle\_time 120;_

### 6、密码过期

查看用户状态

_select username, account\_status from dba\_users where username='user1';_

若状态为lock，则解锁

_alter user user1 account unlock;_

修改密码（特殊密码需使用双引号括起来）

_alter user user1 identified by "EX@111";_

根据需要修改密码过期设置（单位为天）

_alter profile default limit  password\_life\_time 360;_

_alter profile default limit  password\_life\_time unlimited;_

### 7、查看当前用户的表

_select tablename from user\_tables;_

_select \* from all\_tables where owner='XXX';_

### 8、修改列名

_alter table tableName rename column oldColumn to newColumn;_

### 9、修改列数据类型

_alter table tableName modify \(cloumnName 数据类型\);_

### 10、增加字段

_alter table tableName add bank\_name   char\(200\);_

### 11、设置主键

_alter table tableName add constraint PK\_BANK\_ID primary key\(BANK\_ID\);_



