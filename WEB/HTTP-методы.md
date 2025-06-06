---
title: HTTP-методы
date of creation: 2025-06-03T20:24:00
tags:
  - Protocol
  - Web
  - Web/Protocol
  - Terminology
  - Web/Terminology
read status: true
completion status: false
aliases:
---
# HTTP-методы
---

HTTP определяет множество **методов запроса**, которые указывают, какое желаемое действие выполнится для данного ресурса. Несмотря на то, что их названия могут быть существительными, эти методы запроса иногда называются _HTTP глаголами_. Каждый реализует свою семантику, но каждая группа команд разделяет общие свойства: так, методы могут быть [безопасными](https://developer.mozilla.org/ru/docs/Glossary/Safe), [идемпотентными](https://developer.mozilla.org/ru/docs/Glossary/Idempotent) или [кешируемыми](https://developer.mozilla.org/ru/docs/Glossary/Cacheable).

[`GET`](https://developer.mozilla.org/ru/docs/Web/HTTP/Reference/Methods/GET)

Метод `GET` запрашивает представление ресурса. Запросы с использованием этого метода могут только извлекать данные.

[`HEAD`](https://developer.mozilla.org/ru/docs/Web/HTTP/Reference/Methods/HEAD)

`HEAD` запрашивает ресурс так же, как и метод GET, но без тела ответа.

[`POST`](https://developer.mozilla.org/ru/docs/Web/HTTP/Reference/Methods/POST)

`POST` используется для отправки сущностей к определённому ресурсу. Часто вызывает изменение состояния или какие-то побочные эффекты на сервере.

[`PUT`](https://developer.mozilla.org/ru/docs/Web/HTTP/Reference/Methods/PUT)

`PUT` заменяет все текущие представления ресурса данными запроса.

[`DELETE`](https://developer.mozilla.org/ru/docs/Web/HTTP/Reference/Methods/DELETE)

`DELETE` удаляет указанный ресурс.

[`CONNECT`](https://developer.mozilla.org/ru/docs/Web/HTTP/Reference/Methods/CONNECT)

`CONNECT` устанавливает "туннель" к серверу, определённому по ресурсу.

[`OPTIONS`](https://developer.mozilla.org/ru/docs/Web/HTTP/Reference/Methods/OPTIONS)

`OPTIONS` используется для описания параметров соединения с ресурсом.

[`TRACE`](https://developer.mozilla.org/ru/docs/Web/HTTP/Reference/Methods/TRACE)

`TRACE` выполняет вызов возвращаемого тестового сообщения с ресурса.

[`PATCH`](https://developer.mozilla.org/ru/docs/Web/HTTP/Reference/Methods/PATCH)

`PATCH` используется для частичного изменения ресурса.

## [Спецификации](https://developer.mozilla.org/ru/docs/Web/HTTP/Reference/Methods#%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8)

| Спецификация | Название | Комментарий |
| --- | --- | --- |
| [RFC 7231, раздел 4: Request methods](https://datatracker.ietf.org/doc/html/rfc7231#section-4) | Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content | Определение GET, HEAD, POST, PUT, DELETE, CONNECT, OPTIONS, TRACE. |
| [RFC 5789, раздел 2: Patch method](https://datatracker.ietf.org/doc/html/rfc5789#section-2) | PATCH метод для HTTP | Определение PATCH. |

## [Совместимость с браузерами](https://developer.mozilla.org/ru/docs/Web/HTTP/Reference/Methods#%D1%81%D0%BE%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%B8%D0%BC%D0%BE%D1%81%D1%82%D1%8C_%D1%81_%D0%B1%D1%80%D0%B0%D1%83%D0%B7%D0%B5%D1%80%D0%B0%D0%BC%D0%B8)

## [Смотрите также](https://developer.mozilla.org/ru/docs/Web/HTTP/Reference/Methods#%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5_%D1%82%D0%B0%D0%BA%D0%B6%D0%B5)
