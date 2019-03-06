# 零碎问题

### 1、SYS、SYSTEM用户登录

默认密码：

SYSTEM默认密码：manager，使用sqlplus登录时需加上 as sysdba，即密码为：manager as sysdba

SYS默认密码：change\_on\_install，使用sqlplus登录时需加上 as sysdba，即密码为：change\_on\_install as sysdba

（1）显式密码登录

在命令行下登录SYSTEM：sqlplus SYSTEM/manager as sysdba

在命令行下登录SYSTEM（使用tns）：sqlplus SYSTEM/manager@ORCL as sysdba

在命令行下登录SYS：sqlplus SYS/change\_on\_install as sysdba

在命令行下登录SYS（使用tns）：sqlplus SYS/change\_on\_install@ORCL as sysdba

（2）隐式密码登录

先命令行下执行sqlplus或者直接使用sqlplus。在输入用户名后

