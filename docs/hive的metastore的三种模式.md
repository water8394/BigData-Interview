## hive的metastore的三种模式

- **内嵌Derby方式**

  这个是Hive默认的启动模式，一般用于单元测试，这种存储方式有一个缺点：在同一时间只能有一个进程连接使用数据库。

- **Local方式**

  本地MySQL

- **Remote方式**

  远程MySQL,一般常用此种方式



[参考文章](<https://blog.csdn.net/baolibin528/article/details/46710025>)