# SQL学习记录

## 1.基础关键字用法

## DISTINCT

功能是去重，位于列前 distinct user_id,得到的数据集将不会有重复的user_id.

## AS

功能是修改或添加名字，使用对象为列或者结果集。user_id as id或者 select * from user as A

## between A and B 

用于条件判断，相当于 >= A and <=B

## IN

功能是范围筛选.id in ('1','2')。in 后面是小括号

## [NOT] Like

功能是模糊匹配.匹配串中包含如下四种通配符：

_:匹配任意一个字符；%：匹配0个或多个字符；[]:匹配[]中任意一个字符；[^]:不匹配[]中的任意一个字符

## MAX

功能是取出列中的最大值，MAX(age)

## ROUND

功能是对指定数据保留n位小数。ROUND(1.23, 1)对1.23保留1位小数



## LEFT JOIN, RIGHT JOIN, INNER JOIN, FULL JOIN

LEFT JOIN 以左表为基础，对右表进行遍历连接，长度至少为左表的长度；若未找到右表的匹配，则右表字段为空；若左表的条件字段为空，则不返回行。

RIGHT JOIN 与 LEFT JOIN 相反

INNER JOIN只返回两表的交集

FULL JOIN 返回右边全表与左边全表以及相交部分



## UNION 与 UNION ALL

UNION实现的是取并集，没有重复的数据

UNION ALL也是取并集，有重复的数据



经验：GROUP BY 要用在Having语句前面；查询出的结果集需要命名；聚合作为筛选条件时要使用Having；

​			as 语句对结果集命名时，需要在where前面；

​			如果语句存在JOIN，则不能再JOIN的左边和右边使用where，必须对JOIN的结果使用where;

​			join后面需要接结果集，如果是select语句，则需用括号括起来

案例

1.从杂志订单关系表中，选出每个杂志的最新订阅情况

关键 NOT EXISTS

select mid,id,count 

from magazineorder A 

where not exists (select * from magazineorder B where A.mid=B.mid and A.id<B.id)
