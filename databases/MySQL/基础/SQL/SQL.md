# SQL通用语法
1. SQL语句可以单行或多行书写，以分号结尾；
2. SQL语句可以使用空格/缩进来增强语句的可读性
3. MySQL数据库的SQL语句不区分大小写，关键字建议使用大写
4. 注释
	- 单行注释：--注释内容 || # 注释内容（MySQL特有）
	- 多行注释：/ * 注释内容 * /
# SQL分类
![[SQL分类图示.png]]
# DDL
## DDL-数据库操作
### 查询
- 查询**所有**数据库
`SHOW DATABASES;`
- 查询**当前**数据库
`SELECT DATABASE();`
### 创建
`CREATE DATABASE [IF NOT EXISTS] 数据库名 [DEFAULT CHARSET 字符集] [COLATE 排序规则];`
### 删除
`DROP DATABASE[IF EXISIS] 数据库名;`
### 使用
`USE 数据库名;`
## DDL-表操作
### 查询
#### 查询当前所有数据库所有表
`SHOW TABLES;`
#### 查询表结构
`DESC 表名;`
#### 查询指定表的建表语句
`SHOW CREATE TABLE 表名;`
### 创建
```
CREATE TABLE 表名(
	字段1 字段1类型[COMMENT 字段1注释],
	字段2 字段2类型[COMMENT 字段2注释],
	字段3 字段3类型[COMMENT 字段3注释],
	······
	字段n 字段n类型[COMMENT 字段n注释]
)[COMMENT 表注释];
```
- 注：1. 最后一个字段没有逗号
### 数据类型
- MySQL中的数据类型有很多，主要分三类：**数值类型、字符串类型、日期和时间类型**
#### 数值类型
##### TINYINT
- 大小：1 byte
- 有符号(SIGNED)范围：（-128，127）
- 无符号(UNSIGNED)范围：（0，255）
- 小整数值
##### SMALLINT
- 大小：2 byte
- 有符号(SIGNED)范围：（-32768，32767）
- 无符号(UNSIGNED)范围：（0，65535）
- 大整数值
##### MEDIUMINT
- 大小：3 byte
- 有符号(SIGNED)范围：（-8388608，8388607）
- 无符号(UNSIGNED)范围：（0，16777215）
- 大整数值
##### INT || INTEGER
- 大小：4 byte
- 大整数值
##### BIGINT
- 大小：8 byte
- 极大整数值
##### FLOAT
- 大小：4 byte
- 单精度浮点数值
##### DOUBLE
- 大小：8 byte
- 双精度浮点数值
##### DECIMAL
- 大小：
- 依赖于M精度和D标度
#### 字符串类型
![[字符串类型图示.png]]
#### 时间&日期类型
![[时间日期数据类型.png]]
### 修改
#### 添加字段
`ALTER 表名 ADD 字段名 类型(长度) [COMMENT 注释] [约束];`
#### 修改数据类型
`ALTER TABLE 表名 MODIFY 字段名 新数据类型(长度);`
#### 修改字段名和字段类型
`ALTER 表名 CHANGE 旧字段名 新字段名 类型(长度) [COMMENT 注释] [约束];`
#### 删除字段
ALTER TABLE 表名 DROP 字段名;
#### 修改表名
`ALTER TABLE 表名 RENAME TO 新表名;`
### 删除
#### 删除表
`DROP TABLE[IF EXISTS] 表名;`
#### 删除指定表，并重新创建该表
`TRUNCATE TABLE 表名;`
- 删除表时，**表中的数据也会被一并删除**
# DML
## DML-介绍
- DML英文全称是Data Manipulation Language（数据操作语言），用来对**数据库中表**的数据记录进行**增删改**操作
## DML-操作
### 显示表
`SELECT * FROM EMPLOYEE;`
### 添加数据
- INSERT
1. 给指定字段添加数据
`INSERT INTO 表名(字段名1， 字段名2···）VALUES(值1，值2,......);`
2. 给全部字段添加数据
`INSERT INTO 表名 VALUES(值1，值2...);`
3. 批量添加数据
`INSERT INTO 表名(字段名1，字段名2...) VALUES(值1，值2...),(值1，值2，...),(值1，值2...);`
`INSERT INTO 表名 VALUES(值1，值2...),(值1，值2，...),(值1，值2...);`
#### 注意
- 插入数据时，指定的字段顺序与值的顺序是一一对应的
- 字符串和日期数据应包含在引号中
- 插入的数据大小，应该在字段的规定范围内
### 修改数据
- UPDATE
`UPDATE 表名 SET 字段名1 = 值1， 字段名2 = 值2，...[WHERE 条件]`
注：修改语句的条件可以有，也可以没有，如果没有条件，则会修改整张表的所有数据
### 删除数据
- DELETE
`DELETE FROM 表名 [WHERE 条件]`
注：
- DELETE 语句的条件可以有，也可以没有，没有条件，删除整张表的数据
- DELETE 语句不能删除某一个字段的值（可以使用UPDATE）

# DQL

# DCL
