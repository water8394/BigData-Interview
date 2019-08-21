## 启动hadoop集群会分别启动哪些进程,各自的作用

- **NameNode：**
  - 维护文件系统树及整棵树内所有的文件和目录。这些信息永久保存在本地磁盘的两个文件中：命名空间镜像文件、编辑日志文件
  - 记录每个文件中各个块所在的数据节点信息，这些信息在内存中保存，每次启动系统时重建这些信息
  - 负责响应客户端的   数据块位置请求  。也就是客户端想存数据，应该往哪些节点的哪些块存；客户端想取数据，应该到哪些节点取
  - 接受记录在数据存取过程中，datanode节点报告过来的故障、损坏信息

- **SecondaryNameNode(非HA模式)：**
  - 实现namenode容错的一种机制。定期合并编辑日志与命名空间镜像，当namenode挂掉时，可通过一定步骤进行上顶。(**注意 并不是NameNode的备用节点**)
- **DataNode：**
  - 根据需要存取并检索数据块
  - 定期向namenode发送其存储的数据块列表
- **ResourceManager：**
  - 负责Job的调度,将一个任务与一个NodeManager相匹配。也就是将一个MapReduce之类的任务分配给一个从节点的NodeManager来执行。
- **NodeManager：**
  - 运行ResourceManager分配的任务，同时将任务进度向application master报告

- **JournalNode(HA下启用):**
  - 高可用情况下存放namenode的editlog文件