## Hive Sql 是怎样解析成MR job的?

**主要分为6个阶段:**

1. **Hive使用Antlr实现语法解析**.根据Antlr制定的SQL语法解析规则,完成SQL语句的词法/语法解析,将SQL转为抽象语法树AST.

2. **遍历AST,生成基本查询单元QueryBlock**.QueryBlock是一条SQL最基本的组成单元，包括三个部分：输入源，计算过程，输出.
3. **遍历QueryBlock,生成OperatorTree**.Hive最终生成的MapReduce任务，Map阶段和Reduce阶段均由OperatorTree组成。Operator就是在Map阶段或者Reduce阶段完成单一特定的操作。QueryBlock生成Operator Tree就是遍历上一个过程中生成的QB和QBParseInfo对象的保存语法的属性.
4. **优化OperatorTree.**大部分逻辑层优化器通过变换OperatorTree，合并操作符，达到减少MapReduce Job，减少shuffle数据量的目的
5. **OperatorTree生成MapReduce Job**.遍历OperatorTree,翻译成MR任务.
   - 对输出表生成MoveTask
   - 从OperatorTree的其中一个根节点向下深度优先遍历
   - ReduceSinkOperator标示Map/Reduce的界限，多个Job间的界限
   - 遍历其他根节点，遇过碰到JoinOperator合并MapReduceTask
   - 生成StatTask更新元数据
   - 剪断Map与Reduce间的Operator的关系

6. **优化任务.** 使用物理优化器对MR任务进行优化,生成最终执行任务





[参考文章](<https://www.cnblogs.com/Dhouse/p/7132476.html>)