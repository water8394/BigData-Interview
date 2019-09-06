## HMaster宕机的时候,哪些操作还能正常工作

对表内数据的增删查改是可以正常进行的,因为hbase client 访问数据只需要通过 zookeeper 来找到 rowkey 的具体 region 位置即可. 但是对于创建表/删除表等的操作就无法进行了,因为这时候是需要HMaster介入, 并且region的拆分,合并,迁移等操作也都无法进行了

