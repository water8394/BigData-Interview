#### 🚩最近晚上打算抽些时间做点兼职工作，计划帮助刚进入这行的同学或者应届生同学修改简历并提供面试指导
#### 🚩本人目前为一线大厂大数据开发工程师，有意的同学可以联系VX：DongniVirgo
--- 

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

11. [hadoop的常用配置文件有哪些,自己实际改过哪些?](./docs/hadoop的常用配置文件有哪些.md)

12. [小文件过多会有什么危害,如何避免?](./docs/小文件过多会有什么危害.md)

13. [启动hadoop集群会分别启动哪些进程,各自的作用](./docs/启动hadoop集群会分别启动哪些进程.md)

14. 讲一下环形缓冲区的概念

    

## 二、Hive

1. [hive 内部表和外部表的区别](./docs/hive内部表和外部表的区别.md)

2. [hive中 sort by / order by / cluster by / distribute by 的区别](./docs/hive四种排序方式的区别.md)

3. [hive的metastore的三种模式](./docs/hive的metastore的三种模式.md)

4. [hive 中 join都有哪些](./docs/hive中join都有哪些.md)

5. [Impala 和 hive 的查询有哪些区别](./docs/Impala和hive的查询有哪些区别.md)

6. [Hive中大表join小表的优化方法](./docs/Hive中大表join小表的优化方法.md)

7. [Hive Sql 是怎样解析成MR job的?](./docs/HiveToMR.md)

8. [Hive UDF简单介绍](./docs/HiveUDF简单介绍.md)

9. [SQL题: 按照学生科目分组, 取每个科目的TopN](./docs/按照学生科目取每个科目的TopN.md)

10. [SQL题: 获取每个用户的前1/4次的数据](./docs/获取每个用户的前1/4次的数据.md)

    

## 三、Spark

1. [讲一下spark 的运行架构](./docs/讲一下spark的运行架构.md)
2. [一个spark程序的执行流程](./docs/一个spark程序的执行流程.md)
3. [spark的shuffle介绍](./docs/spark的shuffle介绍.md)
4. [Spark的 partitioner 都有哪些?](./docs/Spark的partitioner都有哪些.md)
5. [spark 有哪几种join](./docs/spark有哪几种join.md)
6. [RDD有哪些特点](./docs/RDD有哪些特点.md)
7. [讲一下宽依赖和窄依赖](./docs/讲一下宽依赖和窄依赖.md)
8. [Spark中的算子都有哪些](./docs/Spark中的算子都有哪些.md)
9. [RDD的缓存级别都有哪些](./docs/RDD的缓存级别都有哪些.md)
10. [RDD 懒加载是什么意思](./docs/RDD懒加载是什么意思.md)
11. [讲一下spark的几种部署方式](./docs/讲一下spark的几种部署方式.md)
12. [spark on yarn 模式下的 cluster模式和 client模式有什么区别](./docs/spark中cluster模式和client模式有什么区别.md)
13. [spark运行原理,从提交一个jar到最后返回结果,整个过程](./docs/spark从提交一个jar到最后返回结果.md)
14. [spark的stage是如何划分的](./docs/spark的stage是如何划分的.md)
15. [spark的rpc: spark2.0为什么放弃了akka 而用netty?](./docs/spark2.0为什么放弃了akka而用netty.md)
16. [spark的各种HA,  master/worker/executor/driver/task的ha](./docs/spark的各种HA.md)
17. [spark的内存管理机制,spark 1.6前后分析对比, spark2.0 做出来哪些优化](./docs/spark的内存管理机制.md)
18. [讲一下spark 中的广播变量](./docs/spark中的广播变量.md)
19. [什么是数据倾斜,怎样去处理数据倾斜](./docs/怎样去处理数据倾斜.md)
20. [分析一下一段spark代码中哪些部分在Driver端执行,哪些部分在Worker端执行](./docs/分析一下一段spark代码中哪些部分在Driver端执行.md)

## 四、Flink

