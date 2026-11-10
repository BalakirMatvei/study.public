Можно самому вызвать ошибку
```python
def greeting(name):
	if name == 'Nikita':
		raise BaseException(f'we dont like you, {name}')
	else:
		print(f'Hello, {name}')
```
****
Проброс исключений:
```python
try:
	raise NameError('Hello')
except NameError as exc:
	print(f'Исключение {type(exc)}, параметры - {exc.args}')
	raise
```
сообщение будет выведено на консоль, но ошибка будет вызвана все равно(в блоке `exception` `raise` вызывается без параметров если нужно вызвать ту же ошибку, которую перехватывали)
**Используется для зачистки возможно упущенных данных и/или логирования ошибок**

Можно вызывать другую ошибку:
```python
try:
	raise NameError('Hello')
except NameError as exc:
	print(f'Исключение {type(exc)}, параметры - {exc.args}')
	raise TypeError from exc
```
****
Можно вызывать кастомные ошибки:
```python
class CustomError(Exception):
	pass
	
def my_func(a, b):
	if a < b:
		raise CustomError('Нельзя делить иеньшее на большее')
	else:
		print(a/b)
	
try:
	my_func()
except CustomError as exc:
	print(f'Поймано исключение {exc}')
```
****
Наиболее частые случаи выброса ошибок:
- проверка типов параметров методов/функций
- проверка совместимости параметров методов/функций
- нарушение работы возможности работы кода(неправильные данные)
