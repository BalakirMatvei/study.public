если в запросе, в котором используется много операторов or, слишком много условий, то можно упростить код с помощью оператора **in**:
```sql
select *
from table_name
where country = 'country1' or country = 'country2' or country = 'country3' or country = 'country4' or country = 'country5'
```
или 
```sql
select *
from table_name
where country in ('country1', 'country2', 'country3', 'country4', 'country5')
```

соответсвенно оператор **not in**  включает в финальную выборку все строки в которых не соблюдается ни одно равенство из списка
```sql
select *
from table_name
where country not in ('country1', 'country2', 'country3', 'country4', 'country5')
```