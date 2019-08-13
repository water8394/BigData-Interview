## hadoop1.x的缺点

1. JobTracker存在单点故障的隐患
2. 任务调度和资源管理全部是JobTracker来完成,单点负担过重
3. TaskTracker以Map/Reduce数量表示资源太过简单
4. TaskTracker 分Map Slot 和 Reduce Slot, 如果任务只需要map任务可能会造成资源浪费