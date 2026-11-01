Нужен для обращения к методам базового(родительского) класса из дочернего, чаще всего применяется с методом `__init__()` при его переопределении:
```python
class Robot:
	def __init__(self, model):
		self.model = model
		
	def operate():
		print('robot protects people')
		
class WarRobot(Robot):
	def __init__(self, model, gun):
		super().__init__(model=model)
		self.gun = gun
		
	def operate(self):
		super().operate()
		print(f'with a {gun}')
```
Сначала отрабатывает родительский метод, потом то, что дописано в дочернем.

Метод `super()` обращается вверх по классам по `__mro__`.
[[Множественное наследование#^8acb4a]] 
