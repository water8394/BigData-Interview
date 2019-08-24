## MapReduce过程

MapReduce分为两个阶段: **Map** 和  **Ruduce**.

**Map阶段:**

1. **input**. 在进行map计算之前，mapreduce会根据输入文件计算输入分片（input split），每个输入分片（input split）针对一个map任务
2. **map**. 就是程序员编写好的map函数了，因此map函数效率相对好控制，而且一般map操作都是本地化操作也就是在数据存储节点上进行
3. **Partition**. 需要计算每一个map的结果需要发到哪个reduce端,partition数等于reducer数.默认采用HashPartition.
4. **spill**.此阶段分为sort和combine.首先分区过得数据会经过排序之后写入环形内存缓冲区.在达到阈值之后守护线程将数据溢出分区文件.
   - **sort**. 在写入环形缓冲区前,对数据排序.<key,value,partition>格式排序
   - **combine**(可选). 在溢出文件之前,提前开始combine,相当于本地化的reduce操作

5. **merge.** spill结果会有很多个文件,但最终输出只有一个,故有一个merge操作会合并所有的本地文件,并且该文件会有一个对应的索引文件.

**Reduce阶段:**

1. **copy**. 拉取数据,reduce启动数据copy线程(默认5个),通过Http请求对应节点的map task输出文件,copy的数据也会先放到内部缓冲区.之后再溢写,类似map端操作.
2. **merge**. 合并多个copy的多个map端的数据.在一个reduce端先将多个map端的数据溢写到本地磁盘,之后再将多个文件合并成一个文件.  数据经过 **内存->磁盘 , 磁盘->磁盘**的过程.
3. **output**.merge阶段最后会生成一个文件,将此文件转移到内存中,shuffle阶段结束
4. **reduce**. 开始执行reduce任务,最后结果保留在hdfs上.

