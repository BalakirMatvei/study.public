Используется для работы с файлами на уровне ОС.

Полезные методы:
```python
import os

os.walk(path)#пройтись по всем вайлам в директории, path - путь к директории. Возвращает кортеж для каждого файла вида (dirpath, dirnames, filenames)

os.path.normpath(path)#привести путь к нужному виду для данной ОС

os.path.getsize(path)#получить размер файла

os.path.getctime(path)#возвращает время создания файла в видел "кол-во секунд с начала эпохи(01.01.1970) до создания файла"
#для перевода в привычную дату можно импользовать модуль time
os.path.getmtime(path)#возвращает время последнего изменения
os.path.getatime(path)#возвращает время последнего доступа
import time
seconds = os.path.getctime(path)
time.gmtime(seconds)#возвращает кортеж с годом, месяцум, днем, часом и тд создания файла

os.path.join(dir_path, file_name)#возвращает составленный путь к файлу с учетом ОС

os.path.dirname(path)#для директории возвращает родительскую директорию, а для файла директорию, в которой он лежит

os.path.basename(path)#возвращает имя файла

os.path.split(path)#отделяет только последний файл(директорию, если на нее заканчивается путь) из пути

os.path.splitext(path#отделяет расширение последнего файла)(если путь заканчивается на директорию, то отделит пустую строку)

#обе последние команды(split и splitext) возвращают tuple

os.path.abspath('file_name')#возвращает абсолютный(от корня) относительно текущей директории

os.path.isabs(path)#возвращает True или False, проверяет абсолютный ли путь указан

os.path.exist('file.txt')#проверяет существование пути(к файлу или папке)(возвращает bool)

os.path.isfile("file.txt") # True, если это обычный файл
os.path.isdir("my_dir") # True, если это папка

os.path.expandvars('$HOME/projects')#заменяет в строке пути подстроки вида `$name` или `${name}` на значения соответствующих переменных из окружения операционной системы

paths = ["/usr/lib/python3", "/usr/lib/perl", "/usr/local"]
os.path.commonpath(paths)# возвращает общую часть путей
```
Константы:
```python
os.path.sep# разделитель каталогов "/" или "\\" в зависимости от ОС
os.path.pathsep#разделитель в переменной path ":" или ";"
os.path.curdir# '.'
os.path.pardir# '..'
```

`pathlib`:
```python
from pathlib import Path

P = Path('home') / 'user' / 'example.txt'
#оператор деления прописан в pathlib и добавляет строку в путь с нужным разделителем

p.name #example.txt, возвращает имя файла
p.suffix #txt, расширение файла
p.parent#Path('home/user')
p.exists()#проверяет существование
```

Вместо пути к файлу или его имени можно указать `__file__`, это означает текущий файл