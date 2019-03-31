### 2、分页查询

##### （1）参考资料

[https://www.cnblogs.com/jay763190097/p/6813792.html](https://www.cnblogs.com/jay763190097/p/6813792.html)

[https://www.cnblogs.com/zhaotiancheng/p/6262635.html](https://www.cnblogs.com/zhaotiancheng/p/6262635.html)

##### （2）rownum

说到分页，不得不提到rownum。

rownum总是从1开始的，第一条不满足去掉的话，第二条的rownum 又成了1。依此类推，所以永远没有不满足条件的记录。可以这样理解：rownum是一个序列，是Oracle数据库从数据文件或缓冲区中读取数据的顺序。它取得第一条记录则rownum值为1，第二条为2。依次类推。

当使用“&gt;、&gt;=、=、between...and”这些条件时，从缓冲区或数据文件中得到的第一条记录的rownum为1，不符合sql语句的条件，会被删除，接着取下条。  
下条的rownum还会是1，又被删除，依次类推，便没有了数据。

**综上所述：**上限条件必须放在子查询，而下限条件必须放在外层查询。

