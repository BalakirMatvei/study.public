позволяют задать несколько условий при фильтрации через where
```sql
select *
from table_name
where condition1 and condition2

select *
from table_name
where condition1 or condition2

select *
from table_name
where condition1 and condition2 and condition3

select *
from table_name
where condition1 or condition2 or condition3
```

если стоит 3 уловия и между ними есть и оператор and, и оператор or, то для группировки условий сожно использовать круглые скобки:
```sql
select *
from table_name
where condition1 and (condition2 or condition3)
```

если надо сделать выборку всех значений, у которых какой лтбо параметр попадает в промежуток, то есть 2 варианта записи запроса:
```sql
select * 
from table_name
where quantity >= a and quantity <= b
```
или 
```sql
select * 
from table_name
where quantity between a and b
```

***between подразумевает диапазон с нестрогим неравсенством(>=/ <=, но не >/<) 

так же between применим к датам
