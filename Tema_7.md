# ТЕМА 7. Работа с файлами (ввод, вывод)
Отчет по Теме #7 выполнил(а):
- Ганиева Анастасия Ильсуровна
- ПИЭ-22-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + | - |
| Задание 7 | + | - |
| Задание 8 | + | - |
| Задание 9 | + | - |
| Задание 10 | + | - |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1

Составьте текстовый файл и положите его в одну директорию с программой на Python. Текстовый файл должен состоять минимум из двух строк.

```python
Добрый вечер!
Сегодня понедельник
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/1.png)

## Выводы

Создаем обычный текстовый файл и добавляем в него текст.

## Лабораторная работа №2

Напишите программу, которая выведет только первую строку из вашего файла, при этом используйте конструкцию open()/close().

```python
f = open ('exc1.txt', 'r', encoding='utf-8')
print(f.readline())
f.close()
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/2.png)

## Выводы

Программа выводит первую строку из файла: "Добрый вечер!"

## Лабораторная работа №3

Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию open()/close(). 

```python
file = open('exc1.txt', 'r', encoding='utf-8')
lines = file.readlines()
file.close()
print([line.strip() for line in lines])
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/3.png)

## Выводы
1. Открываем файл exc1.txt в режиме чтения ('r').
- Указываем кодировку UTF-8, чтобы корректно обработать текст.
2. Чтение файла
- Используем метод `readlines()`, который считывает все строки из файла и возвращает их в виде списка
3. Создаем новый список с помощью генератора списков.
- Для каждой строки из списка lines используем метод `strip()`, чтобы удалить лишние пробелы и символы новой строки в начале и конце строки.
- Результат выводится на экран с помощью функции `print()`.
4. В результате программа выводит массив.

## Лабораторная работа №4

Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию with open().

```python
with open('exc1.txt', 'r', encoding='utf-8') as file:
    lines = file.readlines()
print([line.strip() for line in lines])
```
### Результат.
![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/4.png)

## Выводы

1. Используя `with`, мы открываем файл и автоматически он закрывается по завершении блока. 
2. Чтение строк
-Как и в предыдущем варианте, все строки считываются и сохраняются в списке.
3. Обработка и вывод строк
-  `print([line.strip() for line in lines])` Результат выводится так же, как и в предыдущем коде, с использованием метода strip(), чтобы удалить лишние пробелы
4. В результате все строки выводятся в массив.

## Лабораторная работа №5

Напишите программу, которая выведет каждую строку из вашего файла отдельно, при этом используйте конструкцию with open().

```python
with open('exc1.txt', 'r', encoding='utf-8') as file:
    for line in file:
        print(line.strip())
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/5.png)

## Выводы

1. Конструкция `with open(...)` в Python используется для работы с файлами.
-  `with:` это контекстный менеджер, который обеспечивает автоматическое закрытие файла после завершения блока кода.
2. В результате в коде задействована конструкция with open(), а также каждая строка выводится по отдельности.

## Лабораторная работа №6

Напишите программу, которая будет добавлять новую строку в ваш файл, а потом выведет полученный файл в консоль. Вывод можно осуществлять любым способом. Обязательно проверьте сам файл, чтобы изменения в нем тоже отображались.

```python
with open('exc1.txt', 'a', encoding='utf-8') as file:
    file.write('\nЭто новая строка.')
with open('exc1.txt', 'r', encoding='utf-8') as file:
    print(file.read())
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/6.png)

## Выводы

1. Открытие файла
- `'a'` — режим добавления. Если файл уже существует, новые данные будут добавлены в конец файла. 
2. Записываем новую строку
- `file.write('nЭто новая строка.'` добавляет новую строку в файл. Символ n используется для переноса строки, чтобы текст начинался с новой строки.
3. Чтение содержимого файла
- `file.read()` считывает все содержимое файла и возвращает его в виде строки, которая затем выводится на экран.
4. В результате в файл добавлена новая строка.


## Лабораторная работа №7

Напишите программу, которая перепишет всю информацию, которая была у вас в файле до этого, например напишет любые данные из произвольно вами составленного списка. Также не забудьте проверить что измененная вами информация сохранилась в файле. 

```python
data = ['Изменение номер 1', 'Изменение номер 2', 'Изменение номер 3']
with open('exc1.txt', 'w', encoding='utf-8') as file:
    for line in data:
        file.write(line + '\n')
with open('exc1.txt', 'r', encoding='utf-8') as file:
    print(file.read())
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/7.png)

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/77.png)

