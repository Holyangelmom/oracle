### 2、CASE函数

##### （1）case函数简述

case函数有两种用法。

简单Case函数

```
CASE search_expression

WHEN expression1 THEN result1

WHEN expression2 THEN result2

ELSE default_result

END
```

Case搜索函数

```
CASE

WHEN condition1 THEN result1

WHEN condistion2 THEN result2

ELSE default_result

END
```

##### （2）使用样例

简单case函数

```
select

    case sex
    when 1 then '男'
    when 2 then '女'
    else '其他'
    end
    as sex
    
from t_query_config
```

Case搜索函数

```
select 

    case 
    when sex = 1 then '男'  
    when sex = 2 then '女' 
    else '其他' 
    end
    as sex

from t_query_config
```



