## flink中的session Window怎样使用

会话窗口主要是将某段时间内活跃度较高的数据聚合成一个窗口进行计算,窗口的触发条件是 Session Gap, 是指在规定的时间内如果没有数据活跃接入,则认为窗口结束,然后触发窗口结果

Session Windows窗口类型比较适合非连续性数据处理或周期性产生数据的场景,根据用户在线上某段时间内的活跃度对用户行为进行数据统计

```
val sessionWindowStream = inputStream
.keyBy(_.id)
//使用EventTimeSessionWindow 定义 Event Time 滚动窗口
.window(EventTimeSessionWindow.withGap(Time.milliseconds(10)))
.process(......)
```

Session Window 本质上没有固定的起止时间点,因此底层计算逻辑和Tumbling窗口及Sliding 窗口有一定的区别,

Session Window 为每个进入的数据都创建了一个窗口,最后再将距离窗口Session Gap 最近的窗口进行合并,然后计算窗口结果