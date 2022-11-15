# Урок 4. Строки и словари. Домашнее задание

Привет, это снова Артем Манченков и очередное задание!

Вы уже научились работать с циклами, теперь пора написать проект с использованием строк и словарей! В этом задании всё еще будут циклы (в том числе и бесконечные), но основное внимание будет всё-таки на словарях.

Напомним, что в первом курсе мы разрабатываем на Python консольное  (то есть не имеющее интерфейса) приложение для обучения английскому. 

 

На этот раз мы будем угадывать слова. Проверим вашу грамотность?

Приложение хранит русские и английские слова и предлагает нам угадывать. Чтобы нам было проще, программа выдает подсказки с длиной слова и первой буквой. 

## Пример работы программы

```python
Программа: Выберите уровень сложности.
Программа: Легкий, средний, сложный.
Пользователь: Легкий.
Программа: Выбран уровень сложности, мы предложим 5 слов, подберите перевод. 

Программа: Нажмите Enter.
Пользователь:
Программа: level, 7 букв, начинается на у...
Пользователь: Уровень
Программа: Верно, Level — это уровень.

Программа: Нажмите Enter.
Пользователь:
Программа: Divide, 9 букв, начинается на р...
Пользователь: Объединять.
Программа: Неверно. Divide — это разделять.

(Ещё три раунда.)

Программа: Правильно отвечены слова: 
divide
usual
hidden
mirror
Программа: Неправильно отвечены слова: 
hero
Программа:Ваш ранг: 
Отлично.

(Конец)
```

## Основные объекты

`words_easy, words_medium, words_hard`   — словари формата {”слово”: “перевод”, ...}.

`words` —  словарь формата  {”слово”: “перевод”}.

`levels` — ранги пользователя в зависимости от успехов.

`answers` — словарь с записями о верных и неверных ответах.

## Шаги реализации

### Шаг 0

Создайте словари со словами, которые нужно будет угадывать. 

В каждом словаре должно быть пять пар слов.

```python
words_easy = { 
    "family":"семья", 
    "hand": "рука", 
    "people":"люди", 
    "evening": "вечер",
    "minute":"минута", 
}

words_medium = { 
    "believe":"верить", 
    "feel": "чувствовать", 
    "make":"делать", 
    "open": "открывать",
    "think":"думать", 
}

words_hard   = { 
    "rural":"деревенский", 
    "fortune": "удача", 
    "exercise":"упражнение", 
    "suggest": "предлагать",
    "except":"кроме", 
}
```

Создайте словарь `levels` — это уровни, которые будет получать пользователь после решения задач.

```python
levels = {
   0: "Нулевой", 
   1: "Так себе", 
   2: "Можно лучше", 
   3: "Норм", 
   4: "Хорошо", 
   5: "Отлично",
}
```

Создайте словарь `answers`. В нем будут храниться правильные и неправильные слова.

```python
answers = {}
```

### Шаг 1

Получите у пользователя уровень сложности.

Создайте словарь words, положите в него один из словарей (`words_easy` / `words_medium` / `words_hard`)  в зависимости от выбранной сложности.

Например:

```python
words = words_medium
```

### Шаг 2

Запустите цикл по пяти словам из словаря `words`.

Обратите внимание: вам понадобится и ключ, и значение!

Для каждого слова:

- выведите ключ,
- длину слова,
- первую букву.

```python
Программа: divide, 9 букв, начинается на р...
```

Получите у пользователя ответ, сравните ответ со значением. 

Выведите одно из сообщений (обратите внимание: слово выводится с большой буквы):

```python
Программа: Неверно. Divide — это разделять.
```

```python
Программа: Верно, Level — это уровень.
```

Запишите результат в `answers`. Результаты должны храниться в формате:

```python
{
  "mirror": True,
  "divide": False,
  "usual": True,
  ...
}
```

### Шаг 3

Когда слова закончились, выведите в зависимости от результата:

```python
Правильно отвечены слова: 
divide
usual
hidden
mirror

Неправильно отвечены слова: 
hero
```

### Шаг 4

Посчитайте количество правильно отгаданных слов, например, получив список ключей из `answers`. Используйте его в качестве ключа, чтобы получить ранг пользователя.

Выведите ранг пользователя, например:

```python
Ваш ранг: 
Хорошо
```

## Проверьте себя

- [ ]  Словари созданы верно.
- [ ]  Перебор ключей словаря реализован.
- [ ]  Перебор по ключу-значению реализован.
- [ ]  Динамическое создание словаря реализовано.
- [ ]  Чтение из словаря по индексу реализовано.
- [ ]  Получение букв из строки реализовано.
- [ ]  Изменение регистра реализовано.
- [ ]  Получение ранга реализовано