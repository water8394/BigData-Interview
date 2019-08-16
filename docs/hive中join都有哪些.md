## hive中join都有哪些

Hive中除了支持和传统数据库中一样的内关联（JOIN）、左关联（LEFT JOIN）、右关联（RIGHT JOIN）、全关联（FULL JOIN），还支持左半关联（LEFT SEMI JOIN）

- **内关联（JOIN）**

  只返回能关联上的结果。

- **左外关联（LEFT [OUTER] JOIN）**

  以LEFT [OUTER] JOIN关键字前面的表作为主表，和其他表进行关联，返回记录和主表的记录数一致，关联不上的字段置为NULL。

- **右外关联（RIGHT [OUTER] JOIN）**

  和左外关联相反，以RIGTH [OUTER] JOIN关键词后面的表作为主表，和前面的表做关联，返回记录数和主表一致，关联不上的字段为NULL。

- **全外关联（FULL [OUTER] JOIN）**

  以两个表的记录为基准，返回两个表的记录去重之和，关联不上的字段为NULL。

- **LEFT SEMI JOIN**

  以LEFT SEMI JOIN关键字前面的表为主表，返回主表的KEY也在副表中的记录

- **笛卡尔积关联（CROSS JOIN）**

  返回两个表的笛卡尔积结果，不需要指定关联键。



[参考文章](<http://lxw1234.com/archives/2015/06/315.htm>)