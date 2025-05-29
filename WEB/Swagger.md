---
title: Swagger
date of creation: 2025-04-08T22:31:00
tags:
  - API
  - Developing
  - IT
  - Documentation
read status: false
completion status: false
aliases:
---
# Swagger
---

Swagger — это инструмент, который помогает разработчикам создавать, документировать и проверять [API](https://practicum.yandex.ru/blog/chto-takoe-api/). [[API]] — это набор правил и и протоколов, которые позволяют различным системам обмениваться информацией между собой.

API — это общий термин, который применяется в контексте совершенно разных систем. Есть более узкий термин, REST API — это конкретный API, который используется для обмена данными между клиентами и серверами в интернете.

Часть работы с [[REST API]] — это создание описаний работы API: информации о ресурсах, параметрах запросов, возвращаемых данных, конечных точках и других важных вещах. Чтобы автоматизировать это описание, сделать его структурированным и прозрачным, разработчики используют Swagger. А системные аналитики, в свою очередь, с его помощью формируют требования к IT-системам.

*Вот пример части документации, составленной с использованием Swagger:*
```docs
openapi: 3.0.0  
info:  
title: Example API Documentation  
version: 1.0.0  
description: This is an example API documentation for a sample application.  
  
paths:  
/users:  
get:  
summary: Get a list of users  
operationId: getUsers  
description: Retrieves a list of all users in the system.  
responses:  
'200':  
description: A list of users  
content:  
application/json:  
schema:  
$ref: '#/components/schemas/UsersList'  
  
components:  
schemas:  
UsersList:  
type: array  
items:  
type: object  
properties:  
id:  
type: integer  
description: The user's ID  
name:  
type: string  
description: The user's name
```

В этом примере показана часть документации для одного из ресурсов — "/users". Метод "GET" позволяет получить список пользователей.  
  
Документация содержит следующую информацию:  
  
● Заголовок с названием и версией API и описание  
● Описание ресурса с описанием операции  
● Ответ, который будет возвращаться при успешном выполнении операции, с указанием ожидаемого формата (application/json) и модели данных (UsersList)  
● Компоненты, где определена модель данных "UsersList", которая представляет собой массив объектов с полями "id" и "name"  
  
Это лишь небольшой пример, и в реальной документации Swagger может быть ещё больше деталей и дополнительных компонентов, таких как параметры, аутентификация, примеры использования.  
  
Работа с Rest API — один из навыков, которые студенты получают на курсе «Системный аналитик». Они учатся проектировать и описывать взаимодействие систем, в том числе с использованием Swagger.
