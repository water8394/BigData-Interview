## Spark中的算子都有哪些

总的来说,spark分为两大类算子:

- **Transformation 变换/转换算子：这种变换并不触发提交作业，完成作业中间过程处理**

  Transformation 操作是延迟计算的，也就是说从一个RDD 转换生成另一个 RDD 的转换操作不是马上执行，需要等到有 Action 操作的时候才会真正触发运算

- **Action 行动算子：这类算子会触发 SparkContext 提交 Job 作业**

  Action 算子会触发 Spark 提交作业（Job），并将数据输出 Spark系统

  ------

#### 1. Value数据类型的Transformation算子

- 输入分区与输出分区一对一型
  - map算子
  - flatMap算子
  - mapPartitions算子
  - glom算子

- 输入分区与输出分区多对一型
  - union算子
  - cartesian算子

- 输入分区与输出分区多对多型
  - grouBy算子

- 输出分区为输入分区子集型
  - filter算子
  - distinct算子
  - subtract算子
  - sample算子
  - takeSample算子

- Cache型
  - cache算子
  - persist算子

#### 2. Key-Value数据类型的Transfromation算子

- 输入分区与输出分区一对一
  - mapValues算子

- 对单个RDD或两个RDD聚集
  - combineByKey算子
  - reduceByKey算子
  - partitionBy算子
  - Cogroup算子

- 连接
  - join算子
  - leftOutJoin 和 rightOutJoin算子

#### 3. Action算子

- 无输出
  - foreach算子

- HDFS算子
  - saveAsTextFile算子
  - saveAsObjectFile算子

- Scala集合和数据类型
  - collect算子
  - collectAsMap算子
  - reduceByKeyLocally算子
  - lookup算子
  - count算子
  - top算子
  - reduce算子
  - fold算子
  - aggregate算子
  - countByValue
  - countByKey





[参考文章](<https://www.cnblogs.com/kpsmile/p/10434390.html>)
