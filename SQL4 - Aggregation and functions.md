# SQL4 - Aggregation and functions
#sql

Group by: 
GROUP BY returns a single row for each unique combination of the GROUP BY fields.
通常group by 会和count, max, min, avg还有having联系在一起。返回的结果是一个row，所以不能有multiple value，不然就会随便取一个。

```sql
min, max, sum, avg, count
Group By columns
Having condition

// avg
select avg(GPA) 
from Student
where sID in (select sID from Apply where major = 'CS');

// count # of tuples
// 可以在count中加入要查询的distinct的变量以返回distinct值
select count(distinct sID)
from College
where enrollment > 15000;

// group: choose random value when there are multiple choices
select cName, count(*)
from Apply
group by cName;

//
select cName
from Apply
where (condition)
group by cName
having count(*) < 5;

//
sqrt()
power(base, exponenial)
round(number, 2)
```

















