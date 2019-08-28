## 讲一下hbase的写数据的流程

1. Client先访问zookeeper，从.META.表获取相应region信息，然后从meta表获取相应region信息 
2. 根据namespace、表名和rowkey根据meta表的数据找到写入数据对应的region信息 
3. 找到对应的regionserver 把数据先写到WAL中，即HLog，然后写到MemStore上 
4. MemStore达到设置的阈值后则把数据刷成一个磁盘上的StoreFile文件。 
5. 当多个StoreFile文件达到一定的大小后(这个可以称之为小合并，合并数据可以进行设置，必须大于等于2，小于10——hbase.hstore.compaction.max和hbase.hstore.compactionThreshold，默认为10和3)，会触发Compact合并操作，合并为一个StoreFile，（这里同时进行版本的合并和数据删除。） 
6. 当Storefile大小超过一定阈值后，会把当前的Region分割为两个（Split）【可称之为大合并，该阈值通过hbase.hregion.max.filesize设置，默认为10G】，并由Hmaster分配到相应的HRegionServer，实现负载均衡
   