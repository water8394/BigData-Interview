## spark的内存管理机制

**spark的内存结构分为3大块:storage/execution/系统自留**

- **storage 内存**：用于缓存 RDD、展开 partition、存放 Direct Task Result、存放广播变量。在 Spark Streaming receiver 模式中，也用来存放每个 batch 的 blocks

- **execution 内存**：用于 shuffle、join、sort、aggregation 中的缓存、buffer

- **系统自留**:

  - 在 spark 运行过程中使用：比如序列化及反序列化使用的内存，各个对象、元数据、临时变量使用的内存，函数调用使用的堆栈等

  - 作为误差缓冲：由于 storage 和 execution 中有很多内存的使用是估算的，存在误差。当 storage 或 execution 内存使用超出其最大限制时，有这样一个安全的误差缓冲在可以大大减小 OOM 的概率

  

------

#### 1.6版本以前的问题

- 旧方案最大的问题是 storage 和 execution 的内存大小都是固定的，不可改变，即使 execution 有大量的空闲内存且 storage 内存不足，storage 也无法使用 execution 的内存，只能进行 spill，反之亦然。所以，在很多情况下存在资源浪费
- 旧方案中，只有 execution 内存支持 off heap，storage 内存不支持 off heap

#### 新方案的改进

- 新方案 storage 和 execution 内存可以互相借用，当一方内存不足可以向另一方借用内存，提高了整体的资源利用率
- 新方案中 execution 内存和 storage 内存均支持 off heap

