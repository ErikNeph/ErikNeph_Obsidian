---
title: SCRAM
date of creation: 2025-06-19T13:30:00
tags:
  - Web
  - Authentication
  - Developing
  - Backend
  - IT
  - IT/Terminology
  - Web/Terminology
  - IT/WEB
read status: false
completion status: false
aliases:
---
# SCRAM
---

**SCRAM** (Salted Challenge Response Authentication Mechanism, [RFC 5802](https://tools.ietf.org/html/rfc5802). Дата обращения: 27 декабря 2013. [Архивировано](https://web.archive.org/web/20131218104220/http://tools.ietf.org/html/rfc5802) 18 декабря 2013 года.) — [механизм](https://ru.wikipedia.org/wiki/%D0%9C%D0%B5%D1%85%D0%B0%D0%BD%D0%B8%D0%B7%D0%BC "Механизм") хранения данных и [протокол](https://ru.wikipedia.org/wiki/%D0%9F%D1%80%D0%BE%D1%82%D0%BE%D0%BA%D0%BE%D0%BB_%D0%BF%D0%B5%D1%80%D0%B5%D0%B4%D0%B0%D1%87%D0%B8_%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 "Протокол передачи данных") [аутентификации](https://ru.wikipedia.org/wiki/%D0%90%D1%83%D1%82%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F "Аутентификация") посредством [пароля](https://ru.wikipedia.org/wiki/%D0%9F%D0%B0%D1%80%D0%BE%D0%BB%D1%8C "Пароль"). SCRAM относится к механизмам [SASL](https://ru.wikipedia.org/wiki/SASL "SASL") уровня, что делает возможным его использование вместе с некоторыми стандартными протоколами, использующими SASL: [SMTP](https://ru.wikipedia.org/wiki/SMTP "SMTP"), [LDAP](https://ru.wikipedia.org/wiki/LDAP "LDAP"), [IMAP](https://ru.wikipedia.org/wiki/IMAP "IMAP") и [POP](https://ru.wikipedia.org/wiki/POP "POP"). Также Scram является [GSS-API](https://ru.wikipedia.org/wiki/GSS-API "GSS-API") механизмом. Поддерживает привязку канала и двухстороннюю аутентификацию. На момент написания статьи (январь 2013) является наиболее совершенным и многофункциональным.


## Предпосылки
---

- Необходимость в механизме, который бы поддерживал все новые возможности описанные в SASL: поддержка интернационализованных [логинов](https://ru.wikipedia.org/wiki/%D0%9B%D0%BE%D0%B3%D0%B8%D0%BD_\(%D1%83%D1%87%D1%91%D1%82%D0%BD%D0%B0%D1%8F_%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8C\) "Логин (учётная запись)") и паролей, поддержка осуществления единственности аутентификации, поддержка привязки канала
- Потребность в протоколе двухсторонней аутентификации
- Желание чтобы хранимая в идентификационной [базе данных](https://ru.wikipedia.org/wiki/%D0%91%D0%B0%D0%B7%D0%B0_%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 "База данных") информация была недостаточной для того, чтобы злоумышленник мог выдать себя за клиента.
- Необходимость в том, чтобы у [сервера](https://ru.wikipedia.org/wiki/%D0%A1%D0%B5%D1%80%D0%B2%D0%B5%D1%80_\(%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%BD%D0%BE%D0%B5_%D0%BE%D0%B1%D0%B5%D1%81%D0%BF%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5\) "Сервер (программное обеспечение)") не было возможности выдать себя за [клиента](https://ru.wikipedia.org/wiki/%D0%9A%D0%BB%D0%B8%D0%B5%D0%BD%D1%82_\(%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D0%B8%D0%BA%D0%B0\) "Клиент (информатика)") перед другим сервером(исключая [прокси-сервер](https://ru.wikipedia.org/wiki/%D0%9F%D1%80%D0%BE%D0%BA%D1%81%D0%B8-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80 "Прокси-сервер") авторизации).
- Существенная необходимость в механизме, который проще в реализации, чем уже имеющийся(DIGEST-MD5

В целом, все предпосылки отражают недостатки других механизмов аутентификации. Поэтому в июне 2010 был создан SCRAM, лишенный проблем других механизмов, и отвечающий запросам своего времени
