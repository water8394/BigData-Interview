## kafka 与 spark streaming 集成,如何保证 exactly once 语义

- ### Spark Streaming上游对接kafka时保证Exactly Once

  Spark Streaming使用Direct模式对接上游kafka。无论kafka有多少个partition， 使用Direct模式总能保证SS中有相同数量的partition与之相对， 也就是说SS中的KafkaRDD的并发数量在Direct模式下是由上游kafka决定的。 在这个模式下，kafka的offset是作为KafkaRDD的一部分存在，会存储在checkpoints中， 由于checkpoints只存储offset内容，而不存储数据，这就使得checkpoints是相对轻的操作。 这就使得SS在遇到故障时，可以从checkpoint中恢复上游kafka的offset，从而保证exactly once

- ### Spark Streaming输出下游保证Exactly once

  - 第一种“鸵鸟做法”，就是期望下游（数据）具有幂等特性。

    多次尝试总是写入相同的数据，例如，saveAs***Files 总是将相同的数据写入生成的文件

- - 使用事务更新

    所有更新都是事务性的，以便更新完全按原子进行。这样做的一个方法如下： 使用批处理时间(在foreachRDD中可用)和RDD的partitionIndex（分区索引）来创建identifier（标识符)。 该标识符唯一地标识streaming application 中的blob数据。 使用该identifier，blob 事务地更新到外部系统中。也就是说，如果identifier尚未提交，则以 (atomicall)原子方式提交分区数据和identifier。否则，如果已经提交，请跳过更新。



[参考文章1](<http://www.aihacks.life/post/spark-streaming%E5%A6%82%E4%BD%95%E4%BF%9D%E8%AF%81exactly-once%E8%AF%AD%E4%B9%89/>)

[参考文章2](<https://www.jianshu.com/p/10de8f3b1be8>)

[参考文章3](<https://blog.csdn.net/cymvp/article/details/52605987>)

