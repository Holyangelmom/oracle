### 常用函数

### 1、NVL函数

##### （1）函数定义

NVL\(expr1,expr2\)

如果 exp1 为 null 值，则 NVL\( \) 返回 exp2。如果 exp1 为 null 值，则返回 exp1。exp1 和 exp2 可以是任意一种数据类型。如果 exp1 与 exp2 的结果皆为 null 值，则 NVL\( \) 返回 NULL。

##### （2）使用样例

_select nvl\(null,null\) from dual_

_select nvl\(max\(id\)+1,1\) from oadb.t_\_query

