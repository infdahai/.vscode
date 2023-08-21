 
 # chapter 1 初始化
 
 `-l` 列出所有数据库名称。 `-q` 退出 `psql`。

数据目录位于 `/var/lib/postgresql/<dbversino>/main`。

三种关闭数据库的方式，smart，fast和Immediate。smart等待连接中止后关闭数据库。fast快速关闭数据库，断开客户端连接，让已有事务回滚。immediate立即关闭数据库，直接退出，下次启动数据库需要恢复。


# chapter 2 SQL

1.  DQL语句表示数据查询(select)。DML语句指的是data manipulation language，主要指insert，update， delete三种语句。DDL语句指的是数据定义语句，主要用于创建、删除及修改表、索引等语句。
2. `\d` 显示数据库中有哪些表。`\d table_name` 显示表定义。

3. truncate table是ddl语句，将原表内容丢弃，重新创建新表，执行快速。delete则是dml语句，将数据一条一条删除，执行很慢。

## chapter 3 `psql`

1. `\l`查看数据库，`\d`查看表。
2. `\c database` 表示连接到数据库上。
3. 连接命令为 `psql -h ip_addr -p port db_name user_name`
4. `\d+` 相比 `\d` 提供更详细的信息。
5. `\timing` 显示sql已执行时间。（`\timing on`开启计时）
6. `\dn` 列出所有的`schema` 。`\db` 列出所有的表空间。
7. `\encoding` 指定客户端字符编码
8. `\pset`用于设置输出格式，主要与输出时列的下划线排版有关。
9. `\x`将表中每行每列数据拆分成单行显示。、
10. `\i` 命令可以用于执行外部文件中的sql语句。比如在云原生分支上，我们使用该命令可以去调用初始化的脚本来将数据库配置到obs路径上。
11. `psql -f <filename>` 用来执行shell脚本中的命令。
12. `\d?` 用于查询更多的命令，类似于`help`。
13. `\set ECHO_HIDDEN on | off`用于开启是否显示某一个命令实际执行的sql功能。如下图，就是展示了`\dn`实际执行的sql语句。

# chapter 4 数据类型

1. 基本数据类型
2. 类型转换
	1. 类型名 + 单引号'类型值'
	2.  CAST AS
	3.  双冒号
3. 操作符
