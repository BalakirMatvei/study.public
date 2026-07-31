```sql
select count(*)      - выведет колво строк
from table_name
```

можно ниже добавить условие, например:
```sql
select count(*)
from table_name
where city = 'Grodno'
```

если нужно только колво уникальных значений из столбца, то можно добавить distinct:
```sql
select count(distinct column_name)      
from table_name
```