## RDD的缓存级别都有哪些

NONE :什么类型都不是
DISK_ONLY：磁盘
DISK_ONLY_2：磁盘；双副本
MEMORY_ONLY： 内存；反序列化；把RDD作为反序列化的方式存储，假如RDD的内容存不下，剩余的分区在以后需要时会重新计算，不会刷到磁盘上。
MEMORY_ONLY_2：内存；反序列化；双副本
MEMORY_ONLY_SER：内存；序列化；这种序列化方式，每一个partition以字节数据存储，好处是能带来更好的空间存储，但CPU耗费高
MEMORY_ONLY_SER_2 : 内存；序列化；双副本
MEMORY_AND_DISK：内存 + 磁盘；反序列化；双副本；RDD以反序列化的方式存内存，假如RDD的内容存不下，剩余的会存到磁盘
MEMORY_AND_DISK_2 : 内存 + 磁盘；反序列化；双副本
MEMORY_AND_DISK_SER：内存 + 磁盘；序列化  
MEMORY_AND_DISK_SER_2：内存 + 磁盘；序列化；双副本