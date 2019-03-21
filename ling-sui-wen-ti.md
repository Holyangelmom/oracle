# 零碎问题

### 1、SYS、SYSTEM用户登录

默认密码：

SYSTEM默认密码：manager。

SYS默认密码：change\_on\_install。

**（1）显式密码登录**

在cmd或终端命令行下登录SYSTEM：sqlplus SYSTEM/密码 as sysdba

在cmd或终端命令行下登录SYSTEM（使用tns）：sqlplus SYSTEM/密码@ORCL as sysdba

在cmd或终端命令行下登录SYS：sqlplus SYS/密码 as sysdba

在cmd或终端命令行下登录SYS（使用tns）：sqlplus SYS/密码@ORCL as sysdba

**（2）隐式密码登录**

先命令行下执行sqlplus或者直接使用sqlplus。在输入用户名后输入密码xxx，输入密码时要加上as sysdba，即密码为：xxx as sysdba。

**（3）Navicat登录**

navicat只能登录SYS用户，登录SYSTEM用户会提示权限错误，原因未知。

![](/assets/navicat登录SYS.png)

![](/assets/navicat登录SYS2.png)

**（4）其他方式**

略