## Выводы

1. Создание списка данных
-  `data = ['Изменение номер 1', 'Изменение номер 2', 'Изменение номер 3']`
2. Итерация по данным и запись:
 - Проходим по каждой строке в списке data.
 - Для каждой строки используем метод write(), добавляя символ новой строки (\n) после каждой записи, чтобы строки не сливались в одну.
3. Чтение данных и вывод.
4. В результате в файле появится новые строки, изменения сохраняются.

## Лабораторная работа №8

Выберите любую папку на своем компьютере, имеющую вложенные директории. Выведите на печать в терминал ее содержимое, как и всех подкаталогов при помощи функции print_docs(directory).

```python
import os
def print_docs(directory):
    all_files = os.walk(directory)
    for catalog in all_files:
        print(f'Папка {catalog[0]} содержит:')
        print(f'Директории:  {", ".join(catalog[1])}')
        print(f'Файлы:  {", ".join(catalog[2])}')
        print('-' * 40)

print_docs(r'C:\\Users\\Nastya\\PycharmProjects\\pythonProject5')
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/8.png)

## Выводы

1. Импорт модуля `os`: 
- Это стандартный модуль Python, который предоставляет множество функций для работы с файлами и директориями. В данном случае он используется для навигации по файловой системе.
2. Функция `print_docs(directory):` 
- Принимает в качестве параметра путь к директории и выполняет обход файлов в ней.
- Использование directory в функции позволяет легко изменять путь при вызове.
3. os.walk(directory):
- Генерирует кортежи, где каждый кортеж состоит из:
     - `catalog[0]:` Путь к текущей папке.
     - `catalog[1]:` Список поддиректорий в текущей папке.
     - `catalog[2]:` Список файлов в текущей папке.
4. Разделитель:
- `print('-' * 40)` добавляет визуальный разделитель между выводами разных папок, что улучшает читабельность.

## Лабораторная работа №9

Документ «input.txt» содержит следующий текст: 
Приветствие
Спасибо 
Извините 
Пожалуйста 
До свидания 
Ты готов?
Как дела?
С днем рождения! 
Удача!
Я тебя люблю.
Требуется реализовать функцию, которая выводит слово, имеющее максимальную длину (или список слов, если таковых несколько).
Проверьте работоспособность программы на своем наборе данных.

```python
def max_l(filename):
    with open(filename, 'r', encoding='utf-8') as file:
        words = file.read().split()
    max_length = max(len(word) for word in words)
    longest_word = next(word for word in words if len(word) == max_length)
    return longest_word
print(max_l('exc1.txt'))
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/9.png)

## Выводы

1. Определение функции:
- Функция `max_l` принимает один аргумент — имя файла `(filename)`, из которого будет извлекаться информация.
2. Открытие файла:
- Используется конструкция `with open(...)`, которая автоматически закрывает файл после завершения работы с ним. 
3. Чтение и разбиение текста:
- Содержимое файла считывается с помощью `file.read()`, а затем разбивается на отдельные слова с помощью метода `.split()`. 
4. Поиск максимальной длины слова:
- Используется  выражение `len(word) for word in words`, чтобы получить длины всех слов в списке, и функция `max()` находит максимальное значение среди них.
5. Поиск самого длинного слова:
- Функция `next()` используется для нахождения первого слова, длина которого равна ` max_length`. Генераторное выражение внутри `next()` перебирает слова и возвращает первое подходящее.
6. Возврат результата:
- Функция возвращает самое длинное слово, найденное в файле.
7. Вызов функции и вывод результата:
- Функция `max_l` вызывается с именем файла `'exc1.txt'`, и результат (самое длинное слово) выводится на экран с помощью `print()`.

## Лабораторная работа №10

