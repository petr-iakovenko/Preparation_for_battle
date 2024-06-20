# Сборка общих вопросов junior_python_developer

## Общая теория

### Когда вы отправляете запрос с браузера, происходит следующее:
- ##### Формирование HTTP-запроса:
Вы вводите URL в адресной строке браузера или выполняете другое действие (например,  клик по ссылке или отправка формы). Браузер формирует HTTP-запрос на основе этого действия. 
- ##### Разрешение DNS:
Если введённый URL не был кэширован в браузере, происходит DNS-разрешение. Браузер определяет IP-адрес сервера, на который нужно отправить запрос, используя DNS-сервер. 
- ##### Установление соединения:
Браузер устанавливает TCP-соединение с сервером, на который отправляется запрос. Это соединение устанавливается через порт 80 (для HTTP) или 443 (для HTTPS). 
- ##### Отправка запроса:
Браузер отправляет HTTP-запрос на сервер. Запрос включает метод (GET, POST и т.д.),  URL, заголовки (например, User-Agent, Accept-Language) и, возможно, тело запроса (например, данные формы).  
- ##### Обработка запроса сервером:
Сервер получает запрос, обрабатывает его и генерирует HTTP-ответ. 
- ##### Получение ответа:
Браузер ожидает ответ от сервера. Ответ включает статус-код (например, 200 OK, 404 Not Found), заголовки (например, Content-Type, Content-Length) и, возможно, тело ответа (например, HTML-код веб-страницы или данные в формате JSON).
- ##### Отображение содержимого:
Браузер получает содержимое ответа и отображает его пользователю. Если это HTML-страница, браузер рендерит её и показывает на экране. Если это файл или другие данные, браузер может предложить их для скачивания или обработать соответствующим образом. 
- ##### Закрытие соединения:
После завершения передачи данных браузер закрывает TCP-соединение с сервером.
***
### Типы данных в Python (mutable / immutable)
- ##### Изменяемые типы данных (mutable)
Их можно изменять после их создания (изменять их содержимое, добавлять или удалять элементы).

Списки (lists):
```python 
my_list = [1, 2, 3]
my_list.append(4)  # теперь [1, 2, 3, 4]
```
Словари (dictionaries):
```python
my_dict = {'a': 1, 'b': 2}
my_dict['c'] = 3  # теперь {'a': 1, 'b': 2, 'c': 3}
```
Множества (sets):
```python
my_set = {1, 2, 3}
my_set.add(4)  #  теперь {1, 2, 3, 4}
```
- ##### Неизменяемые типы данных (immutable)
Неизменяемые типы данных нельзя изменять после их создания. Любое изменение приводит к созданию нового объекта.

Числа (integers, floats, complex):
```python
x = 5 
```
Строки (strings):
```python
my_string = "hello" 
```
Кортежи (tuples):
```python
my_tuple = (1, 2, 3) 
```
Булевы значения (booleans):
```python
is_true = True 
is_false = False
```
None:
```python
x = None
```
***
### Что быстрее? list tuple set dict
Самый быстрый доступ по индексу: `list` и `tuple` (O(1)).  
Самая быстрая проверка на наличие элемента: `set` и `dict` (O(1)).  
Самое быстрое добавление элемента: `list` (в конец), `set` и `dict` (O(1)).  
Самое быстрое удаление элемента: `set` и `dict` (O(1)).  

То есть `dict` и `set(множество)` часто быстрее, когда нужно проверять 
наличие элемента, добавлять или удалять элементы.  
А `list(список)` и `tuple(кортеж)` быстрее при доступе по индексу.
***
### Что такое исключения?
Исключения — это ошибки, которые возникают во время выполнения программы.  
Когда программа сталкивается с ошибкой, она "выбрасывает" исключение, 
которое может остановить её выполнение.  
#### Обработка исключений  
Чтобы программа не завершалась при возникновении ошибки, мы можем "ловить" исключения и обрабатывать их с помощью конструкции `try-except`.  

Блоки `else` и `finally`:  
`else`: Выполняется, если ошибок не было.
`finally`: Выполняется всегда, независимо от того, была ошибка или нет.  
Полезно для завершения работы, например, закрытия файла.
```python
try:
    value = int(input("Введите число: "))
    result = 10 / value
except ZeroDivisionError:
    print("Ошибка: Деление на ноль!")
except ValueError:
    print("Ошибка: Некорректное значение!")
else:
    print(f"Результат: {result}")
finally:
    print("Блок finally всегда выполняется")
```

***
### Какие условные операторы существуют?
`if-elif-else`
Циклы (loops):
`for` - проходится по каждому элементу до последнего вкл.
`while` - бесконечен пока не объявится значение `false`.

### pass, break и continue 
`pass`, `break` и `continue` — это ключевые слова в Python, которые используются 
для управления выполнением кода в циклах и условиях.

