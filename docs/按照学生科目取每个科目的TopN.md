## Hive SQL : 按照学生科目取每个科目的TopN

```SQL
id,name,subject,score
1,小明,语文,87
2,张三,语文,27
3,王五,语文,69
4,李四,语文,99
5,小明,数学,86
6,马六,数学,33
7,李四,数学,44
8,小红,数学,50
```

**按照各个科目的成绩排名 取 Top3**

```
select a.* from
(select id,name,subject,score,row_number() over(partition by subject order by score desc) rank from student) a
where a.rank <= 3
```



[参考文章](<https://blog.csdn.net/WYpersist/article/details/80318305>)