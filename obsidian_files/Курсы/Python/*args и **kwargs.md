Что бы передать в функцию произвольное количество позиционных параметров можно использовать `args`
```python
def print_them_all(*args):
	for ind, el in enumerate(args):
		print('positional argumet', ind, ': ', el)
		
print_them_all(2, 3, 'hello')
#positional argumet 0: 2
#positional argumet 1: 3
#positional argumet 2: 'hello'
```
`*args`  собирает ВСЕ переданные в функцию позиционные параметры в кортеж, т.е. если внутри функции написать `print(type(args))`, то оно выдаст `<class 'tuple'>`

Если мы хотим передать в функцию заранее созданный список, то его нужно указывать с распаковкой:
```python
my_list = [1, 2, 3]

print_them_all(*my_list)
#positional argumet 0: 1
#positional argumet 1: 2
#positional argumet 2: 3
```
Все работает
Но если указать список без распаковки
```python
my_list = [1, 2, 3]

print_them_all(my_list)
```
то в args создастся кортеж, состоящий из одного элемента(нашего списка)
```python
print_them_all(my_list)
#positional argumet 0: [1, 2, 3]
```
Что бы передать в функцию произвольное количество именованных параметров можно использовать `**kwargs`
```python
def print_them_all(**kwargs):
	for key, value in kwargs.items():
		print('keyword argumet:', key, '=', value)
		
print_them_all(num1=2, num2=3, message='hello')
#keyword argumet: num1 = 2
#keyword argumet: num2 = 3
#keyword argumet: message = 'hello'
```
`**kwargs`  собирает ВСЕ переданные в функцию именованные параметры в словарь, т.е. если внутри функции написать `print(type(kwargs))`, то оно выдаст `<class 'dict'>`

Если мы хотим передать в функцию заранее созданный словарь, то его нужно указывать с распаковкой:
```python
my_dict = {num1 : 2, num2 : 3, message : 'hello'}

print_them_all(**my_dict)
#keyword argumet 0: 2
#keyword argumet 1: 3
#keyword argumet 2: 'hello'
```

Если функция принимает только позиционные параметры(задана с args), то при вызове нельзя в нее передавать именованные параметры. И наоборот

Если мы хотим, что бы функция могла принимать произвольное количество как позиционных, так и именованных параметров, то нужно при ее описании задать и args, и kwargs
```python
def print_them_all(*args, **kwargs):  
    for arg in args:  
        print(arg)  
    for kwarg, value in kwargs.items():  
        print(value)
```
Но все равно при вызове нужно указывать сначала позиционные, а потом именованные аргументы. Иначе интерпритатор выдаст ошибку.

Распаковка работает все так же:
```python
def print_them_all(*args, **kwargs):  
    for arg in args:  
        print(arg)  
    for kwarg, value in kwargs.items():  
        print(value)
        
my_list = [1, 2, 3]
my_dict = {num1 : 2, num2 : 3, message : 'hello'}

print_threm_all(*my_list, **my_dict)
```
Но чаще всего функцию задают так, что бы она принимала параметр, был параметр по умолчанию, собирала все позиционные и именованные параметры.
```python
def print_them_all(a, b=5, *args, **kwargs)
```

