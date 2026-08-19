позволяет объеденить данные из нескольких таблиц(если они связаны с помощью foreign key)
```sql
select column_name1, column_name2, column_name3
from table_name1
join table_name2 on table_name1.fk_column = table_name2.fk_column
```
записи ***join*** и ***inner join*** - равнозначны

С помощью ***join*** можно объединять данные из более чем двух таблиц
```sql
select column_name1, column_name2, column_name3, column_name4, column_name5, column_name6
from table_name1
join table_name2 on table_name1.fk_column1 = table_name2.fk_column1
join table_name3 on table_name2.fk_column2 = table_name3.fk_column2
```
