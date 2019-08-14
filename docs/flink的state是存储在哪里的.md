## flink 的 state 是存储在哪里的

Apache Flink内部有四种state的存储实现，具体如下：

- **基于内存的HeapStateBackend** - 在debug模式使用，不 建议在生产模式下应用；
- **基于HDFS的FsStateBackend** - 分布式文件持久化，每次读写都产生网络IO，整体性能不佳；
- **基于RocksDB的RocksDBStateBackend** - 本地文件+异步HDFS持久化；
- **基于Niagara(Alibaba内部实现)NiagaraStateBackend** - 分布式持久化- 在Alibaba生产环境应用；



[参考文章](<https://juejin.im/post/5c87dbdbe51d45494c77d607>)