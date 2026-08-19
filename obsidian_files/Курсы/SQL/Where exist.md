Применяется в строке ***where*** и возвращает ***True*** если условию подзапроса удовлетворит хотя бы 1 звпись
```sql
select *
from table_name
where exists (select * from table_name2
			where condition)
```
Так же можно инвертировать с помощью оператора ***not***
```sql
select *
from table_name
where not exists (select * from table_name2
			where condition)
```