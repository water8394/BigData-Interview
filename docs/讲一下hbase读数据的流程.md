## 讲一下hbase读数据的流程

1. 首先，客户端需要获知其想要读取的信息的Region的位置，这个时候，Client访问hbase上数据时并不需要Hmaster参与（HMaster仅仅维护着table和Region的元数据信息，负载很低），只需要访问zookeeper，从meta表获取相应region信息(地址和端口等)。【Client请求ZK获取.META.所在的RegionServer的地址。】

2. 客户端会将该保存着RegionServer的位置信息的元数据表.META.进行缓存。然后在表中确定待检索rowkey所在的RegionServer信息（得到持有对应行键的.META表的服务器名）。【获取访问数据所在的RegionServer地址】

3. 根据数据所在RegionServer的访问信息，客户端会向该RegionServer发送真正的数据读取请求。服务器端接收到该请求之后需要进行复杂的处理。

4. 先从MemStore找数据，如果没有，再到StoreFile上读(为了读取的效率)。



[参考文章1](<https://blog.csdn.net/HaixWang/article/details/79520141#%E8%AF%BB%E6%B5%81%E7%A8%8B%E6%A6%82%E8%A7%88>)

[参考文章2](<http://hbasefly.com/2016/12/21/hbase-getorscan/?rkfcfo=fy6gy1>)