Позволяет применить какую либо агрегатную функцию и группировать по какому либо параметру
```sql
select column_name, count(*)
from orders
where condition
group by column_name
order by count(*) 
limit A
```
Этот запрос позволяет посчитать количество чего либо удовлетворяющего ***condition*** и вывести эти данные по ***column_name*** 