`pass` - используется для заполнения места, где код требуется синтаксически, 
но ничего делать не нужно.  
`break` - Позволяет выйти из цикла, когда достигнуто определенное условие.  
`continue` - Помогает пропустить текущую итерацию цикла и перейти к 
следующей.
***

### Объектно-ориентированное программирование (ООП)
Классы — это шаблон или чертеж для создания объектов по каким-то данным (поля) и действия (методы), созданных на основе класса.

#### Инкапсуляция:
это принцип, при котором данные объекта и методы, которые с ними работают, 
объединяются в единую сущность (класс). Это скрывает внутренние детали реализации объекта и предоставляет только необходимые интерфейсы для взаимодействия с ним.  

_Пример: класс `Car` может иметь закрытые поля (например, `engine` и `fuelLevel`) и публичные методы (например, `startEngine()` и `drive()`)._
#### Наследование:
позволяет создавать новый класс на основе существующего класса. Новый класс (подкласс) наследует свойства и методы базового класса (суперкласса), что позволяет повторно использовать код и улучшает его структуру.  

_Пример: класс `ElectricCar` может наследовать от класса `Car` и добавлять специфические для электромобиля свойства и методы (например, `batteryLevel` и `charge()`)._
#### Полиморфизм:
позволяет объектам разных классов обрабатывать одинаковые сообщения по-разному.
Это достигается через переопределение методов в подклассах. Полиморфизм позволяет использовать объекты с общим интерфейсом, не зная их конкретный тип.  

_Пример: метод `drive()` может быть реализован по-разному в классах `Car` и `ElectricCar`, но вызывать его можно одинаково._
#### Абстракция:
это принцип, при котором скрываются сложные детали реализации и предоставляются только основные характеристики и функциональность объекта. 
Это позволяет сосредоточиться на важных аспектах объекта, не вдаваясь в детали его реализации.  

_Пример: класс `Vehicle` может быть абстрактным и определять общие свойства и методы для всех транспортных средств, такие как `move()` и `stop()`, но не реализовывать их._
```python
# Абстракция
class Животное:
    def издатьЗвук(self):
        raise NotImplementedError("Подкласс должен реализовать этот метод")

# Наследование и Полиморфизм
class Собака(Животное):
    def издатьЗвук(self):
        return "Гав!"

class Кошка(Животное):
    def издатьЗвук(self):
        return "Мяу!"

# Инкапсуляция
class Человек:
    def __init__(self, имя):
        self.__имя = имя  # Приватное поле

    def поприветствовать(self):
        return f"Привет, меня зовут {self.__имя}"

# Пример использования
собака = Собака()
кошка = Кошка()
print(собака.издатьЗвук())  # Выведет "Гав!"
print(кошка.издатьЗвук())  # Выведет "Мяу!"

человек = Человек("Алиса")
print(человек.поприветствовать())  # Выведет "Привет, меня зовут Алиса"
```
```python
class Машина:
    def __init__(self, цвет, модель, год_выпуска):
        self.цвет = цвет
        self.модель = модель
        self.год_выпуска = год_выпуска

    def завести(self):
        print(f"{self.модель} завелась!")

    def ехать(self):
        print(f"{self.модель} едет!")

    def остановиться(self):
        print(f"{self.модель} остановилась!")

# Создание объектов (экземпляров класса)
машина1 = Машина("красный", "Тесла", 2022)
машина2 = Машина("синий", "БМВ", 2021)

# Вызов методов объекта
машина1.завести()        # Выведет "Тесла завелась!"
машина1.ехать()          # Выведет "Тесла едет!"
машина1.остановиться()   # Выведет "Тесла остановилась!"

машина2.завести()        # Выведет "БМВ завелась!"
машина2.ехать()          # Выведет "БМВ едет!"
машина2.остановиться()   # Выведет "БМВ остановилась!"
```

### Что такое методы классов?
Методы классов — это функции, которые находятся внутри класса и описывают, что объекты этого класса могут делать.  

В Python есть три вида методов классов:  
 
#### Обычные методы (`instance methods`):  
- Работают с объектами класса.  
- Первый параметр — `self`, который ссылается на текущий объект.
```python
class MyClass:
    def __init__(self, value):
        self.value = value
    
    def display(self):
        print(f"Значение: {self.value}")

# Создание объекта
obj = MyClass(10)
obj.display()  # Выведет "Значение: 10"
```
#### Классовые методы (`class methods`):
- Работают с самим классом, а не с объектами.
- Первый параметр — `cls`, который ссылается на класс.
- Объявляются с помощью декоратора `@classmethod`.
```python
class MyClass:
    count = 0
    
    def __init__(self, value):
        self.value = value
        MyClass.count += 1
    
    @classmethod
    def get_count(cls):
        return cls.count

# Создание объектов
obj1 = MyClass(10)
obj2 = MyClass(20)

print(MyClass.get_count())  # Выведет 2
```

