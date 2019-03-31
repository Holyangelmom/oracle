### 2、分页查询

##### （1）参考资料

[https://www.cnblogs.com/jay763190097/p/6813792.html](https://www.cnblogs.com/jay763190097/p/6813792.html)

[https://www.cnblogs.com/zhaotiancheng/p/6262635.html](https://www.cnblogs.com/zhaotiancheng/p/6262635.html)

##### （2）rownum

分页的目的就是控制输出结果集大小，将结果尽快的返回。说到分页，不得不提到关键字rownum。

rownum总是从1开始的，第一条不满足去掉的话，第二条的rownum 又成了1。依此类推，所以永远没有不满足条件的记录。可以这样理解：rownum是一个序列，是Oracle数据库从数据文件或缓冲区中读取数据的顺序。它取得第一条记录则rownum值为1，第二条为2。依次类推。

当使用“&gt;、&gt;=、=、between...and”这些条件时，从缓冲区或数据文件中得到的第一条记录的rownum为1，不符合sql语句的条件，会被删除，接着取下条。下条的rownum还会是1，又被删除，依次类推，便没有了数据。

**综上所述：**上限条件必须放在子查询，而下限条件必须放在外层查询。

##### （3）两种分页写法

```java
--第一种方法

select *
from (select row_.*, rownum rn
      from (select *
            from test
            order by id asc
            ) row_
      where rownum <= 40)
where rn >= 20;



--疑问：可以用两层查询就能完成分页，为何网上很多人用三层查询？
select row_.*
from (
    select test.*, rownum rn
    from test
    where rownum <= 40
) row_
where row_.rn >=20



--第二种方法
select * 
from (select a.*, rownum rn  
      from (select * 
            from test
            ) a
)
where rn between 20 and 40  
```

对比这两种写法，绝大多数的情况下，第一个查询的效率比第二个高得多。

第一种写法：在大多数情况拥有较高的效率，主要体现在第二层通过rownum&lt;= 40来控制最大值，在查询的最外层控制最小值。

第二种写法：去掉查询第二层的where rownum &lt;= 40语句，在查询的最外层控制分页的最小值和最大值。

