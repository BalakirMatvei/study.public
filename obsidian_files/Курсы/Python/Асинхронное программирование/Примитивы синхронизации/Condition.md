Condition объединяет `Lock` и очередь ожидания. Он нужен когда потоки должны ждать изменения общего состояния, а не просто изменения флага.
****
Ключевая операция `wait()` делает 3 вещи:
- Снимает `Lock`(что бы другие смогли изменить состояние объекта)
- засыпает до `notify()`
- после пробуждения снова ставит замок 
****
Методы:
```python
cond = threading.Condition(lock=None)#можно передать свой Lock/Rlock

with cond:#замок нужно держать для всех операций ниже
	cond.wait(timeout=None)
	cond.wait_for(predicate, timeout=None)
	cond.notify(n=1)#разбудить n ожидающий
	cond.notify_all()#разбудить всех
```
****
Условие можно проверять в цикле:
```python
def consumer(name): 
	for _ in range(5): 
		with cond: 
			while not buffer:
			cond.wait() 
			item = buffer.popleft() print(f" - {name} взял {item}") 
			cond.notify_all() # будим производителей 
		time.sleep(random.uniform(0, 0.5))
```
А можно с помощью `wait_for`:
```python
with cond:
	cond.wait_for(lambda: len(buffer) > 0)
	item = buffer.popleft()
```
`wait_for(predicate)` сам проверяет условие в цикле.
****
Почему условие проверяется с помощью `while`, а не в`if`:
Между моментом когда 1 поток разбудили, и моментом, когда он снова получил замок(`Lock`), другой поток может изменить состояние объекта.
****
Потерянный сигнал:
`notify()` будит только тех, кто уже ждет, если уведомление ушло до вызова `wait()`, то оно потеряется. Поэтому вот надежная схема:
Состояние хранится в переменной (buffer, флаг), а condition только будит.