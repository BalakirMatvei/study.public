ключевое слово ***limit*** пишется в самом конце запроса и ограничевает количество записей в итоговой выборке:
```sql
select *
from table_name
where condition
order by column_name
limit A                    - где A это количество записей
```