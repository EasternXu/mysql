# 数据库引擎
# mysiam--<=5.5mysql默认引擎 
#####1.数据文件--支持物理赋值，粘贴
		*.frm--结构文件
		*.MYD--数据文件
		*.MYI--索引文件
##### 2.存储方式 -- 存储顺序为插入顺序
##### 3.并发性
		不支持事务
		如果对表的事务要求不高，以查询和添加为主，可以使用。
# innodb-->=5.5mysql默认引擎--推荐
##### 1.提供事务，行级锁定，存储引擎

##### 2.数据文件
	*.frm--结构文件
	默认 ibdata1--存放数据和索引
##### 3. 修改存储配置
	set global innodb_file_per_table=1 -- 每个表对应一个表空间文件
	表名.frm--对应表的结构文件
	表名.ibd--对应表的存放数据和索引
##### 4.数据备份与还原
	mysqldump -u用户名 -p密码 数据库名称 > 保存路径.sql  【备份】
	mysqldump -u用户名 -p密码 数据库名称 < 保存路径.sql  【备份】

##### 5.存储方式 -- 按照主键顺存储

##### 6.并发处理
	- 1.锁机制 --  保证操作的隔离性 
	操作：
		1.读锁--读操作时增加的锁，也叫共享锁，加锁时，所有人只能读。
		2.写锁==写操作是增加的锁，也叫独占锁或者排他锁，只有锁表的客户可以操作这个表（读写）
	锁定范围：
		1.表级锁
		2.行级锁


 

