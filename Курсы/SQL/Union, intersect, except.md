***UNION*** 
***Union*** позволяет объединять результаты 2х ***select*** в 1 столбец
при этом удаляя дубликаты, если надо оставить дубликаты, то можно использовать ***union all*** 
```sql
select column_name1
from table_name1
union
select column_name2
from table_name2

select column_name1
from table_name1
union all
select column_name2
from table_name2
```

***INTERSECT*** 
***intersect*** является пересечением данных из таблиц, т.е. значение должно быть в обеих таблицах для того что бы оно попало в финальную выборку
```sql
select column_name1
from table_name1
intersect
select column_name2
from table_name2
```
так же как и ***union***, ***intersect*** не показывает дубликаты. => для их показа можно применить ***intersect all*** 
```sql
select column_name1
from table_name1
intersect all
select column_name2
from table_name2
```

***EXCEPT***
***except*** передает значение в финальную выборку только если оно есть в 1ой таблице и отсутствует во 2ой
```sql
select column_name1
from table_name1
except
select column_name2
from table_name2
```
так же как и ***union***, ***except*** не показывает дубликаты. => для их показа можно применить ***except all***
```sql
select column_name1
from table_name1
except all
select column_name2
from table_name2
```
