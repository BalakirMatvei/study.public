***having*** - это пост фильтр, который по принципу работы аналогичен фильтру ***where***, но применяется он после группировки ***group by***(но до сортировки ***order by***) 
```sql
select column_name1, sum(column_name2 * column_name3)
from table_name
where column_name4 <> 1
group by column_name1
having condition
order by column_name1 desc
```
