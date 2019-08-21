## spark的stage是如何划分的

**stage的划分依据就是看是否产生了shuflle(即宽依赖),遇到一个shuffle操作就划分为前后两个stage.**

![](D:\Note\big-data-interview\BigData-Interview\pictures\stageDivide.jpg)

