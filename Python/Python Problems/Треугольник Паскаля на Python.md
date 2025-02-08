---
title: Треугольник Паскаля на Python
date of creation: 2025-02-08T13:44:00
tags:
  - Python
  - Python/Problem
  - Python/Task
  - Python/Useful
  - Developing
  - Developing/Python
  - Practice
  - Practicum
  - Task
  - Problem
read status: true
completion status: true
aliases:
  - Треугольник Паскаля на Питоне
---
---
# Треугольник Паскаля на Python

[Задача на wiki](https://ru.wikipedia.org/wiki/%D0%A2%D1%80%D0%B5%D1%83%D0%B3%D0%BE%D0%BB%D1%8C%D0%BD%D0%B8%D0%BA_%D0%9F%D0%B0%D1%81%D0%BA%D0%B0%D0%BB%D1%8F)

```python
def pascal(n):
    # Базовый случай: нулевая строка
    if n == 0:
        return [1]
    
    # Инициализируем первую строку
    row = [1]
    
    # Генерируем строки до n-й
    for i in range(1, n + 1):
        # Новая строка начинается с 1
        new_row = [1]
        # Каждый элемент новой строки (кроме первого и последнего)               равен сумме двух элементов из предыдущей строки
        for j in range(1, i):
            new_row.append(row[j - 1] + row[j])
        # Новая строка заканчивается 1
        new_row.append(1)
        # Обновляем текущую строку
        row = new_row
    
    return row

# Пример использования
n = int(input("Введите номер строки: "))
print(pascal(n))
```

