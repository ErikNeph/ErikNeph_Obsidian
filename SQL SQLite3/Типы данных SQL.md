
При разработке базы данных с использованием SQL для каждого используемого столбца должен быть назначен определенный тип данных. Типы данных могут незначительно отличаться в зависимости от используемой версии SQL. Однако, как правило, у вас будут числовые, символьные или текстовые типы данных, дата и время,
а также логические значения. Рассмотрим каждый из них


## Числовые типы данных

В состав *числовых данных* входят целочисленные данные, которые служат для отображения целых чисел. Обычно, когда используется целочисленный тип данных, он имеет ограничения на длину. Напомним, что изображенная на рис. 7 таблица содержала сведения о пациентах. Для столбца Weight (Вес) разумно использовать целочисленный тип данных с ограничением до трех цифр. Почему?

1. Вполне достаточно округлить значение в большую и меньшую сторону до ближайшего значения фунта или килограмма и не использовать десятичные знаки.
2. Вряд ли нам понадобится более трех цифр для указания значения веса в фунтах.

Когда целочисленные данные не подходят и возникает необходимость в более точном числовом формате, мы можем использовать формат чисел с плавающей запятой. Как и целочисленные данные, они могут быть ограничены по
длине.

![[числовые данные.jpg]]
### ПРИМЕЧАНИЕ
*Для типов данных, допускающих более длинные диапазоны цифр, символов и т. д., требуется больший объем памяти в байтах. SQL также допускает*
*денежные (финансовые) типы данных.*


## Символьные, или текстовые, типы данных

*Символьные, или текстовые, типы данных* (еще их называют «строковые») могут хранить строки символов как фиксированной, так и переменной длины. Например, если один из столбцов вашей базы данных содержит стандартные шестизначные почтовые индексы Канады (которые включают как цифры, так и буквы), то вам необходимо использовать символьный, или текстовый, тип данных со строкой фиксированной длины из шести символов. Если вы создавали столбец для хранения имени или фамилии клиента, вам необходимо использовать строку переменной длины с ограничением по максимальной
и минимальной длине.

![[Символьные или текстовые данные.jpg]]


## Дата и время

*Дата и время* — эти данные важны во многих случаях. SQL предлагает пользователям различные форматы даты и времени: YYYY-MM-DD (ГГГГ-ММ-ДД), YYYY-MM-DD HH:MI:SS (ГГГГ-ММ-ДД ЧЧ:МИ:СС), YY-MM-DD (ГГ-ММДД). Вы также можете отформатировать столбец так, чтобы он содержал только год, в четырех- или двухзначном формате. Например, 2019 или просто 19. На
рис. 18 показан пример использования данных даты и времени.

![[Дата и время.jpg]]


## Логический тип данных

*Логические значения* — это данные, принимающие значения True (Правда) или False (Ложь). Например, если вы отвечаете за секретную операцию для правительства или частного лица, вы можете использовать базу данных для отслеживания уровня допуска сотрудников. Если вам необходимо найти список сотрудников с допусками A, B и D, но не обязательно C, то использование логического анализа данных может значительно упростить процесс. На рис. 19
показан пример использования логических данных.

![[Логические данные.jpg]]

### Примечание

*В разных версиях SQL — разные списки распознаваемых типов данных. Некоторые версии SQL, такие как SQL Server и MySQL (описаны далее в этой главе), не дают пользователю возможности присвоить данным тип Boolean. Вместо этого они предоставляют тип данных Bit, который может быть легко преобразован в логический формат.*


## Системы управления реляционными базами данных

SQL применяется в целом ряде программных пакетов, известных как *реляционные системы управления базами данных* (РСУБД). Эти системы упрощают применение SQL, когда пользователь дает команды и задает вопросы базе данных. Наиболее распространенные СУБД — это Oracle Database, Microsoft SQL Server, MySQL, IBM Db2 и SQLite.

![[РСУБД ы.jpg]]

Некоторые РСУБД изначально представлены в графическом виде, другие — в текстовом. РСУБД также различают по подходу к SQL. Ранее в этой главе мы уже упоминали об одной такой аномалии при обработке логических данных. РСУБД действительно различаются по способу представления информации
базы данных.

Тот факт, что мы сообщаем РСУБД, какую информацию нам предоставлять, определяет SQL как декларативный язык программирования. Это отличает его от таких языков программирования, как C++, Java и т. д. Они являются более процедурными, так как с их помощью программа создается от начала до конца (распределяется память, в том числе для существующих справочных файлов, и т. д.). В случае SQL все распределение памяти и другие действия выполняются
РСУБД.

==Читайте также далее об== - [[Типы функций в SQL]]