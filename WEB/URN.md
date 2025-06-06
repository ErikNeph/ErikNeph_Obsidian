---
title: URN
date of creation: 2025-04-11T20:56:00
tags:
  - Web
  - Web/Terminology
  - Terminology
  - IT/WEB
read status: true
completion status: false
aliases:
---
# URN
---

**URN (Uniform Resource Name)** – это строка символов, которая используется для идентификации какого-либо ресурса, но только по его имени.
>![[URN_diagramm.jpg]]
>URN

В нашем примере это выглядит так. Мы знаем этого человека, знаем, что его зовут Боб. Но мы не знаем, где он живет. Нам придется искать его только по имени.

Важно запомнить такой момент. Все эти три термина находятся в такой условной зависимости (или иерархии), как на картинке ниже. Потому что [[URI]] может использовать и адрес, и имя при идентификации ресурса. В то время как [[URL]] и [[URN]] только адрес и только имя соответственно.

>![[URN_URL_URI_diagram.jpg]]
>Каждый [[URL#^85dd45|URL]] является [[URI#^ebb086|URI]]. Каждый URN является URI. Но не каждый URI, к примеру, является URL (он может быть URN).

**URN** служит для обозначения уникального имени ресурса, неважно, где этот ресурс располагается в данный момент времени или вообще. Такая природа URN (независимость от адреса) позволяет ресурсам перемещаться с одного места на другое. URN позволяет получить доступ к ресурсу по различным сетевым протоколам, обращаясь к одному и тому же имени.

>![[URN_diagram.jpg]]
>. URN позволяет получить доступ к ресурсу по различным сетевым протоколам, обращаясь к одному и тому же имени

На текущий день URN все еще считается экспериментальным и не так сильно распространен, как URL, так как для полной поддержки URN требуется поддерживающая его развитая сетевая инфраструктура.

## Выводы
---

Подводя итог можно сказать, что если мы говорим про сеть Интернет, то чаще всего используем термин URL, так как находим определенный ресурс в сети именно по его адресу на каком-то сервере. Также часто можно встретить аббревиатуру URI, подразумевающую именно URL. Хотя по факту это не совсем так, потому что URL является часть URI. В то же время в контексте веба URN практически не используется.
