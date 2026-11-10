Можно прописать блок кода, который **будет выполнятся** в случае, **когда не будет ошибок**:
```python
try:
	f1()
except ZeroDivisionErorr:
	print('smth went wrong...')
else:
	print('all good!')
```

Можно прописать блок кода, который **будет выполнятся в любом случае**:
```python
try:
	f1()
except ZeroDivisionError:
	print('smth went wrong...')
else:
	print('all good!')
finally:
	print('done!')
```
