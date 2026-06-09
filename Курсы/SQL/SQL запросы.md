 ```sql
 create - создать что либо
 
 create table(a,b,c) - создать таблицу, a,b,c - столбцы
 
 insert into table_name(a,b,c)
 values(a_value, b_value, c_value); - вставить значения a_value, b_value,                                        c_value в колонки a,b,c таблицы                                            table_name
 
 
 update table_name set
 a_value = 'new a_value'
 where condition                 - обновить значение a_value в таблице                                        table_name в строке, где условие                                           condition выполняется
 
 
 delete from table_name
 where condition       - удалить строку таблицы table_name, где условие                             condition выполняется 
 
 
 select a, b, c from table_name
 where condition                    - вернуть строку, где условие                                                condition выполняется(вместо a, b, c                                       можно поставить * если нужны все                                           столбцы в выборке )
 
 create table table_name2(
	 a bigint not null,
	 b varchar not null,
	 fk bigint not null,
	 constraint fk_name foreign key (fk) references table_name1(id)
);

- создается таблица table_name2, в ней создается столбец, который будет внешним ключом(fk), столбец fk связывается со столбцом id в таблице table_name1.
  
  select table_name2.*, table_name1.* from table_name2
  join table_name1 on table_name1.id = table_name2.id
  - объединяет выборку из 2 и первой таблицы и связывает строки у которых одинкавый id
    
	    
  select * from left_table
  left/right outer join rigth_table on table_name1.id = table_name2.id
	 - в отличии от inner join(просто join) добавляет в выборку и те строки(из левой или правой таблицы), у которых нет совпадения по id
 
 full outer join - содержит и left и right outer join
 
bigint - целое число

varchar(64) - строка длинной до 64 символов

not null - поле не может быть пустым

primary key  - колонка уникальный идентификатор 

or и and - операторы для составления сложных условий
```