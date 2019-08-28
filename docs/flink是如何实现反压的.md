## flink是如何实现反压的

flink的反压经历了两个发展阶段,分别是基于TCP的反压(<1.5)和基于credit的反压(>1.5)

- #### 基于 TCP 的反压

  flink中的消息发送通过RS(ResultPartition),消息接收通过IC(InputGate),两者的数据都是以 LocalBufferPool的形式来存储和提取,进一步的依托于Netty的NetworkBufferPool,之后更底层的便是依托于TCP的滑动窗口机制,当IC端的buffer池满了之后,两个task之间的滑动窗口大小便为0,此时RS端便无法再发送数据

  基于TCP的反压最大的问题是会造成整个TaskManager端的反压,所有的task都会受到影响

- #### 基于 Credit 的反压

  RS与IC之间通过backlog和credit来确定双方可以发送和接受的数据量的大小以提前感知,而不是通过TCP滑动窗口的形式来确定buffer的大小之后再进行反压

  ![](D:\Note\big-data-interview\BigData-Interview\pictures\flink基于credit的反压.png)



[参考视频](<https://www.bilibili.com/video/av55487329>)

[参考文章1](<https://blog.csdn.net/u010376788/article/details/92086752>)

[参考文章2](<https://blog.csdn.net/u010376788/article/details/95047250>)

