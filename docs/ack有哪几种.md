## Ack 有哪几种, 生产中怎样选择?

ack=0/1/-1的不同情况：

- Ack = 0

  producer不等待broker的ack，broker一接收到还没有写入磁盘就已经返回，当broker故障时有可能丢失数据；

- Ack = 1

  producer等待broker的ack，partition的leader落盘成功后返回ack，如果在follower同步成功之前leader故障，那么将会丢失数据；

- Ack = -1

  producer等待broker的ack，partition的leader和follower全部落盘成功后才返回ack，数据一般不会丢失，延迟时间长但是可靠性高。

**生产中主要以 Ack=-1为主,如果压力过大,可切换为Ack=1. Ack=0的情况只能在测试中使用.**

