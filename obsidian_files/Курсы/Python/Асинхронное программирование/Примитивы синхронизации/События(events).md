Устроен как булев флаг(начальное значение False) и очередь ожидающих
```python 
start = threading.Events()

start.wait()#Останавливает всех в этом месте
#может принимать timeout, тогда флаг сменится на True по истечении этого времени

start.set()#меняет флаг на True, "размораживает" всех ожидающих

start.clear()#меняет флаг на False

start.is_set()#проверяет значение флага
```
Лучше использовать start.wait(1) чем time.sleep(1).
При time.sleep() поток нельзя разбудить раньше и остановка занимает больше времени.
****
Пример(забег):
```python
import time  
import threading  
  
class Runner(threading.Thread):  
     def __init__(self, name):  
         threading.Thread.__init__(self)  
         self.name = name  
         self.position = 0  
  
  
     def run(self):  
         start.wait()  
         for i in range(1, 11):  
             time.sleep(0.5)  
             if not dist[i - 1]:  
                 dist[i - 1] = self.name  
                 self.position = 1  
                 print(f'{dist[i - 1]} - {i*100}m')  
             else:  
                 self.position = 0  
  
  
dist = [None for _ in range(10)]  
start = threading.Event()  
names = ["Petya", "Vasya", "Ivan", "Sasha", "Gleb"]  
  
runners = [Runner(name) for name in names]  
  
print('.' * 20, "START", "." * 20)  
  
for runner in runners:  
    runner.start()  
  
start.set()  
  
for runner in runners:  
    runner.join()  
  
print('.' * 20, "FINISH", "." * 20)  
  
for runner in runners:  
    if runner.position == 1:  
        print(f'{runner.name} is winner!!!')
```
****
Что Event не может:
- Передавать данные(это только да/нет, для данных лучше использовать другие структуры(например `queue.Queue`))
- Будить 1 поток, `.set()` будит сразу всех(если нужно одного, то лучше использовать `Condition` с `notify()` или семафор)
- Работать как импульс(Между, написанными подряд, `.set()` и `.clear()` поток может не успеть проснуться).