## RDD有哪些特点

1. **A list of partitions**
   RDD是一个由多个partition（某个节点里的某一片连续的数据）组成的的list；将数据加载为RDD时，一般会遵循数据的本地性（一般一个hdfs里的block会加载为一个partition）。

2.  **A function for computing each split**
   RDD的每个partition上面都会有function，也就是函数应用，其作用是实现RDD之间partition的转换。

3. **A list of dependencies on other RDDs**
   RDD会记录它的依赖 ，为了容错（重算，cache，checkpoint），也就是说在内存中的RDD操作时出错或丢失会进行重算。

4. **Optionally,a Partitioner for Key-value RDDs**
     可选项，如果RDD里面存的数据是key-value形式，则可以传递一个自定义的Partitioner进行重新分区，例如这里自定义的Partitioner是基于key进行分区，那则会将不同RDD里面的相同key的数据放到同一个partition里面

5. **Optionally, a list of preferred locations to compute each split on**

   最优的位置去计算，也就是数据的本地性。

