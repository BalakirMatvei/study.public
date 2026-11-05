Служит гарантом закрытия файла
```python
with open(file_name, 'r', 'utf8') as file:
	for line in file:
		print(line, end='')
print(file.closed)#True
```
При выходе из блока кода отделенного отступами файл закрывается автоматически.