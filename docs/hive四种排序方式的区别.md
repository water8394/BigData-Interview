## hive四种排序方式的区别

- **order by** 
      order by 是要对输出的结果进行全局排序，这就意味着**只有一个reducer**才能实现（多个reducer无法保证全局有序）但是当数据量过大的时候，效率就很低。如果在严格模式下（hive.mapred.mode=strict）,则必须配合limit使用

- **sort by**
      sort by 不是全局排序，只是在进入到reducer之前完成排序，只保证了每个reducer中数据按照指定字段的有序性，是局部排序。配置mapred.reduce.tasks=[nums]可以对输出的数据执行归并排序。可以配合limit使用，提高性能

- **distribute by** 
      distribute by 指的是按照指定的字段划分到不同的输出reduce文件中，和sort by一起使用时需要注意，
  distribute by必须放在前面

- **cluster by**

  cluster by 可以看做是一个特殊的distribute by+sort by，它具备二者的功能，但是只能实现倒序排序的方式,不能指定排序规则为asc 或者desc



[参考文章](<https://blog.csdn.net/high2011/article/details/78012317>)

