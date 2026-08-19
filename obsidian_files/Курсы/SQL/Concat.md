Позволяет объеденить данные 2х столбцов в 1(например имя и фамилию пользователя)
```sql
select concat(column_name1, 'sep', column_name2)
from table_name
```
где ***sep*** - разделитель между данными(обычно используется пробел)

Так же ***concat*** можно заменить на:
```sql
select column_name1 || 'sep' || column_name2
from table_name
```
