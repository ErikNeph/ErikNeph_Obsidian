---
title: Последовательность Фибоначчи на Python
date of creation: 2025-01-21T15:56:00
tags:
  - Python/Code
  - Code
  - Python/Useful
  - Developing
  - Example
  - Examples
read status: true
completion status: false
aliases:
  - Фибоначчи на Python
---
---
# Последовательность Фибоначчи

*Решение через цикл* **`for`**:

```python
num = 10

n1, n2 = 1, 1

for i in range(num):
	print(n1, end=" ")
	n1, n2 = n2, n1 + n2

```

*Решение через рекурсию* (временная сложность квадратичная):

```python
def fib(n):
	n = abs(n)
	if n == 0:
		return 0
	elif n == 1:
		return 1
	else:
		return fib(n-1) + fib(n-2)


for i in range(1, 11):
	print(fib(i), end=" ")

```
