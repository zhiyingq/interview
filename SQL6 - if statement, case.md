# SQL6 - if statement, case 
#sql

```sql
select x, y, z, if (x + y > z and x + z > y and z + y > x, "Yes", "No") as triangle
from triangle

ifnull(statement, null)
limit 1 // has only one result
offset 1 // has offset 1, start from 2
```

```sql
IF(condition, value_if_true, value_if_false)
SELECT IF(STRCMP("hello","bye") = 0, "YES", "NO");

```

```sql
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;

update salary
set sex = case sex
            when 'm' then 'f'
            when 'f' then 'm'
          end
;

SELECT CASE 
            WHEN Obsolete = 'N' or InStock = 'Y' 
               THEN 1 
               ELSE 0 
       END as Saleable, * 
FROM Product
```








