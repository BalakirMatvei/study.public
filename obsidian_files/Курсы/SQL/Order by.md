для сортировки данных по убыванию или возрастанию можно использовать ключевое слово ***order by*** 
```sql
select column_name
from table_name
where condition
order by column_name asc - в порядке возрастания

select column_name
from table_name
where condition
order by column_name desc - в порядке убывания
```

если не передавать параметр ***asc*** или ***desc***, то по умолчанию сортировка будет происходить в порядке возрастания

так же можно сортировать более чем по 1 колонке
тогда при сортировке второй колонки не будет нарушаться сортировка первой колонки
```sql
select distinct column_name1, column_name2
from table_name
where condition
order by column_name1 asc/desc, column_name2 asc/desc
```