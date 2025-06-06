---
title: URL
date of creation: 2025-04-11T20:42:00
tags:
  - Web
  - Terminology
  - Web/Terminology
  - Internet
  - IT
  - IT/WEB
read status: true
completion status: false
aliases:
---
# URL
---

**URL** обозначает _Uniform Resource Locator_. URL это лишь адрес, который выдан уникальному ресурсу в интернете. В теории, каждый корректный URL ведёт на уникальный ресурс. Такими ресурсами могут быть HTML-страница, CSS-файл, изображение и т.д. На практике, существуют некоторые исключения, когда, например, URL ведёт на ресурс, который больше не существует или который был перемещён. Поскольку ресурс, доступный по URL, а также сам URL обрабатываются веб-сервером, его владелец должен внимательно следить за размещаемыми ресурсами и связанными с ними URL.

Вот несколько примеров URL:
https://developer.mozilla.org
https://developer.mozilla.org/ru/docs/Learn/
https://developer.mozilla.org/ru/search?q=URL

Каждый из этих URLs могут быть напечатаны в адресной строке браузера, чтобы заставить его загрузить связанную страницу (ресурс).

URL состоит из различных частей, некоторые из которых являются обязательными, а некоторые - факультативными. Рассмотрим наиболее важные части на примере:
http://www.example.com:80/path/to/myfile.html?key1=value1&key2=value2#SomewhereInTheDocument

![[URL_diagramm.jpg]]
***Любой URL состоит из нескольких компонентов. Протокол и хост являются обязательными, все остальные - нет.*** ^85dd45
## [[Протокол]]
---

**`http://`** это протокол. Он отображает, какой протокол браузер должен использовать. Обычно это [[HTTP]]-протокол или его безопасная версия - [[HTTPS]]. Интернет требует эти 2 протокола, но браузеры часто могут использовать и другие протоколы, например `mailto:` (чтобы открыть почтовый клиент) или [[ftp]] для запуска передачи файлов, так что не стоит удивляться, если вы вдруг увидите другие протоколы.


## [[Domain Name]]
---

**`www.example.com`** это [[Domain Name|доменное имя]]. Оно означает, какой веб-сервер должен быть запрошен. В качестве альтернативы может быть использован и [IP-адрес](https://developer.mozilla.org/ru/docs/Glossary/IP_Address), но это делается редко, поскольку запоминать IP сложнее, и это не популярно в интернете.


## [[Port]]
---

**`:80`** это порт. Он отображает технический параметр, используемый для доступа к ресурсам на веб-сервере. Обычно подразумевается, что веб-сервер использует стандартные порты HTTP-протокола (80 для HTTP и 443 для HTTPS) для доступа к своим ресурсам. В любом случае, порт - это факультативная составная часть URL.**`/path/to/myfile.html`** это адрес ресурса на веб-сервере. В прошлом, адрес отображал местоположение реального файла в реальной директории на веб-сервере. В наши дни это чаще всего абстракция, позволяющая обрабатывать адреса и отображать тот или иной контент из баз данных.


## Адрес ресурса
---

`?key1=value1&key2=value2` это дополнительные параметры, которые браузер сообщает веб-серверу. Эти параметры - список пар ключ/значение, которые разделены символом `&`. Веб-сервер может использовать эти параметры для исполнения дополнительных команд перед тем как отдать ресурс. Каждый веб-сервер имеет свои собственные правила обработки этих параметров и узнать их можно, только спросив владельца сервера.


## Якорь
---

`#SomewhereInTheDocument` это якорь на другую часть того же самого ресурса. Якорь представляет собой вид "закладки" внутри ресурса, которая переадресовывает браузер на "заложенную" часть ресурса. В HTML-документе, например, браузер может переместиться в точку, где установлен якорь; в видео- или аудио-документе браузер может перейти к времени, на которое ссылается якорь. Важно отметить, что часть URL после #, которая также известна как идентификатор фрагмента, никогда не посылается на сервер вместе с запросом.

Вам стоит представлять URL как обычный почтовый адрес: _протокол_ обозначает почтовый транспорт, который вы собираетесь использовать,_доменное имя_ - это город, _порт_ - это почтовый индекс; _адрес_ - это номер дома;_параметры_ представляют собой дополнительную информацию, как, например, номер квартиры; и, наконец, _якорь_ представляет собой конкретного получателя, которому вы адресуете своё письмо.
