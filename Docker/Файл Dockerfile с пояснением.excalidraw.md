---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - Docker
  - Developing
  - Diagrams
---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠== You can decompress Drawing data with the command palette: 'Decompress current Excalidraw file'. For more info check in plugin settings under 'Saving'



# Code Block

```dockerfile
FROM node
LABEL maintener ian.miell@gmail.com
RUN git clone -q https://github.com/docker-in-practice/todo.git
WORKDIR todo
RUN npm install > /dev/null
EXPOSE 8000
CMD ["npm", "start"]
```


# Code Block 1

```dockerfile
FROM node
LABEL maintener ian.miell@gmail.com
RUN git clone -q https://github.com/docker-in-practice/todo.git
WORKDIR todo
RUN npm install > /dev/null
EXPOSE 8000
CMD ["npm", "start"]
```

# Excalidraw Data

## Text Elements
FROM node
LABEL maintener ian.miell@gmail.com
RUN git clone -q https://github.com/docker-in-practice/todo.git
WORKDIR todo
RUN npm install > /dev/null
EXPOSE 8000
CMD ["npm", "start"] ^bq8ngKSD

Определяет базовый образ ^FICV7v4m

Объявляет автора ^Q6cEWfls

Клонирует код приложения ^cUESJNMG

Перемещает в новый клонированный каталог ^G8elwNSy

Запускает команду установки менеджера пакетов (npm) ^6TuMls34

Указывает,что контейнеры из собранного образа
будут прослушивать этот порт  ^jaBNlL5M

Указывает, какая команда будет запущена при запуске ^zOv53hs8

Файл Dockerfile начинается с определения базового образа с помощью команды FROM.
В этом примере используется образ Node.js, поэтому у вас есть доступ к двоичным файлам Node.js.
Официальный образ Node.js называется node.
Далее вы объявляете автора с помощью команды LABEL.
В этом случае мы используем один из наших адресов электронной почты, но вы можете заменить его своей ссылкой, поскольку теперь это ваш файл Dockerfile.
Эта строка не обязательна для создания рабочего образа Docker, но рекомендуется ее включить.
На этом этапе сборка унаследовала состояние node­контейнера, и вы готовы работать над ним.
Затем вы клонируете код приложения с помощью команды RUN.
Указанная команда используется для получения кода приложения, выполняя git внутри контейнера.
В этом случае Git устанавливается внутри базового образа, но нельзя принимать это как должное.
Теперь вы перемещаетесь в новый клонированный каталог с помощью команды WORKDIR. Это не только меняет каталоги в контексте сборки, но и последняя команда WORKDIR определяет, в каком каталоге вы находитесь по умолчанию, когда запускаете свой контейнер из собранного образа.
Затем вы запускаете команду установки менеджера пакетов Node.js (npm). Она установит зависимости для вашего приложения. В этом примере вывод вас не интересует, поэтому вы перенаправляете его в /dev/null.
Поскольку порт 8000 используется приложением, вы применяете команду EXPOSE, чтобы сообщить Docker, что контейнеры из собранного образа должны прослушивать этот порт.
Наконец, вы используете команду CMD, чтобы сообщить Docker, какая команда будет выполнена при запуске контейнера.
Этот простой пример иллюстрирует несколько ключевых особенностей Docker и файлов Dockerfiles.
Dockerfile – это простая последовательность ограниченного набора команд, выполняемых в строгом порядке. Это оказывает воздействие на файлы и метаданные полученного образа.
Здесь команда RUN влияет на файловую систему, проверяя и устанавливая приложения, а команды EXPOSE, CMD и WORKDIR – на метаданные образа. ^5EyjO8d3

Смотрите также >>> Собираем образ Docker ^LZ2tRo5S

И не забыть про -> Ключевые концепции Docker ^dwXHjwem

## Element Links
bq8ngKSD: [[Dockerfile]]

LZ2tRo5S: [[Собираем образ Docker.excalidraw]]

dwXHjwem: [[Ключевые концепции Docker.excalidraw]]

%%
## Drawing
```compressed-json
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
```
%%