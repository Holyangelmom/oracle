1、查询session连接数

select count\(\*\) from v$session;

2、查询并发/活动的session连接数

select count\(\*\) from v$session where status='ACTIVE';

3、查询最大连接数

show parameter processes;

4、查询不同用户的连接状态

select username,count\(username\),status from v$session where username is not null group by username,status;

5、设置默认的idle\_time时间\(单位:min\)

alter profile default limit idle\_time 120;

6、密码过期

查看用户状态

select username, account\_status from dba\_users where username='user1';

若状态为lock，则解锁

alter user user1 account unlock;

修改密码（特殊密码需使用双引号括起来）

alter user user1 identified by "EX@111";

根据需要修改密码过期设置（单位为天）

alter profile default limit  password\_l_ife_\_time 360;

alter profile default limit  password\_l_ife_\_time unlimited;

7、sqlplus连接数据库 用户密码包含特殊字符

sqlplus username/\"password\"@SID

sqlplus user1/\"EX163@333\"@ORCL

