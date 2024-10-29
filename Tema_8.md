# Тема 8. Введение в ООП
Отчет по Теме #8 выполнил(а):
- Ганиева Анастасия Ильсуровна
- ПИЭ-22-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1

Создайте класс “Car” с атрибутами производитель и модель. Создайте объект этого класса. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями.

```python
# определяем класс Car
class Car:
    # инициализируем новый объект Car с маркой и моделью
    def __init__(self, make, model):
        # устанавливаем атрибут make для текущего объекта
        self.make = make
        # устанавливаем атрибут model для текущего объекта
        self.model = model

# создаем экземпляр класса Car с маркой "Toyota" и моделью "Corolla"
my_car = Car("Toyota", "Corolla")

```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_8/images8/1.png)

## Выводы

1. Определение класса: определяем новый класс Car.
2. Конструктор `__init__:` конструктор принимает два параметра: `make` и `model`.
3. Создание объекта my_car:
   - Экземпляр my_car создается с использованием класса Car.
   - При создании объекта передаются параметры `"Toyota"` и `"Corolla"`, что означает, что атрибут make будет равен "Toyota", model  "Corolla".

## Лабораторная работа №2

Дополните код из первого задания, добавив в него атрибуты и методы класса, заставьте машину “поехать”. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
# определяем класс Car
class Car:
    # инициализируем новый объект Car с маркой и моделью
    def __init__(self, make, model):  # исправлено на __init__ для корректного функционирования
        # устанавливаем атрибут make для текущего объекта
        self.make = make
        # устанавливаем атрибут model для текущего объекта
        self.model = model

    # метод для симуляции вождения автомобиля
    def drive(self):
        # выводим сообщение о том, что автомобиль движется
        print(f"Driving the {self.make} {self.model}")
# создаем экземпляр класса Car с маркой "Toyota" и моделью "Corolla"
my_car = Car("Toyota", "Corolla")  # создаем объект my_car, передавая параметры
# вызываем метод drive для объекта my_car
my_car.drive()
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_8/images8/2.png)

## Выводы

1. Определение класса Car: представляет собой шаблон для создания объектов с определенными характеристиками, такими как марка и модель.
2. Конструктор `__init__` инициализирует новые объекты класса. Он принимает два параметра (`make` и `model`) и присваивает их атрибутам объекта с помощью `self`.
3. Метод `drive` выводит текстовое сообщение, информирующее, что автомобиль движется, используя атрибуты `make` и `model`. 
4. Создается экземпляр класса `Car` с маркой `"Toyota"` и моделью `"Corolla"`. Это означает, что в памяти создается объект `my_car`, который имеет доступ к всем методам и атрибутам, определенным в классе.
5. Вызов метода drive:  вызывается метод `drive` для объекта `my_car`. Это приводит к выводу сообщения на экран: `"Driving the Toyota Corolla"`.


## Лабораторная работа №3

Создайте новый класс “ElectricCar” с методом “charge” и атрибутом емкость батареи. Реализуйте его наследование от класса, созданного в первом задании. Заставьте машину поехать, а потом заряжаться. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
# определяем класс Car
class Car:
    # инициализируем новый объект Car с маркой и моделью
    def __init__(self, make, model):
        # устанавливаем атрибут make для текущего объекта
        self.make = make
        # устанавливаем атрибут model для текущего объекта
        self.model = model
    # метод для симуляции вождения автомобиля
    def drive(self):
        # выводим сообщение о том, что автомобиль движется
        print(f"Driving the {self.make} {self.model}")
# определяем класс ElectricCar, наследующий от Car
class ElectricCar(Car):
    # инициализируем новый объект ElectricCar с маркой, моделью и емкостью батареи
    def __init__(self, make, model, battery_capacity):
        # вызываем конструктор родительского класса для инициализации атрибутов make и model
        super().__init__(make, model)
        # устанавливаем емкость батареи для текущего объекта
        self.battery_capacity = battery_capacity
    # метод для зарядки электромобиля
    def charge(self):
        # выводим сообщение о зарядке
        print(f"Charging the {self.make} {self.model} with {self.battery_capacity} kWh")
