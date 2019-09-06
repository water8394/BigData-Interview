## kafka 实现高吞吐的原理

- 读写文件依赖OS文件系统的页缓存，而不是在JVM内部缓存数据，利用OS来缓存，内存利用率高
- sendfile技术（零拷贝），避免了传统网络IO四步流程
- 支持End-to-End的压缩
- 顺序IO以及常量时间get、put消息
- Partition 可以很好的横向扩展和提供高并发处理



[参考文章1](<https://www.jianshu.com/p/d6a73be9d803>)

[参考文章2](<https://blog.csdn.net/stark_summer/article/details/50144591>)