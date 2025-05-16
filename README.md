创新小组DBMS用户手册
一、软件简介
CXSQL 是一款数据库管理系统，支持数据库的创建、数据库表的管理、记录的添加与查询、完整性约束的实现、索引的创建与实现以及多用户等功能。用户可以使用 SQL 语句（包括 DDL、DML、DCL）来控制数据库，定义数据库的模式结构与权限约束，实现对数据的追加、删除等操作。


二、项目版本要求
gcc：13.1.1，使用 c++17 标准
qt：5.15.9
cmake：3.26.3
qmake：3.1


三、用户使用办法
1.注册

点击注册

注册好后用户信息会被保存。
2.基本使用

（一）数据库操作
1.创建数据库

sql
CREATE DATABASE database_name;


2.删除数据库

sql
DROP DATABASE database_name;


3.使用数据库

sql
USE database_name;
（二）表操作
1.创建表

sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...
);


2.删除表

sql
DROP TABLE table_name;


3.查看表结构

sql
DESCRIBE table_name;
（三）记录操作
1.插入记录

sql
INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...);


2.查询记录

sql
SELECT column1, column2, ... FROM table_name WHERE condition;


3.更新记录

sql
UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition;


4.删除记录

sql
DELETE FROM table_name WHERE condition;
（四）用户与权限操作
1.创建用户

sql
CREATE USER user_name IDENTIFIED BY password;



2.授予权限

sql
GRANT privilege_type ON database_name.table_name TO user_name;



3.撤销权限

sql
REVOKE privilege_type ON database_name.table_name FROM user_name;


也可以直接在UI上点击来创建新表或者数据库

四、GUI 操作说明
GUI 界面提供了图形化操作方式，方便用户进行数据库操作。主要功能按钮及操作如下：


创建库：点击相应按钮，输入数据库名称，即可创建新的数据库。
创建表：点击按钮后，在弹出界面输入表名和字段信息，创建新表。
创建记录：选择表后，点击按钮，输入记录信息进行添加。
新建索引：选择表和字段，创建索引以提高查询效率。
删除数据库：选择要删除的数据库，点击按钮进行删除。
删除表：选择表后，点击按钮删除该表。
复杂查询：点击按钮，输入复杂的查询条件进行数据查询。
执行.sql 文件：点击按钮，选择 SQL 脚本文件进行执行。
切换用户：点击按钮，返回登录界面，可切换不同用户登录。


五、常见问题解答（FAQ）
（一）有关 #include<filemanager> 的编译错误
gcc 在 c++17 中支持了 filemanager 库，但 qt5 在 c++17 中只支持 experimental/filemanager，需要根据环境具体决定。可以在 file/src/filemanager.cpp 中修改对应内容。
（二）关键字 NULL 的使用
NULL 为 Co1aSQL 关键字，若在 SQL 语句中占用该关键字，可能不一定能得到预期结果，请避免在关键位置使用。
六、注意事项
请确保你的开发环境满足项目版本要求，否则可能会出现编译或运行错误。
在进行数据库和表的删除操作时，请谨慎操作，因为删除后的数据将无法恢复。
使用 SQL 语句时，请遵循 SQL 语法规则，避免出现语法错误。
