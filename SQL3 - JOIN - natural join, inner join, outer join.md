# SQL3 - JOIN - natural join, inner join, outer join
#sql

## Natural Join
- - - -
A NATURAL JOIN is a JOIN operation that creates an implicit join clause for you based on the common columns in the two tables being joined. Common columns are columns that have the same name in both tables. 

If the SELECT statement in which the NATURAL JOIN operation appears has an asterisk (*) in the select list, the asterisk will be expanded to the following list of columns (in this order):

1.All the common columns
2.Every column in the first (left) table that is not a common column
3.Every column in the second (right) table that is not a common column
- - - -

## Inner Join
INNER JOIN: The INNER JOIN keyword selects all rows from both the tables as long as the condition satisfies. This keyword will create the result-set by combining all rows from both the tables where the condition satisfies i.e value of the common field will be same.

## Outer Join
Left outer join, right outer join, full outer join (left union right)

LEFT JOIN: This join returns all the rows of the table on the left side of the join and matching rows for the table on the right side of join. The rows for which there is no matching row on right side, the result-set will contain null.

RIGHT JOIN: RIGHT JOIN is similar to LEFT JOIN. This join returns all the rows of the table on the right side of the join and matching rows for the table on the left side of join. The rows for which there is no matching row on left side, the result-set will contain null. 

FULL JOIN: FULL JOIN creates the result-set by combining result of both LEFT JOIN and RIGHT JOIN. The result-set will contain all the rows from both the tables. The rows for which there is no matching, the result-set will contain NULL values.


```sql
// Inner Join on condition - theta-join

// Inner Join Using(attrs) 
// Left | Right | Full Outer Join


// inner join = 等价于使用逗号(,)
select distinct sName, major 
from Student (inner) join Apply
on Student.sID = Apply.sID

// natural join
select distinct sName, major
form Student natural join Apply
where sizeHS < 1000

// using join
select sName, GPA
from Student join Apply using(sID)
where sizeHS < 1000

select sName, GPA
from Student join Apply
on Student.sID = Apply.sID
and sizeHS < 1000 and major = 'CS'

// left outer join
// 如果右边的咩有匹配 留下空值
select sName
from Student natural left (outer) join Apply using(sID);

// if apply don't match any student, add null
select sName
from Student natural right outer join Apply;

// full outer join
select sName
from Student full outer join Apply using(sID);

// equals
select sName
from Student left outer join Apply using(sID)
union	
select sName
from Student right outer join Apply using(sID)


```

## Performance
A LEFT [OUTER] JOIN can be faster than an equivalent subquery because the server might be able to optimize it better—a fact that is not specific to MySQL Server alone.

















