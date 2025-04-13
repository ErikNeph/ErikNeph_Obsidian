---
title: random
date of creation: 2025-03-19T03:42:00
tags:
  - IT
  - Developing
  - Developing/Python
  - Python
  - Python/Base
  - Python/Library
  - Library
  - Module
  - Python/Module
  - Python/Developing
read status: true
completion status: true
aliases:
  - Python random
  - random Python
  - python random
---
Официальная документация модуля random: https://docs.python.org/3/library/random.html
# random
---

**Модуль random** управляет генерацией случайных чисел. Его основные функции:

-   `random()`: генерирует случайное число от 0.0 до 1.0
    
-   `randint()`: возвращает случайное число из определенного диапазона
    
-   `randrange()`: возвращает случайное число из определенного набора чисел
    
-   `shuffle()`: перемешивает список
    
-   `choice()`: возвращает случайный элемент списка
    

Функция `random()` возвращает случайное число с плавающей точкой в промежутке от 0.0 до 1.0. Если же нам необходимо число из большего диапазона, скажем от 0 до 100, то мы можем соответственно умножить результат функции random на 100.

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p><p>4</p><p>5</p><p>6</p></td><td><div><p><code>import</code> <code>random</code></p><p><code>number </code><code>=</code> <code>random.random()&nbsp;</code></p><p><code>print</code><code>(number)</code></p><p><code>number </code><code>=</code> <code>random.random() </code><code>*</code> <code>100</code>&nbsp;</p><p><code>print</code><code>(number)</code></p></div></td></tr></tbody></table>

Функция `randint(min, max)` возвращает случайное целое число в промежутке между двумя значениями min и max.

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p><p>4</p></td><td><div><p><code>import</code> <code>random</code></p><p><code>number </code><code>=</code> <code>random.randint(</code><code>20</code><code>, </code><code>35</code><code>)&nbsp;</code></p><p><code>print</code><code>(number)</code></p></div></td></tr></tbody></table>

Функция `randrange()` возвращает случайное целое число из определенного набора чисел. Она имеет три формы:

-   `randrange(stop)`: в качестве набора чисел, из которых происходит извлечение случайного значения, будет использоваться диапазон от 0 до числа stop
    
-   `randrange(start, stop)`: набор чисел представляет диапазон от числа start до числа stop
    
-   `randrange(start, stop, step)`: набор чисел представляет диапазон от числа start до числа stop, при этом каждое число в диапазоне отличается от предыдущего на шаг step
    

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p><p>4</p><p>5</p><p>6</p><p>7</p><p>8</p></td><td><div><p><code>import</code> <code>random</code></p><p><code>number </code><code>=</code> <code>random.randrange(</code><code>10</code><code>)&nbsp;</code></p><p><code>print</code><code>(number)</code></p><p><code>number </code><code>=</code> <code>random.randrange(</code><code>2</code><code>, </code><code>10</code><code>)&nbsp;</code></p><p><code>print</code><code>(number)</code></p><p><code>number </code><code>=</code> <code>random.randrange(</code><code>2</code><code>, </code><code>10</code><code>, </code><code>2</code><code>)&nbsp;</code></p><p><code>print</code><code>(number)</code></p></div></td></tr></tbody></table>

### Работа со списком
---

Для работы со списками в модуле random определены две функции: функция shuffle() перемешивает список случайным образом, а функция choice() возвращает один случайный элемент из списка:

<table><tbody><tr><td><p>1</p><p>2</p><p>3</p><p>4</p><p>5</p></td><td><div><p><code>numbers </code><code>=</code> <code>[</code><code>1</code><code>, </code><code>2</code><code>, </code><code>3</code><code>, </code><code>4</code><code>, </code><code>5</code><code>, </code><code>6</code><code>, </code><code>7</code><code>, </code><code>8</code><code>]</code></p><p><code>random.shuffle(numbers)</code></p><p><code>print</code><code>(numbers)&nbsp;</code></p><p><code>random_number </code><code>=</code> <code>random.choice(numbers)</code></p><p><code>print</code><code>(random_number)</code></p></div></td></tr></tbody></table>