Требуется создать csv-файл «rows_300.csv» со следующими столбцами:
•	№ - номер по порядку (от 1 до 300);
•	Секунда – текущая секунда на вашем ПК;
•	Микросекунда – текущая миллисекунда на часах.
Для наглядности на каждой итерации цикла искусственно приостанавливайте скрипт на 0,01 секунду.

```python
import csv
import time
with open('file_csv.csv', 'w', newline='') as csvfile:
    writer = csv.writer(csvfile)
    writer.writerow(['№', 'Секунда', 'Микросекунда'])
    for i in range(1, 301):
        seconds = time.localtime().tm_sec
        microseconds = int(time.time() * 1e6) % 1e6
        print(f"Строка {i}: Секунды - {seconds}, Микросекунды - {microseconds}")
        writer.writerow([i, seconds, microseconds])
        time.sleep(0.01)
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/10.png)

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/1010.png)

## Выводы

1. Импорт библиотек:
- ` import csv` 
- `import time` 
2. Создание файла `file_csv.csv` для записи ('w'). Первая строка CSV-файла будет заголовком с названиями колонок: `№, Секунда, Микросекунда`.
3. Выполнение цикла:
- Цикл будет выполнять 300 итераций (от 1 до 300).
   - В каждой итерации извлекается текущее значение секунд (seconds) и вычисляются микросекунды (microseconds).
   - Затем выводится сообщение в консоль, показывающее номер строки, секунды и микросекунды.
   - Данные записываются в файл CSV.
   - В конце каждой итерации программа «засыпает» на 0.01 секунды.
4. В результате создается csv файл. 

## Самостоятельная работа №1

Найдите в интернете любую статью (объем статьи не менее 200 слов), скопируйте ее содержимое в файл и напишите программу, которая считает количество слов в текстовом файле и определит самое часто встречающееся слово. Результатом выполнения задачи будет: скриншот файла со статьей, листинг кода, и вывод в консоль, в котором будет указана вся необходимая информация.

```python
from collections import Counter
import re
def count_words_and_most_common(filename):
    with open(filename, 'r', encoding='utf-8') as file:
        text = file.read()
    words = re.findall(r'\b\w+\b', text.lower())
    total_words = len(words)
    word_counts = Counter(words)
    most_common_word, most_common_count = word_counts.most_common(1)[0]
    print(f'Общее количество слов: {total_words}')
    print(f'Самое частое слово: "{most_common_word}" (встречается {most_common_count} раз)')
count_words_and_most_common('roman.txt')
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/11.png)

Статья:

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/111.png)

## Выводы

1. Импорт библиотек:
- Импортируем модуль Counter из коллекций, который позволяет легко подсчитывать количество слов, и модуль re для работы с регулярными выражениями.
2. Функция `count_words_and_most_common` принимает имя файла как параметр.
3. Файл открывается для чтения, и его содержимое загружается в переменную text.
4. Извлечение слов:
- `words = re.findall(r'\b\w+\b', text.lower())` находится все слова в тексте, переводя их в нижний регистр. Слова определяются последовательностями букв, и символы, не являющиеся буквами, игнорируются.
5. Подсчет общего количества слов:
- `total_words = len(words)` переменная `total_words` будет хранить общее количество найденных слов.
6. Подсчет частоты каждого слова:
- `word_counts = Counter(words)` создаётся словарь с подсчетом каждой уникального слова.
7. Поиск самого частого слова:
- `most_common_word, most_common_count = word_counts.most_common(1)[0]`
- `most_common(1)` возвращает список с одним элементом в виде кортежа, и мы извлекаем его в отдельные переменные.
8. Вывод результатов

## Самостоятельная работа №2

У вас появилась потребность в ведении книги расходов, посмотрев все существующие варианты вы пришли к выводу что вас ничего не устраивает и нужно все делать самому. Напишите программу для учета расходов. Программа должна позволять вводить информацию о расходах, сохранять ее в файл и выводить существующие данные в консоль. Ввод информации происходит через консоль. Результатом выполнения задачи будет: скриншот файла с учетом расходов, листинг кода, и вывод в консоль, с демонстрацией работоспособности программы.