#### Статические методы (`static methods`):
- Не имеют доступа ни к объектам, ни к классу.
- Это просто функции, которые находятся внутри класса для удобства.
- Объявляются с помощью декоратора `@staticmethod`.
```python
class MyClass:
    @staticmethod
    def greet(name):
        print(f"Привет, {name}!")

# Вызов статического метода
MyClass.greet("Мир")  # Выведет "Привет, Мир!"
```

### Что такое дандер методы классов?
Дандер методы (`double underscore methods`)  — это специальные методы с особыми именами, которые начинаются и заканчиваются двойным подчеркиванием (`__`). Они позволяют определять специфическое поведение объектов в Python и используются для различных задач, таких как инициализация объектов, перегрузка операторов и т.д.

Дандер методы помогают классам в Python взаимодействовать с языковыми конструкциями и стандартными операторами. Они позволяют контролировать, как объекты создаются, инициализируются и как они ведут себя при использовании операций, таких как сложение, вычитание и сравнение.

`__init__` - вызывается при создании нового экземпляра класса и используется для инициализации его состояния.
```python
class MyClass:
    def __init__(self, value):
        self.value = value

obj = MyClass(10)  # Вызовет __init__, инициализируя объект obj
```
`__str__ и __repr__`: `__str__` - возвращает строковое представление объекта для пользовательского вывода, а `__repr__` — для внутреннего представления.
```python
class MyClass:
    def __init__(self, value):
        self.value = value
    
    def __str__(self):
        return f"MyClass instance with value {self.value}"
    
    def __repr__(self):
        return f"MyClass({self.value})"

obj = MyClass(10)
print(str(obj))   # Выведет: MyClass instance with value 10
print(repr(obj))  # Выведет: MyClass(10)
```
`__add__` - позволяет определить поведение объекта при использовании оператора +.
```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __add__(self, other):
        return Point(self.x + other.x, self.y + other.y)

p1 = Point(1, 2)
p2 = Point(3, 4)
p3 = p1 + p2
print(p3.x, p3.y)  # Выведет: 4 6
```
***

### Что такое рекурсия?
Рекурсия — это когда функция вызывает саму себя. Это полезно для решения задач, которые можно разбить на более мелкие 
задачи того же типа.

Пример:  
Числа Фибоначчи — это последовательность, где каждое число — это сумма двух предыдущих. Начинается с 0 и 1.  
F(0)=0  
F(1)=1  
F(2)=F(1)+F(0)=1  
F(3)=F(2)+F(1)=2  
F(4)=F(3)+F(2)=3  
и так далее.
    
Рекурсивная функция для чисел Фибоначчи: 
```python
def fibonacci(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n-1) + fibonacci(n-2)

print(fibonacci(5))  # Выведет 5
```

#### Когда использовать рекурсию?
Рекурсия полезна, когда:  
- Задача может быть разделена на меньшие подзадачи того же типа.
- Работаешь с деревьями и графами.
- Нужен простой и интуитивно понятный код.  
 
Важные моменты  
- Базовый случай: Условие, при котором функция перестаёт вызывать саму себя.
- Рекурсивный случай: Когда функция вызывает саму себя с новыми параметрами.

Недостатки:
- Может вызвать переполнение стека, если нет базового случая.
- Может быть менее эффективной по памяти и времени по сравнению с обычными циклами.

Рекурсия — это просто способ заставить функцию решать большие задачи, разбивая их на маленькие части.
***
### Что такое `list comprehension`?
`List comprehension` — это короткий и удобный способ создавать списки в Python.

Основной синтаксис: `[выражение for элемент in коллекция if условие]`

Пример:  
Необходимо создать список квадратов чисел от 0 до 9.  
Обычный способ:
```python
squares = []
for x in range(10):
    squares.append(x**2)
print(squares)  # Выведет [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
С использованием list comprehension:
```python
squares = [x**2 for x in range(10)]
print(squares)  # Выведет [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
Пример с фильтрацией:  
Необходимо создать список четных чисел от 0 до 9  
Обычный способ:
```python
even_numbers = []
for x in range(10):
    if x % 2 == 0:
        even_numbers.append(x)
print(even_numbers)  # Выведет [0, 2, 4, 6, 8]

```
С использованием `list comprehension`:
```python
even_numbers = [x for x in range(10) if x % 2 == 0]
print(even_numbers)  # Выведет [0, 2, 4, 6, 8]

```
***
### Функция enumirate():
Используется для перебора элементов последовательности (например, списка или кортежа) одновременно с отслеживанием их индексов.
```python
my_list = ['apple', 'banana', 'cherry']

for index, value in enumerate(my_list):
    print(index, value)
    
# Вывод
# 0 apple
# 1 banana
# 2 cherry
```