1. [讲一下flink的运行架构](./docs/讲一下flink的运行架构.md)

2. [讲一下flink的作业执行流程](./docs/讲一下flink的作业执行流程.md)

3. [flink具体是如何实现exactly once 语义](./docs/flink具体是如何实现exactlyonce语义.md)

4. [flink 的 window 实现机制](./docs/flink的window实现机制.md)

5. [flink的window分类](./docs/flink的window分类.md)

6. [flink 的 state 是存储在哪里的](./docs/flink的state是存储在哪里的.md)

7. [flink是如何实现反压的](./docs/flink是如何实现反压的.md)

8. [flink的部署模式都有哪些](./docs/flink的部署模式都有哪些.md)

9. [讲一下flink on yarn的部署](./docs/讲一下flinkonyarn的部署.md)

10. [flink中的时间概念 , eventTime 和 processTime的区别](./docs/flink中的时间概念.md)

11. [flink中的session Window怎样使用](./docs/flink中的sessionWindow怎样使用.md)

    


## 五、HBase

1. [讲一下 Hbase 架构](./docs/讲一下Hbase架构.md)
2. [hbase 如何设计 rowkey](./docs/hbase如何设计rowkey.md)
3. [讲一下hbase的存储结构,这样的存储结构有什么优缺点](./docs/讲一下hbase的存储结构.md)
4. [hbase的HA实现,zookeeper在其中的作用](./docs/hbase的HA实现.md)
5. [HMaster宕机的时候,哪些操作还能正常工作](./docs/HMaster宕机.md)
6. [讲一下hbase的写数据的流程](./docs/讲一下hbase的写数据的流程.md)
7. [讲一下hbase读数据的流程](./docs/讲一下hbase读数据的流程.md)

## 六、Kafka

1. [讲一下 kafka 的架构](./docs/讲一下kafka的架构.md)

2. [kafka 与其他消息组件对比?](./docs/kafka与其他消息组件对比.md)

3. [kafka 实现高吞吐的原理](./docs/kafka实现高吞吐的原理.md)

4. [kafka怎样保证不重复消费](./docs/kafka怎样保证不重复消费.md)

5. [kafka怎样保证不丢失消息](./docs/kafka怎样保证不丢失消息.md)

6. [kafka 与 spark streaming 集成,如何保证 exactly once 语义](./docs/kafka与sparkstreaming集成.md)

7. [ack 有哪几种, 生产中怎样选择?](./docs/ack有哪几种.md)

8. [如何通过 offset 寻找数据](./docs/如何通过offset寻找数据.md)

9. [如何清理过期数据](./docs/如何清理过期数据.md)

10. [1条message中包含哪些信息](./docs/1条message中包含哪些信息.md)

11. [讲一下zookeeper在kafka中的作用](./docs/讲一下zookeeper在kafka中的作用.md)

12. [kafka 可以脱离 zookeeper 单独使用吗](./docs/kafka可以脱离zookeeper单独使用吗.md)

13. [kafka有几种数据保留策略](./docs/kafka有几种数据保留策略.md)

14. [kafka同时设置了7天和10G清除数据,到第5天的时候消息到达了10G,这个时候kafka如何处理?](./docs/kafka同时设置了7天和10G清除数据.md)

    

## 七、Zookeeper

1. [zookeeper是什么,都有哪些功能](./docs/zookeeper是什么.md)
2. [zk 有几种部署模式](./docs/zk有几种部署模式.md)
3. [zk 是怎样保证主从节点的状态同步](./docs/zk是怎样保证主从节点的状态同步.md)
4. [说一下 zk 的通知机制](./docs/说一下zk的通知机制.md)
5. [zk 的分布式锁实现方式](./docs/zk的分布式锁实现方式.md)
6. [zk 采用的哪种分布式一致性协议? 还有哪些分布式一致性协议](./docs/大数据生态圈还有哪些选举协议.md)
7. [讲一下leader 选举过程](./docs/讲一下leader选举过程.md)

