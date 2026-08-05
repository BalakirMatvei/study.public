скалярные функции ***min, max, avg*** используются для нахождения минимального, максимального и среднего значений соответсвенно
```sql
select min(column_name)
from table_name

select max(column_name)
from table_name

select avg(column_name)
from table_name
```

для подсчета суммы всех значений в определенной колонке можно использовать скалярную функцию ***sum*** 
```sql
select sum(column_name)
from table_name
```
логично, что в функцию ***sum*** нужно передавать ту колонку, в которой содержатся числовые значения(***int, float***)