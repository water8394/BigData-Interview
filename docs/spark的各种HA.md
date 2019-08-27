## spark的各种HA,  master/worker/executor的ha

- #### Master异常

  spark可以在集群运行时启动一个或多个standby Master,当 Master 出现异常时,会根据规则启动某个standby master接管,在standlone模式下有如下几种配置

  - ZOOKEEPER

    集群数据持久化到zk中,当master出现异常时,zk通过选举机制选出新的master,新的master接管是需要从zk获取持久化信息

  - FILESYSTEM

    集群元数据信息持久化到本地文件系统, 当master出现异常时,只需要在该机器上重新启动master,启动后新的master获取持久化信息并根据这些信息恢复集群状态

  - CUSTOM

    自定义恢复方式,对 standloneRecoveryModeFactory 抽象类 进行实现并把该类配置到系统中,当master出现异常时,会根据用户自定义行为恢复集群

  - None

    不持久化集群的元数据, 当 master出现异常时, 新启动的Master 不进行恢复集群状态,而是直接接管集群

- #### Worker异常

  Worker 以定时发送心跳给 Master, 让 Master 知道 Worker 的实时状态,当worker出现超时时,Master 调用 timeOutDeadWorker 方法进行处理,在处理时根据 Worker 运行的是 Executor 和 Driver 分别进行处理

  - 如果是Executor, Master先把该 Worker 上运行的Executor 发送信息ExecutorUpdate给对应的Driver,告知Executor已经丢失,同时把这些Executor从其应用程序列表删除, 另外, 相关Executor的异常也需要处理
  - 如果是Driver, 则判断是否设置重新启动,如果需要,则调用Master.shedule方法进行调度,分配合适节点重启Driver, 如果不需要重启, 则删除该应用程序

- #### Executor异常

  1. Executor发生异常时由ExecutorRunner捕获该异常并发送ExecutorStateChanged信息给Worker
  2. Worker接收到消息时, 在Worker的 handleExecutorStateChanged 方法中, 根据Executor状态进行信息更新,同时把Executor状态发送给Master
  3. Master在接受Executor状态变化消息之后,如果发现其是异常退出,会尝试可用的Worker节点去启动Executor

  