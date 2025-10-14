---
title: JWT
date of creation: 2025-06-02T18:29:00
tags:
  - Web
  - Abbreviation
  - Backend
  - Terminology
  - IT/Terminology
  - Web/Terminology
  - Authentication
  - IT/Abbreviation
  - Web/Abbreviation
read status: true
completion status: true
aliases:
  - JWT-token
  - JWT-tokens
  - JWT-authorization
  - jwt-token
  - jwt-tokens
  - Json Web Token
  - Json web token
  - json web token
  - JSON Web Token
  - JSON web token
  - Json-Web-Token
  - Json-web-token
  - json-web-token
---
# JWT
---

==**JWT** (Json Web Token) — ключ аутентификации пользователя.== Используется для запросов к защищенным методам API.

JWT-токен состоит из трёх частей, разделенных точками: ==заголовка (header), полезной нагрузки (payload) и подписи (signature)==. Заголовок и полезная нагрузка представляют собой JSON-объекты, закодированные в Base64, а подпись используется для проверки целостности и подлинности токена. 

![](https://habrastorage.org/webt/oq/x9/6o/oqx96ozecxiq4qbsrzrk-dw7n5u.png)
![](https://habrastorage.org/r/w1560/getpro/habr/upload_files/3da/dea/593/3dadea593579174c6a05b4395df33e2a.png)

- **Заголовок (Header):** 
    
    Содержит метаданные о токене, такие как тип токена (например, JWT) и алгоритм, используемый для его подписи (например, HS256). 
    
- **Полезная нагрузка (Payload):** 
    
    Содержит данные, которые необходимо передать. Это могут быть утверждения (claims) о пользователе, такие как его идентификатор, роль или срок действия токена. 
    
- **Подпись (Signature):** 
    
    Создается путем комбинирования закодированных заголовка и полезной нагрузки с секретным ключом и алгоритмом подписи. Подпись гарантирует, что токен не был изменен в процессе передачи.


>Принцип работы JWT
>![[JWT-Принцип работы(диаграмма).excalidraw|800x300]]
