#
## sql优化
### 语句
- 不要写SELECT *的语句
- 不要写没有WHERE的SQL语句
- 使用join代替子查询
- 联合查询快，数据量少情况下；数据量大一般就会很慢
- 单表查询慢一些，但是在数据量大情况下易于解耦，易于优化
- update 批量更新用update table set field = case id when 1 then 10 case id when 2 then 20 end where id in (1,2) 比一条条更新快5-10倍
### 索引优化
- 主键索引，它是一种特殊的唯一索引，不允许有空值。
- 不要写SELECT *的语句

### 全表扫描语句(慎用)
- 左模糊查询'%...'
- 使用了不等操作符！=
- Or使用不当，or两边都必须有索引才行
- In 、not in
- Where子句对字段进行表达式操作

## GPU Database
- ![avatar](https://raw.githubusercontent.com/mouse123/my-tips/master/image/gpu.gif)