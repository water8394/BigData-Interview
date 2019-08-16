## Spark的 partitioner 都有哪些?

**Partitioner主要有两个实现类：HashPartitioner和RangePartitioner,HashPartitioner是大部分transformation的默认实现，sortBy、sortByKey使用RangePartitioner实现，也可以自定义Partitioner.**

- **HashPartitioner**

  numPartitions方法返回传入的分区数，getPartition方法使用key的hashCode值对分区数取模得到PartitionId，写入到对应的bucket中。

- **RangePartitioner**

  RangePartitioner是先根据所有partition中数据的分布情况，尽可能均匀地构造出重分区的分隔符，再将数据的key值根据分隔符进行重新分区

  - 使用reservoir Sample方法对每个Partition进行分别抽样
  - 对数据量大(大于sampleSizePerPartition)的分区进行重新抽样
  - 由权重信息计算出分区分隔符rangeBounds
  - 由rangeBounds计算分区数和key的所属分区



[参考文章](<https://blog.csdn.net/qq_34842671/article/details/83685179>)