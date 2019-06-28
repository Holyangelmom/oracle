# 其他命令

### 1、sqlplus连接数据库 用户密码包含特殊字符

_sqlplus username/\"password\"@SID_

_sqlplus user1/\"EX163@333\"@ORCL_

### 2、重启数据库

shutdown immediate;

startup;

##### 3、导出导入数据库

（1）完全导出导入命令

exp username/password@ip:port file="本地地址/文件名.dmp" full=y;

imp username/password@ip:portfile="本地地址/文件名.dmp" full=y;

（2）部分用户表导出导入

exp username/password@ip:portfile="本地地址/文件名.dmp" tables=\(table1, table2...\);

imp username/password@ip:port file="本地地址" full=y;

