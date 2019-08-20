## 分析一下一段spark代码中哪些部分在Driver端执行,哪些部分在Worker端执行

Driver Program是用户编写的提交给Spark集群执行的application，它包含两部分

- **作为驱动**： Driver与Master、Worker协作完成application进程的启动、DAG划分、计算任务封装、计算任务分发到各个计算节点(Worker)、计算资源的分配等。
- **计算逻辑本身**，当计算任务在Worker执行时，执行计算逻辑完成application的计算任务



一般来说transformation算子均是在worker上执行的,其他类型的代码在driver端执行