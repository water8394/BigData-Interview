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

4. Yarn 调度MapReduce

5. hdfs读写流程

6. hdfs创建一个文件的流程

7. hadoop1.x 和hadoop 2.x 的区别

8. hadoop HA介绍

9. hadoop的配置文件有哪些,自己实际改过哪些?

10. 小文件过多会有什么危害,如何避免?

11. 启动hadoop集群会分别启动哪些进程,各自的作用

    

## 二、Hive

1. hive 内部表和外部表的区别

2. hive中 sort by / order by 的区别

3. 写HQL: 两张表-> 一张歌曲表,一张专辑表,找出每张专辑的Top100

4. hive的metastore的三种模式

5. hive 中 join都有哪些

6. Impala 和 hive 的查询有哪些区别

7. Hive中大表join小表的优化方法

8. Hive Sql 是怎样解析成MR job的

9. Hive UDF

   

## 三、Spark

1. spark shuffle 介绍
2. Spark的 partitioner 都有哪些,怎样实现的
3. spark 有哪几种join,使用场景以及实现原理
4. DAGschedular/Taskscheduler/Schedulerbankend的实现原理
5. RDD有哪些特点
6. 讲一下宽依赖和窄依赖
7. Spark中的算子都有哪些
8. RDD的缓存级别都有哪些
9. RDD 懒加载是什么意思
10. spark的工作机制,都有哪些角色
11. spark on yarn 模式下的 cluster模式和 client模式有什么区别
12. spark运行原理,从提交一个jar到最后返回结果,整个过程
13. spark的stage是如何划分的
14. spark的rpc: spark2.0为什么放弃了akka 而用netty?
15. spark的各种HA,  master/worker/executor/driver/task的ha
16. spark的内存管理机制,spark 1.6前后分析对比, spark2.0 做出来哪些优化
17. tungsten引擎: cpu和内存两方面分别说明
18. 讲一下spark 中的广播变量
19. 什么是数据倾斜
20. 怎样去处理数据倾斜

## 四、Flink

1. flink 的 window 实现机制

2. flink 的 state 实现机制

3. flink中的时间概念 , eventTime 和 processTime的区别

   

## 五、HBase

1. hbase 如何设计 rowkey
2. hbase 如何利用 phoniex 实现二级索引
3. 讲一下 Hbase 架构
4. hbase 设计的优缺点,对比 nosql 和 关系型数据库
5. hbase的HA实现,zookeeper在其中的作用
6. master宕机的时候,哪些操作还能正常工作
7. hbase的读写流程

## 六、Kafka

1. kafka 相比其他消息组件有什么好处?

2. kafka 实现高吞吐的原理

3. kafka 的消息传递语义 / kafka怎样保证数据的一致性

4. kafka 与 spark streaming 集成,如何保证 exactly once 语义

5. ack 有哪几种, 生产中怎样选择?

6. 如何通过 offset 寻找数据

7. 生产者/消费者 各如何监控数据及时消费

8. kafk 的 ISR 机制

9. 如何清理过期数据

10. 1条message中包含哪些信息

11. kafka 可以脱离 zookeeper 单独使用吗

12. kafka有几种数据保留策略

13. kafka同时设置了7天和10G清除数据,到第5天的时候消息到达了10G,这个时候kafka如何处理?

    

## 七、Zookeeper

1. zookeeper是什么
2. zk都有哪些功能
3. zk 有几种部署模式
4. zk 是怎样保证主从节点的状态同步
5. 说一下 zk 的通知机制
6. zk 的分布式锁实现方式
7. zk 采用的哪种 选举协议? 大数据生态圈还有哪些选举协议
8. 有 ABCDE 五台机器,讲一下leader 选举过程