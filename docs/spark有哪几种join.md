## spark有哪几种join



**Spark 中和 join 相关的算子有这几个**：`join`、`fullOuterJoin`、`leftOuterJoin`、`rightOuterJoin`

- **join**

  join函数会输出两个RDD中key相同的所有项，并将它们的value联结起来，它联结的key要求在两个表中都存在，类似于SQL中的INNER JOIN。但它不满足交换律，a.join(b)与b.join(a)的结果不完全相同，值插入的顺序与调用关系有关。

- **leftOuterJoin**

  leftOuterJoin会保留对象的所有key，而用None填充在参数RDD other中缺失的值，因此调用顺序会使结果完全不同。如下面展示的结果，

- **rightOuterJoin**

  rightOuterJoin与leftOuterJoin基本一致，区别在于它的结果保留的是参数other这个RDD中所有的key。

- **fullOuterJoin**

  fullOuterJoin会保留两个RDD中所有的key，因此所有的值列都有可能出现缺失的情况，所有的值列都会转为Some对象。



[参考文章](<http://www.neilron.xyz/join-in-spark/>)

