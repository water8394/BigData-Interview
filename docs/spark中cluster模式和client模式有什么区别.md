## spark on yarn 模式下的 cluster模式和 client模式有什么区别

1. yarn-cluster 适用于生产环境。而 yarn-client 适用于交互和调试，也就是希望快速地看到 application 的输出.
2.   yarn-cluster 和 yarn-client 模式的区别其实就是 **Application Master 进程**的区别，yarn-cluster 模式下，driver 运行在 AM(Application Master)中，它负责向 YARN 申请资源，并监督作业的运行状况。当用户提交了作业之后，就可以关掉 Client，作业会继续在 YARN 上运行。然而 yarn-cluster 模式不适合运行交互类型的作业。而 yarn-client 模式下，Application Master 仅仅向 YARN 请求 executor，Client 会和请求的container 通信来调度他们工作，也就是说 Client 不能离开。