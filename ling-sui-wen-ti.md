# 零碎问题

1、使用sqlplus登录SYS、SYSTEM用户

（1）首次登录

SYSTEM默认密码：manager，使用sqlplus登录时需加上 as sysdba，即密码为：manager as sysdba

SYS默认密码：change\_on\_install，使用sqlplus登录时需加上 as sysdba，即密码为：change\_on\_install as sysdba

（2）修改密码

alter user SYS identified by "xxx";

（3）再次登录

SYS默认密码：xxx，使用sqlplus登录时**仍需加上 as sysdba**，即密码为：xxx as sysdba

