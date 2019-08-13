## Yarn 调度MapReduce过程

![](../picturees/yarn调度mr过程.jpg)

1. Mr程序提交到客户端所在的节点（MapReduce）
2. yarnrunner向Resourcemanager申请一个application。
3. rm将该应用程序的资源路径返回给yarnrunner
4. 该程序将运行所需资源提交到HDFS上
5. 程序资源提交完毕后，申请运行mrAppMaster
6. RM将用户的请求初始化成一个task
7. 其中一个NodeManager领取到task任务。
8. 该NodeManager创建容器Container，并产生MRAppmaster
9. Container从HDFS上拷贝资源到本地
10. MRAppmaster向RM申请运行maptask容器
11. RM将运行maptask任务分配给另外两个NodeManager，另两个NodeManager分别领取任务并创建容器.
12. MR向两个接收到任务的NodeManager发送程序启动脚本，这两个NodeManager分别启动maptask，maptask对数据分区排序。
13. MRAppmaster向RM申请2个容器，运行reduce task。
14. reduce task向maptask获取相应分区的数据。
15. 程序运行完毕后，MR会向RM注销自己。

[参考文章](<https://blog.csdn.net/qq_26442553/article/details/78699759>)