# создаем экземпляр класса Car с маркой и моделью
my_car = Car("Toyota", "Corolla")
my_car.drive()  # вызываем метод drive для Toyota Corolla
# создаем экземпляр класса ElectricCar с маркой, моделью и емкостью
my_electric_car = ElectricCar("Tesla", "Model S", 75)
# вызываем метод drive для объекта my_electric_car
my_electric_car.drive()  
# вызываем метод charge для объекта my_electric_car
my_electric_car.charge()  
```
### Результат.
![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_8/images8/3.png)

## Выводы

1. Структура классов: Код представляет два класса — `Car` и `ElectricCar`, где второй наследует первый, позволяя использовать методы и атрибуты.
2. Инициализация объектов: Каждый класс имеет конструктор `(__init__)`, который инициализирует его атрибуты (марка, модель, емкость батареи).
3. Методы: 
   - Метод `drive` демонстрирует возможность "движения" автомобиля и выводит сообщение о автомобиле.
   - Метод `charge` в классе `ElectricCar` позволяет имитировать процесс зарядки электромобиля.
4. При создании объектов классов выводится информации о моделях машин и процессе их зарядки, что демонстрирует инкапсуляцию и использование наследования в ООП.

## Лабораторная работа №4

Реализуйте инкапсуляцию для класса, созданного в первом задании. Создайте защищенный атрибут производителя и приватный атрибут модели. Вызовите защищенный атрибут и заставьте машину поехать. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
# определяем класс Car
class Car:
    # инициализируем новый объект Car с маркой и моделью
    def __init__(self, make, model):
        self._make = make      # защищенный атрибут для производителя
        self.__model = model   # приватный атрибут для модели
    # метод для вождения автомобиля
    def drive(self):
        # выводим сообщение о том, что автомобиль движется
        print(f"Driving the {self._make} {self.__model}")
    # метод для получения защищенного атрибута
    def get_make(self):
        return self._make
# создаем экземпляр класса Car с маркой и моделью
my_car = Car("Toyota", "Corolla")
# выввод
print(my_car.get_make()) 
# вызываем метод drive для объекта my_car, чтобы ехать
my_car.drive() 

```
### Результат.
![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_8/images8/4.png)

## Выводы

1. Определяется класс Car,в котором автомобиль с двумя атрибутами: маркой (make) и моделью (model).
   - Атрибут make помечен как защищенный (_make), предназначен для использования внутри класса и его подклассов.
   - Атрибут model помечен как приватный (__model), препятствует доступу к нему вне класса.
2. Метод __init__ служит конструктором, который инициализирует экземпляр класса и задаёт значения для атрибутов make и model.
3. Метод drive выводит сообщение о том, что автомобиль движется, используя как защищённый, так и приватный атрибуты.
4. Метод get_make: предоставляет доступ к защищённому атрибуту _make, позволяя получать значение марки автомобиля извне класса
5. Создается объект my_car класса Car с маркировкой "Toyota" и моделью "Corolla". Это отображает использование класса на практике и показывает применение инкапсуляции.

## Лабораторная работа №5

Реализуйте полиморфизм создав основной (общий) класс “Shape”, а также еще два класса “Rectangle” и “Circle”. Внутри последних двух классов реализуйте методы для подсчета площади фигуры. После этого создайте массив с фигурами, поместите туда круг и прямоугольник, затем при помощи цикла выведите их площади. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
import math  # импортируем модуль math
# Определяем общий класс Shape
class Shape:
    def area(self):
        raise NotImplementedError("This method should be overridden in subclasses.")
# Определяем класс Rectangle, наследующий от Shape
class Rectangle(Shape):
    def __init__(self, width, height):
        """Инициализируем прямоугольник с заданной шириной и высотой"""
        self.width = width
        self.height = height
    def area(self):
        """Перекрываем метод area для подсчета площади прямоугольника"""
        return self.width * self.height
# Определяем класс Circle, наследующий от Shape
class Circle(Shape):
    def __init__(self, radius):
        """Инициализируем круг с заданным радиусом"""
        self.radius = radius
    def area(self):
        """Перекрываем метод area для подсчета площади круга"""
        return math.pi * (self.radius ** 2)
# список фигур
shapes = []
# добавляем в список экземпляр Rectangle и Circle
shapes.append(Rectangle(8, 12))
shapes.append(Circle(5))
# Цикл для вывода площадей всех фигур
for shape in shapes:
    print(f"Площадь фигуры: {shape.area():.2f}")

```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_8/images8/5.png)

## Выводы

1. Импорт модуля ``: нужен для вычисления площадей
2. Общий класс `Shape`: абстрактный класс с методом area, который не реализован. Он будет переопределен в классах-наследниках.
3. Класс Rectangle:
   - Имеет инициализатор, который принимает ширину и высоту.
   - Переопределяет метод area, который возвращает площадь прямоугольника, рассчитываемую по формуле width * height.
4. Класс `Circle`:
   - Имеет инициализатор, который принимает радиус.
   - Переопределяет метод area, который возвращает площадь круга по формуле π * radius^2.
5. Создание массива shapes: список, который содержит экземпляры классов `Rectangle` и `Circle`.
6. Цикл для вывода площадей: перебираются все фигуры в массиве shapes и вызываем метод area для каждой фигуры, выводя результат в формате с двумя знаками после запятой.


## Самостоятельная работа №1

Самостоятельно создайте класс и его объект. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Company:
    def __init__(self, name, age, gender, profession):
        self.name = name
        self.age = age
        self.gender = gender
        self.profession = profession  
    def show_info(self):
        print(f"Информация о сотруднике:\nИмя: {self.name}\nВозраст: {self.age}\nПол: {self.gender}\nПрофессия: {self.profession}")

    def greet(self):
        print(f"Здравствуйте, {self.name}! Ваша профессия: {self.profession}\n")

employee1 = Company('Василий', 59, 'мужской', 'слесарь')
employee1.show_info()
employee1.greet()

employee2 = Company("Шахноза", 53, "женский", "уборщица")
employee2.show_info()
employee2.greet()

```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_8/images8/11.png)