```python
def add_expense():
    date = input("Введите дату расхода (в формате ДД-ММ-ГГГГ): ")
    description = input("Введите категорию расхода: ")
    amount = input("Введите сумму расходов: ")
    with open('расходы.txt', 'a', encoding='utf-8') as file:
        file.write(f'{date}: {description}: {amount}\n')

def show_expenses():
    print("Записи расходов:")
    try:
        with open('расходы.txt', 'r', encoding='utf-8') as file:
            for line in file:
                date, description, amount = line.strip().split(': ')
                print(f"Дата: {date}")
                print(f"Категория: {description}")
                print(f"Сумма: {amount}\n")
    except FileNotFoundError:
        print("Нет записей расходов.")

while True:
    action = input("Введите '1' для добавления расхода или '2' для вывода всех расходов: ").strip()
    if action == '1':
        add_expense()
    elif action == '2':
        show_expenses()
    else:
        print("Вы ошиблись при вводе данных,пробуйте еще раз")
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/122.png)

Файл, в который записываются расходы:

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/12.png)
![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/121.png)
## Выводы

1. Программа позволяет вести дневник рассходов. Пользователь вводит данные самостоятельно: дата расхода, категория, стоиимость. Также есть возможность просматривать все записи.
2. Данные сохраняются в текстовом файле расходы.txt.
3. Программа работает в цикле, позволяя пользователю выполнять действия до тех пор, пока он не решит выйти.

## Самостоятельная работа №3

Имеется файл input.txt с текстом на латинице. Напишите программу, которая выводит следующую статистику по тексту: количество букв латинского алфавита; число слов; число строк.
•	Текст в файле: Beautiful is better than ugly. Explicit is better than implicit. Simple is better than complex.
Complex is better than complicated.
•	Ожидаемый результат: Input file contains:
108 letters
20 words
4 lines

```python
def count_text_statistics(file_path):
    total_letters = 0
    total_words = 0
    total_lines = 0
    with open(file_path, 'r', encoding='utf-8') as file:
        for line in file:
            total_lines += 1 
            words = line.split()
            total_words += len(words)
            for char in line:
                if char.isalpha() and char.isascii():
                    total_letters += 1
    return total_letters, total_words, total_lines
file_path = 'input.txt'
letters, words, lines = count_text_statistics(file_path)

print(f"Input file contains:\n{letters} letters\n{words} words\n{lines} lines")

```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/13.png)

## Выводы

1. Функция `count_text_statistics(file_path):`
- Принимает путь к файлу в качестве аргумента.
- Инициализирует счетчики для букв, слов и строк `(total_letters, total_words, total_lines)`.
- Открывает файл для чтения с кодировкой UTF-8.
- Для каждой строки файла разделяет строку на слова и увеличивает счетчик слов на количество найденных слов. Для каждого символа в строке проверяет, является ли он буквой (латинской) и увеличивает счетчик букв, если условие выполняется.
2. Функция:
- Путь к файлу задается переменной `file_path`.
- Вызывается функция `count_text_statistics`, и результат сохраняется в переменные letters, words и lines.
3. Вывод результата

## Самостоятельная работа №4

Напишите программу, которая получает на вход предложение, выводит его в терминал, заменяя все запрещенные слова звездочками * (количество звездочек равно количеству букв в слове). Запрещенные слова, разделенные символом пробела, хранятся в текстовом файле input.txt. Все слова в этом файле записаны в нижнем регистре. Программа должна заменить запрещенные слова, где бы они ни встречались, даже в середине другого слова. Замена производится независимо от регистра: если файл input.txt содержит запрещенное слово exam, то слова exam, Exam, ExaM, EXAM и exAm должны быть заменены на ****.
•  Запрещенные слова:
hello email python the exam wor is
•  Предложение для проверки:
Hello, world! Python IS the programming language of thE future. My EMAIL is gai2004@list.ru
PYTHON is awesome!!!!
•  Ожидаемый результат:
*****, ***ld! ******  *** programming language of *** future. My
*****  gai2004@list.ru
****** ** awesome!!!!

```python
def load_forbidden_words(file_path):
    with open(file_path, 'r', encoding='utf-8') as file:
        forbidden_words = file.read().strip().split()
    return forbidden_words
