# mysql


## 数据类型

### 整数类型

		unsigned表示不可以有负值，尽量不使用。unsigned不仅限定存入数据的正负号，也会限制从数据库中取出数据为非负数。（所以可能会出问题）。如果设置zerofill属性，则该列自动为unsigned

### 日期和时间类型

		timestamp占用空间最小，存入utc时间，可自动根据时区刷新，支持范围小，datetime范围大占用空间大，time表示时间间隔，可以有负值

### 字符类型

		通过设置字符集的排序规则可以区分大小写，以ci结尾的即表示忽略大小写
		使用char和varchar比较字符串时，比较字符串内容，不考虑补位情况，而binary和varbinary比较时需要考虑空位补位的情况

## sql_mode设置

		allow_invalid_dates允许非法日期对DATE和DATETIME有效，timestamp无效（注意timestamp和datetime的区别）
		STRICT_TRANS_TABLES对所有事务表严格，strict_all_tables对所有事务非事务表严格。

## 查询

		除去group by（null值会被分到一组）和order by（null值会放在一起排序），null在比较中都不相等。
		
		子查询不能作为聚合函数的分组条件
		distinct关键字会创建内存临时表（或者放于硬盘上），为distinct列创建唯一索引