## Выводы

1. Класс Company определяет структуру для представления человека (сотрудника). Он содержит методы и атрибуты:
     - __init__ – это метод инициализации класса. Когда создается объект этого класса, он принимает параметры:
       - `name` - имя сотрудника
       - `age` - возраст сотрудника
       - `gender` - пол сотрудника
       - `profession` - профессия сотрудника
     - Эти параметры присваиваются атрибутам объекта `(self.name, self.age` и т.д.), чтобы хранить информацию о каждом конкретном сотруднике.

2. Метод `show_info`: выводит информацию о сотруднике: имя, возраст, пол и профессию.

3. Метод `greet`: выводит приветственное сообщение для сотрудника, включая его имя и профессию.

4. Создание объектов `employee1` и `employee2`.

## Самостоятельная работа №2
Самостоятельно создайте атрибуты и методы для ранее созданного класса. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Company:
    def __init__(self, employee_id, name, age, gender, profession, department, salary):
        self.employee_id = employee_id
        self.name = name
        self.age = age
        self.gender = gender
        self.profession = profession
        self.department = department
        self.salary = salary

    def show_info(self):
        print(f"Информация о сотруднике:\n"
              f"ID: {self.employee_id}\n"
              f"Имя: {self.name}\n"
              f"Возраст: {self.age}\n"
              f"Пол: {self.gender}\n"
              f"Профессия: {self.profession}\n"
              f"Отдел: {self.department}\n"
              f"Заработная плата: {self.salary}\n")

    def update_salary(self, new_salary):
        self.salary = new_salary
        print(f"Заработная плата обновлена для {self.name}: {self.salary}")

    def promote(self):
        self.profession = f"старший {self.profession}"
        print(f"{self.name} был повышен на должность: {self.profession}")

    def show_department(self):
        print(f"{self.name} принадлежит к отделу: {self.department}")

employee1 = Company(1, 'Василий', 59, 'мужской', 'слесарь', 'Слесарный', 80000)
employee1.show_info()
employee1.update_salary(95000)
employee1.promote()
employee1.show_department()