def replace_forbidden_words(sentence, forbidden_words):
    for word in forbidden_words:
        sentence = sentence.replace(word, '*' * len(word))                  
        sentence = sentence.replace(word.capitalize(), '*' * len(word))    
        sentence = sentence.replace(word.upper(), '*' * len(word))          
        sentence = sentence.replace(word[0].upper() + word[1:], '*' * len(word) + word[1:]) 
    return sentence
file_path = 'input.txt'
forbidden_words = load_forbidden_words(file_path)
input_sentence = "Hello, world! Python IS the programming language of thE future. My EMAIL is gai2004@list.ru\nPYTHON is awesome!!!!"
output_sentence = replace_forbidden_words(input_sentence, forbidden_words)
print(output_sentence)
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/14.png)

## Выводы

1. Функция добавления запрещенных слов:
- `load_forbidden_words(file_path)`: открывает файл input.txt для чтения, читает содержимое файла, удаляет лишние пробелы и разделяет строку на слова, формируя список запрещенных слов.
2. Функция замены запрещенных слов:
- `replace_forbidden_words(sentence, forbidden_words):` принимает строку sentence и список forbidden_words.
- Для каждого запрещенного слова выполняется замены:
    - Заменяет слово в низком регистре.
    - Заменяет слово с первой заглавной буквой.
    - Заменяет слово в полном верхнем регистре.
    - Заменяет слово, если первая буква заглавная, а остальные - маленькие.
    - Замена производится на строку, состоящую из символов *, где количество звёздочек соответствует длине слова.
3. Обработка входных данных:
- Определяется путь к файлу `input.txt`, из которого загружаются запрещенные слова.
- Определяется тестовая строка `input_sentence`, в которой будут заменены запрещенные слова.
4. Вывод результата.

## Самостоятельная работа №5

Самостоятельно придумайте и решите задачу, которая будет взаимодействовать с текстовым файлом.

Напишем программу, которая загружает текст из файла, подсчитывает количество слов в тексте и выводит количество уникальных слов, а также частоту появления каждого слова. Результаты сохраняются в новый файл.

```python
import re
from collections import Counter
def load_text(file_path):
    """Загрузка текста из файла"""
    with open(file_path, 'r', encoding='utf-8') as file:
        return file.read()
def count_words(text):
    words = re.findall(r'\b\w+\b', text.lower())
    return Counter(words)
def save_results(word_counts, output_file):
    with open(output_file, 'w', encoding='utf-8') as file:
        file.write(f"Количество уникальных слов: {len(word_counts)}\n\n")
        file.write("Частота слов:\n")
        for word, count in word_counts.items():
            file.write(f"{word}: {count}\n")
input_file = 'input.txt'
output_file = 'output.txt'
text = load_text(input_file)
word_counts = count_words(text)
save_results(word_counts, output_file)
print(f"Результаты сохранены в '{output_file}'")
```
### Результат.

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/15.png)

Текст для работы

![image](https://github.com/GanievaAnastasiia/Software_Engineering/blob/Тема_7/images7/155.png)

## Выводы

1. Программа загружает текст из файла `input.txt.`
2. Подсчитывает все слова, игнорируя регистр и пунктуацию.
3. Сохраняет результаты в файл `output.txt`, где будет указано количество уникальных слов и частота появления каждого слова.

## Общие выводы по теме

1. Работа с файлами 
- При работе с текстовыми файлами необходимо учитывать кодировки (например UTF-8), чтобы избежать проблем с отображением символов
- Использование конструкции with позволяет автоматически закрывать файл после завершения работы с ним, что является хорошей практикой
2. Основные операции
- Основные операции с файлами включают открытие (с помощью функции `open())`, чтение `(read()`, `readline()`, `readlines())`, запись (`write()`, `writelines())` и закрытие (`close()`).
- Поддержка различных режимов открытия файлов, таких как `r` (чтение), `w` (запись), `a` (добавление), `rb` (чтение в двоичном режиме), позволяет гибко управлять доступом к файлам.
3. Чтение
- Функции чтения позволяют загружать данные как целиком, построчно или в виде списка строк.
- Запись данных более чем одной строки осуществляется с помощью метода `writelines()`, что позволяет эффективно сохранять данные в файл.
4. В ходе данной лабораторной работы был успешно применены теоретические значния работы с файлами на практине. 