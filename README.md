## SpApi - Pyhon библиотека для простого доступа к api серверов #СП

Это переделка библиотеки https://github.com/ronanru/spapi только для Python

### Установка
```
Создаёте в корне своего проекта папку modules в неё cкопируете папку spapi из этого репозитория
```


### Использование

```python
from modules import spapi

api = spapi.SpApi("spm") # вместо spm пишете нужный сервер если он есть во вкладке 'Поддерживаемые сервера' тут - https://github.com/ronanru/spapi

```


### Синтаксис и инструкции
```python
data = api.getLastChatMessages(5).messages 

# data - Это переменная, в неё мы записываем значение, которое вернул метод

# api - Обьект api который мы создали выше во вкладке "Использование"

# getLastChatMessages(5) - Метод обьекта api. Список методов будет ниже.
# Значение в скобках это аргумент этого метода, тут он означает лимит сообщений

# message - Это переменная обьекта getLastChatMessages(5)
# тоесть мы хотим от этого метода список сообщений.
# Без него это выглядело бы примерно вот так - <GetLastChatMessages messages='[]'>

```

### Приступим к коду
```python
from modules import spapi

api = spapi.SpApi("spm")


chat         = api.getLastChatMessages(4)
online       = api.getOnlinePlayers()
time         = api.getServerTime()
weather      = api.getServerWeather()

a = input("Введите что вы хотите получить -> ")
if a == "chat":
	print(chat)

elif a == "online":
	print(online)

elif a == "time":
	print(time)

elif a == "weather":
	print(weather)

else:
	print("Таких данных не обнаружено.")
```
