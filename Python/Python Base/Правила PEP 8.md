---
title: Правила PEP 8
date of creation: 2025-01-15
tags:
  - Python
  - Python/PEP
  - Developing
  - Developing/Python
  - IT
  - IT/Python
  - IT/Useful
  - Useful
read status: false
completion status: 
aliases:
  - PEP 8
---
---
# Правила PEP 8


Документ РЕР 8 содержит детализированные правила написания корректно оформленного кода на Python. По мере развития языка этот документ постоянно обновляется. Было бы неплохо, если бы вы прочитали целиком все руководство (https://peps.python.org/pep-0008/). Ниже приведены некоторые правила, которых следует обязательно придерживаться.


## Пробелы :LiSpace:
---

**Пробелы**. В языке Python пробелы имеют синтаксическое значение. Особое значение Руthоn-программисты придают влиянию пробелов на удобочитаемость кода.

- Используйте пробелы, а не символы табуляции, для отступов.
- Используйте по 4 пробела для каждого уровня синтаксически значимых отступов.
- Длина строк не должна превышать 79 символов.
- Дополнительные строки являющиеся продолжением длинных выражений, должны выделяться четырьмя дополнительными пробелами сверх обычного их кол-ва для отступов данного уровня.
- Между определениями функций и классов в файлах следует вставлять две пустые строки.
- Между определениями методов в классах следует вставлять одну пустую строку.
- Не окружайте пробелами индексы элементов списков. вызовы функций и операторы присваивания значений именованным аргументам.
- Помещайте по одному и только одному пробелу до и после оператора присваивания.


## Имена 📛
---

**Имена**. В документе РЕР 8 для различных элементов языка предлагается свой стиль имен. Благодаря этому можно легко определить в процессе чтения кода. какому типу соответствует то или иное имя.

- Имена функций. переменных и атрибутов должны следовать формату **`lowercase_underscore`** (нижний регистр букв. разделение слов символами подчеркивания).
- Имена защищенных атрибутов экземпляра должны следовать формату **`_leading_underscore`** (один символ подчеркивания в начале).
- Имена закрытых атрибутов экземпляра должны следовать фopмaтy **`_leading_underscore`** (два символа подчеркивания в начале).
- Имена классов и исключений должны следовать формату **`CapitalizedWord`** (каждое слово начинается с прописной буквы).
- Константы уровня модуля должны записываться в формате **`ALL_CAPS`** (все буквы прописные. в качестве разделителя используется символ подчеркивания).
- В определениях методов экземпляров классов в качестве имени первого параметра следует всегда указывать **`self`** (это имя ссылается на текущий объект).
- В определениях методов классов в качестве имени первого параметра следует всегда указывать **`cls`** (это имя ссылается на текущий класс).


## Выражения и инструкции
---

**Выражения и инструкции**. Одно из положений дзен-философии Python гласит: "Должен существовать один - и предпочтительно только один - очевидный способ сделать это". В рекомендациях документа РЕР 8 предпринимается попытка кодифицировать такой стиль написания выражений и предложений.

- Используйте встроенные отрицания **`(if а is not b)`**, а не отрицание утвердительных выражений **`(if not а is b)`**.
- Не тестируйте пустые значения (такие, как **`[]`** или **`''`**) проверяя их длину **`(if len(somelist) == 0)`**. Вместо этого используйте проверку **`if not somelist`**, исходя из того, что результат вычисления пустого выражения неявно трактуется как **`False`**.
- То же самое касается и непустых значений (таких, как **`[1]`** или
  **`'hi'`**): в инструкции **`if somelist`** результат вычисления непустого значения неявно трактуется как **`True`**.
- Избегайте записи инструкций **`if`**, циклов **`for`** и **`while`**, а также сложных инструкций **`except`** в одной строке. Размещайте их на нескольких строках, чтобы сделать код более понятным.
- Всегда помещайте инструкции **`import`** в самом начале файла.
- Для импорта модулей всегда используйте их абсолютные имена, а не имена, заданные относительно пути к текущему модулю. Например , чтобы импортировать модуль **`foo`** из пакета **`bar`**, следует использовать инструкцию **`from bar import foo`**, а не просто **`import foo`**.
- Если требуется выполнить относительный импорт, то используйте явный синтаксис: **`from . import foo`**
- Импортируемые модули должны располагаться в разделах, указываемых в следующем порядке: 1) модули стандартных библиотек; 2) модули сторонних разработчиков; 3) ваши собственные модули. В каждом подразделе модули должны располагаться в алфавитном порядке.

>[!info]
>Средство **`Pylint`** (http://www.pylint.org/) - это популярный статический анализатор исходного кода на языке Python. **`Pylint`** обеспечивает автоматическое обнаружение отклонений стиля оформления кода от стандартов РЕР 8 и выявляет многие другие типы распространенных ошибок в программах на языке Python.


## Вывод
---

- Всегда следуйте рекомендациям по оформлению кода Python, изложенным в документе РЕР 8.
- Использование общего с многочисленными членами Руthоn-сообщества стиля оформления кода облегчает коллективную разработку.
- Использование единообразного стиля упрощает изменение кода впоследствии.
