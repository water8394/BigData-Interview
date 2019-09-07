## 如何通过offset寻找数据

如果consumer要找offset是1008的消息，那么，

1，按照二分法找到小于1008的segment，也就是00000000000000001000.log和00000000000000001000.index

2，用目标offset减去文件名中的offset得到消息在这个segment中的偏移量。也就是1008-1000=8，偏移量是8。

3，再次用二分法在index文件中找到对应的索引，也就是第三行6,45。

4，到log文件中，从偏移量45的位置开始（实际上这里的消息offset是1006），顺序查找，直到找到offset为1008的消息。查找期间kafka是按照log的存储格式来判断一条消息是否结束的。

[参考文章](<https://blog.csdn.net/lkforce/article/details/77854813>)