employee2 = Company(2, "Шахноза", 53, "женский", "уборщица", "Клининг", 30000)
employee2.show_info()
employee2.update_salary(32000)
employee2.promote()
employee2.show_department()
```
### Результат.
![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_8/images8/12.png)

## Выводы


## Самостоятельная работа №3

Самостоятельно реализуйте наследование, продолжая работать с ранее созданным классом. Оно должно отличаться, от того, что указано в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Company:
    def __init__(self, employee_id, name, age, gender, profession, department, salary):
        self.employee_id = employee_id
        self.name = name
        self.age = age
        self.gender = gender
        self.profession = profession
        self.department = department
        self.salary = salary

    def show_info(self):
        print(f"Информация о сотруднике:\n"
              f"ID: {self.employee_id}\n"
              f"Имя: {self.name}\n"
              f"Возраст: {self.age}\n"
              f"Пол: {self.gender}\n"
              f"Профессия: {self.profession}\n"
              f"Отдел: {self.department}\n"
              f"Заработная плата: {self.salary}\n")

    def update_salary(self, new_salary):
        self.salary = new_salary
        print(f"Заработная плата обновлена для {self.name}: {self.salary}")

    def promote(self):
        self.profession = f"старший {self.profession}"
        print(f"{self.name} был повышен на должность: {self.profession}")

    def show_department(self):
        print(f"{self.name} принадлежит к отделу: {self.department}")
# подкласс Manager
class Manager(Company):
    def __init__(self, employee_id, name, age, gender, profession, department, salary, number_of_reports, department_budget):
        super().__init__(employee_id, name, age, gender, profession, department, salary)
        self.number_of_reports = number_of_reports  # количество подчиненных
        self.department_budget = department_budget  # бюджет отдела
    def allocate_budget(self, amount):
        if amount <= self.department_budget:
            self.department_budget -= amount
            print(f"{self.name} распределил {amount} бюджета. Остаток бюджета: {self.department_budget}")
        else:
            print(f"Недостаточно бюджета для распределения {amount}.")
    def manage_reports(self):
        print(f"{self.name} управляет {self.number_of_reports} подчиненными.")
manager1 = Manager(1, 'Анатолий', 45, 'мужской', 'менеджер', 'Продажи', 90000, 5, 200000)
manager1.show_info()
manager1.manage_reports()
manager1.allocate_budget(15000)
manager1.promote()
manager1.show_department()
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_8/images8/13.png)

## Выводы

1. Класс Company содержит общие атрибуты и методы для сотрудников компании. Он включает в себя информацию о сотрудниках, методы для отображения информации, обновления зарплаты, повышения и отображения отдела.

2. Класс Manager это подкласс , который наследует от класса Company. Он добавляет дополнительные атрибуты (number_of_reports и department_budget) и методы (allocate_budget и manage_reports).


## Самостоятельная работа №4

Самостоятельно реализуйте инкапсуляцию, продолжая работать с ранее созданным классом. Она должна отличаться, от того, что указана в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Company:
    def __init__(self, name, gender, profession):
        self.__name = name          # приватный атрибут
        self.__gender = gender      # приватный атрибут
        self.__profession = profession  # приватный атрибут
    def show_info(self):
        print(f"Информация о сотруднике:\nИмя: {self.__name}\nПол: {self.__gender}\nПрофессия: {self.__profession}")
    def greet(self):
        print(f"Здравствуйте, {self.__name}! Ваша профессия: {self.__profession}\n")
    def update_profession(self, new_profession):
        self.__profession = new_profession
    def get_profession(self):
        return self.__profession

employee1 = Company('Василий', 'мужской', 'слесарь')
employee1.show_info()
employee1.greet()
employee2 = Company("Шахноза", "женский", "уборщица")
employee2.show_info()
employee2.greet()

employee1.update_profession('слесарь-электрик') 
print(f"Новая профессия Василия: {employee1.get_profession()}")

```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_8/images8/14.png)

## Выводы

1. В классе `Company` атрибуты `__name, __gender`и `__profession` объявлены как приватные. Это означает, что они не могут быть доступны напрямую из внешнего кода. Это помогает защитить данные от случайного изменения.
2. Методы `update_profession` и `get_profession`, которые позволяют изменять и получать значение приватного атрибута `__profession`. 

## Самостоятельная работа №5

Самостоятельно реализуйте полиморфизм. Он должен отличаться, от того, что указан в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Employee:
    def __init__(self, name, gender, profession):  
        self.__name = name
        self.__gender = gender
        self.__profession = profession
    def show_info(self):
        raise NotImplementedError("Пожалуйста, реализуйте метод show_info в дочернем классе.")

    def greet(self):
        print(f"Здравствуйте, {self.__name}! Ваша профессия: {self.__profession}\n")
class Worker(Employee):
    def show_info(self):
        print(f"Информация о рабочем:\nИмя: {self._Employee__name}\nПол: {self._Employee__gender}\nПрофессия: {self._Employee__profession}")
class Cleaner(Employee):
    def show_info(self):
        print(f"Информация о уборщице:\nИмя: {self._Employee__name}\nПол: {self._Employee__gender}\nПрофессия: {self._Employee__profession}")
worker1 = Worker('Василий', 'мужской', 'слесарь')
cleaner1 = Cleaner("Шахноза", "женский", "уборщица")
employees = [worker1, cleaner1]
for employee in employees:
    employee.show_info()
    employee.greet()
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_8/images8/15.png)

## Выводы

1. Класс Employee, который определяет метод show_info(). Дочерние классы Worker и Cleaner переопределяют метод show_info(), предоставляя свою реализацию. Это означает, что каждый класс может иметь свою собственную логику для отображения информации о работнике.
2. В цикле for employee in employees: перебирается список employees, содержащий объекты классов Worker и Cleaner. При вызове employee.show_info() и employee.greet()вызывается соответствующий метод для каждого объекта, в зависимости от его класса. 


## Общие выводы по теме

Основные концепции объектно-ориентированного программирования ООП:

1. Классы является шаблонов для создания объектов. Объекты представляют собой экземпляры классов и могут содержать атрибуты и методы.
2. Инкапсуляция скрытие деталей состояния объекта, а также предоставление доступа к объекту только через определенные методы.
3. Наследование позволяет создавать новые классы на основе существующих. Дочерние классы могут наследовать свойства и методы родительских классов.
4. Полиморфизм позволяет использовать объекты разных классов в качестве объектов одного и того же типа.

В данной теме были рассмотрены основы ООП и применены на практике: понятия класса, объекта, наследования, инкапсуляции, полиморфизма и методов. 