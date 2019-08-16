#### 大数据面试题汇总与答案分享

------

<table>
    <tr>
     <th><img width="50px" src="./pictures/hadoop.jpg"></th>
     <th><img width="50px" src="./pictures/hive.jpg"></th>
     <th><img width="50px" src="./pictures/spark.jpg"></th>
     <th><img width="50px" src="./pictures/flink.png"></th>
     <th><img width="50px" src="./pictures/hbase.png"></th>
     <th><img width="50px" src="./pictures/kafka.png"></th>
     <th><img width="50px" src="./pictures/zookeeper.jpg"></th>
    </tr>
<tr>
  <td align="center"><a href="#一hadoop">Hadoop</a></td>
  <td align="center"><a href="#二hive">Hive</a></td>
  <td align="center"><a href="#三spark">Spark</a></td>
  <td align="center"><a href="#四flink">Flink</a></td>
  <td align="center"><a href="#五hbase">HBase</a></td>
  <td align="center"><a href="#六kafka">Kafka</a></td>
  <td align="center"><a href="#七zookeeper">Zookeeper</a></td>
</tr>
    </table>


## 一、Hadoop

1. [HDFS架构](./docs/HDFS架构.md)

2. [Yarn架构](./docs/Yarn架构.md)

3. [MapReduce过程](./docs/MapReduce过程.md)

4. [Yarn 调度MapReduce](./docs/Yarn调度MapReduce.md)

5. [hdfs写流程](./docs/hdfs写流程.md)

6. [hdfs读流程](./docs/hdfs读流程.md)

7. [hdfs创建一个文件的流程](./docs/hdfs创建一个文件的流程.md)

8. [hadoop1.x 和hadoop 2.x 的区别](./docs/hadoop1.x和hadoop2.x的区别.md)

9. [hadoop1.x的缺点](./docs/hadoop1.x的缺点.md)

10. [hadoop HA介绍](./docs/hadoopHA介绍.md)

11. hadoop的配置文件有哪些,自己实际改过哪些?

12. 小文件过多会有什么危害,如何避免?

13. 启动hadoop集群会分别启动哪些进程,各自的作用

    

## 二、Hive

1. [hive 内部表和外部表的区别](./docs/hive内部表和外部表的区别.md)

2. [hive中 sort by / order by / cluster by / distribute by 的区别](./docs/hive四种排序方式的区别.md)

3. 写HQL: 两张表-> 一张歌曲表,一张专辑表,找出每张专辑的Top100

4. hive的metastore的三种模式

5. [hive 中 join都有哪些](./docs/hive中join都有哪些.md)

6. Impala 和 hive 的查询有哪些区别

7. Hive中大表join小表的优化方法

8. [Hive Sql 是怎样解析成MR job的?](./docs/HiveToMR.md)

9. Hive UDF

   

## 三、Spark

1. [讲一下spark 的运行架构](./docs/讲一下spark的运行架构.md)
2. [一个spark程序的执行流程](./docs/一个spark程序的执行流程.md)
3. [spark的shuffle介绍](./docs/spark的shuffle介绍.md)
4. Spark的 partitioner 都有哪些,怎样实现的
5. [spark 有哪几种join](./docs/spark有哪几种join.md)
6. DAGschedular/Taskscheduler/Schedulerbankend的实现原理
7. [RDD有哪些特点](./docs/RDD有哪些特点.md)
8. 讲一下宽依赖和窄依赖
9. Spark中的算子都有哪些
10. RDD的缓存级别都有哪些
11. RDD 懒加载是什么意思
12. [讲一下spark的几种部署方式](./docs/讲一下spark的几种部署方式.md)
13. [spark on yarn 模式下的 cluster模式和 client模式有什么区别](./docs/spark中cluster模式和client模式有什么区别.md)
14. [spark运行原理,从提交一个jar到最后返回结果,整个过程](./docs/spark从提交一个jar到最后返回结果.md)
15. spark的stage是如何划分的
16. [spark的rpc: spark2.0为什么放弃了akka 而用netty?](./docs/spark2.0为什么放弃了akka而用netty.md)
17. spark的各种HA,  master/worker/executor/driver/task的ha
18. spark的内存管理机制,spark 1.6前后分析对比, spark2.0 做出来哪些优化
19. tungsten引擎: cpu和内存两方面分别说明
20. [讲一下spark 中的广播变量](./docs/spark中的广播变量.md)
21. 什么是数据倾斜
22. 怎样去处理数据倾斜

## 四、Flink

1. [讲一下flink的运行架构](./docs/讲一下flink的运行架构.md)

2. [flink 的 window 实现机制](./docs/flink的window实现机制.md)

3. [flink的window分类](./docs/flink的window分类.md)

4. flink 的 state 实现机制

5. [flink 的 state 是存储在哪里的](./docs/flink的state是存储在哪里的.md)

6. flink中的时间概念 , eventTime 和 processTime的区别

   

## 五、HBase

1. [讲一下 Hbase 架构](./docs/讲一下Hbase架构.md)
2. [hbase 如何设计 rowkey](./docs/hbase如何设计rowkey.md)
3. hbase 如何利用 phoniex 实现二级索引
4. hbase 设计的优缺点,对比 nosql 和 关系型数据库
5. hbase的HA实现,zookeeper在其中的作用
6. master宕机的时候,哪些操作还能正常工作
7. hbase的读写流程

## 六、Kafka

1. [讲一下 kafka 的架构](./docs/讲一下kafka的架构.md)

2. kafka 相比其他消息组件有什么好处?

3. kafka 实现高吞吐的原理

4. kafka 的消息传递语义 / kafka怎样保证数据的一致性

5. kafka 与 spark streaming 集成,如何保证 exactly once 语义

6. ack 有哪几种, 生产中怎样选择?

7. 如何通过 offset 寻找数据

8. 生产者/消费者 各如何监控数据及时消费

9. kafk 的 ISR 机制

10. 如何清理过期数据

11. 1条message中包含哪些信息

12. [讲一下zookeeper在kafka中的作用](./docs/讲一下zookeeper在kafka中的作用.md)

13. kafka 可以脱离 zookeeper 单独使用吗

14. kafka有几种数据保留策略

15. kafka同时设置了7天和10G清除数据,到第5天的时候消息到达了10G,这个时候kafka如何处理?

    

## 七、Zookeeper

1. zookeeper是什么
2. zk都有哪些功能
3. zk 有几种部署模式
4. zk 是怎样保证主从节点的状态同步
5. 说一下 zk 的通知机制
6. zk 的分布式锁实现方式
7. zk 采用的哪种 选举协议? 大数据生态圈还有哪些选举协议
8. [讲一下leader 选举过程](./docs/讲一下leader选举过程.md)

