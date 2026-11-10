`warning` - предупреждение, более мягкая версия ошибки, которая не останавливает выполнение программы.
****
Для их использования нужно импортировать их:
```python
import warnings
```
****
Что бы вызвать warning нужно использовать функцию `warn`:
```python
warnings.warn('some message')
```
![[Pasted image 20261109213957.png]]
****
Еще функция `warn()` принимает категорию предупреждения:
```python
warnings.warn('some message', category=category)
```
![[Pasted image 20261109214348.png]]
****
`Warnings`не получится ловить капсулой `try except` как исключения(ошибки)(просто ничего не произойдет)
****
Но можно фильтровать варнинги:
![[Pasted image 20261109215215.png]]
для этого используется функция `simplefilter(parametr)`
Например:
```python
simplefilter('ignore')
```

Но если передать 
```python
simplefilter('error')
```
То можно ловить их через капсулу `try except`
```python
warnings.warn('ne tyda', category=SyntaxWarning)

siplefilter('error')

try:
	print('hello world')
except SyntaxWarning:
	print('we catched warning')
```
