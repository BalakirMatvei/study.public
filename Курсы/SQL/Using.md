***using*** значительно укорачивает запрос при работе с ***join*** 
Вместо 
```sql
select column_name1, column_name2, column_name3
from table_name1
join table_name2 on table_name1.fk_column = table_name2.fk_column
```
можно написать
```sql
select column_name1, column_name2, column_name3
from table_name1
join table_name2 using(fk_column)
```
Но для использования ***using***, колонки, по которым происходит соединение, должны одинаково называться в обеих таблицах