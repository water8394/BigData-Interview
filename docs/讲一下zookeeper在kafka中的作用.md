## 讲一下zookeeper在kafka中的作用

![](../pictures/kafka在zk中的存储结构.png)



#### zk的作用主要有如下几点:

1. kafka的元数据都存放在zk上面,由zk来管理
2. 0.8之前版本的kafka, consumer的消费状态，group的管理以及 offset的值都是由zk管理的,现在offset会保存在本地topic文件里
3. 负责borker的lead选举和管理

