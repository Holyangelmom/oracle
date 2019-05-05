### 4、ORA-02290: 违反检查约束条件

在建表时设置某些字段不可为空，Oracle为此增加了一条约束条件，在每次插入数据时都检查是否满足该约束条件，不满足则报错。在撸bug时用sql修改该字段可为空，但因为该字段对应的约束条件依然存在，故插入数据时报错：ORA-02290: 违反检查约束条件。

解决方法：

（1）确定该约束在哪个字段上：select \* from user\_constraints where table\_name='TABLENAME';

（2）找到报错中约束条件，删除该check约束问题也就可以解决：ALTER TABLE TABLENAME DROP CONSTRAINT SYS\_C0069731。【注：这里不需要使用引号】





