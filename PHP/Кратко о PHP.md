---
tags:
  - Programming
  - ProgrammingLanguage
  - Developing
  - Backend
  - WebDeveloping
  - IT
  - PHP
date: 2023-05-24T22:09:00
---
# Кратко о [[PHP]]

Использование PHP существенно упрощает встраивание средств, придающих веб-страницам динамические свойства. Когда страницам присваивается расширение [[PHP]], у них появляется прямой доступ к языку сценариев. Разработчику нужно лишь написать код, похожий на этот:

```PHP
<?php
  echo " Сегодня " . date('T') . ". ";
?>
Последние новости.
```

Открывающий тег `<?php` дает веб-серверу разрешение на интерпретацию всего последующего кода вплоть до тега `?>`. Все, что находится за пределами этой конструкции, отправляется клиенту в виде простого HTML. Поэтому текст Последние новости просто выводится в браузер. А внутри PHP-тегов встроенная функция `date()` отображает текущий день недели, соответствующий системному времени сервера.

В итоге на выходе из этих двух частей получается примерно следующее: `Сегодня Wednesday. Последние новости.`

PHP — довольно гибкий язык, и некоторые разработчики предпочитают помещать PHP-конструкцию непосредственно рядом с кодом PHP, как в этом примере:

```PHP
Сегодня <?php echo date("l"); ?>. Последние новости.
```

Существуют также другие способы форматирования и вывода информации, которые будут рассмотрены в главах, посвященных PHP. Важно усвоить то, что, используя PHP, веб-разработчики получают язык сценариев, который хотя и не обладает быстротой кода, скомпилированного на C или ему подобных языках, но все же работает невероятно быстро и к тому же очень хорошо вписывается в разметку HTML.

Используя PHP, вы получаете средство управления своим веб-сервером с неограниченными возможностями. Если понадобится на лету внести изменения в HTML, обработать данные кредитной карты, добавить сведения о пользователе в базу данных или извлечь информацию из стороннего сайта, все это можно будет сделать из тех же самых PHP-файлов, в которых находится и сам код HTML. Следующий раздел -> [[Введение в PHP]]


**Cмотри далее**: [[Выражения и управление процессом выполнения программы в PHP]]
