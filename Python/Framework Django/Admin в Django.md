---
title: Admin в Django
date of creation: 2025-06-06T23:19:00
tags:
  - Django
  - Framework/Python
  - Python/Framework
  - Developing
  - Backend
  - Python/Backend
read status: false
completion status: true
aliases:
  - Админка в Django
  - Административная панель в Django
---
# Admin в Django
---

Создание раздела администратора, через который пользователи смогут добавлять, изменять и удалять данные — утомительная работа. Она не требует творческого подхода. По этой причине Django полностью автоматизирует создание раздела администратора на основе моделей.

Django разрабатывался с упором на разделение сайта на две части: редактирование контента и просмотр контента. В этом уроке мы разберем работу с Django Admin, который администраторы сайта используют, чтобы добавлять контент на сайт. И он будет отображаться для всех посетителей сайта. Django Admin не предназначен для использования обычными посетителями, это место для управления сайтом.


## Создание суперпользователя
---

Если мы посмотрим на наш главный файл _urls.py_, то увидим, что по умолчанию раздел администратора у нас подключен:

```python
urlpatterns = [
    # ...
    path("admin/", admin.site.urls),
]
```

Если перейти по данному адресу, откроется страница для входа в раздел администратора:

![](https://cdn2.hexlet.io/derivations/image/original/eyJpZCI6IjJkMTk3YmUyZDBmOTUxNGFmN2U0ODk0Yzk5ZDMzZTRjLnBuZyIsInN0b3JhZ2UiOiJjYWNoZSJ9?signature=2bb08d74e603bc7355161c43cf933eb1948113b9217107a3f370b9aa1f1ec463)

Чтобы войти в раздел администратора, нам необходимо иметь учетную запись пользователя со статусом Staff. Мы можем создать учетную запись _superuser_, у которой есть полный доступ к сайту и все необходимые разрешения. Для этого выполним следующую команду и заполним информацию о себе:

```bash
python manage.py createsuperuser

Username: admin
Email address: admin@example.com
Password: **********
Password (again): **********
Superuser created successfully.
```

Теперь мы можем зайти в админку под созданной учетной записью:

![](https://cdn2.hexlet.io/derivations/image/original/eyJpZCI6IjVhZDk4MmU3MjlkZGVjODg2NjlmYmRjNGI3MGFjZGVjLnBuZyIsInN0b3JhZ2UiOiJjYWNoZSJ9?signature=8ac7204a83cb9864125fdfe93e27fd4ec37614468cf45b1c02818b485c768463)

В этом разделе мы видим все наши модели, которые сгруппированы по установленному приложению. Пока мы видим несколько типов редактируемого контента: группы и пользователи. Они предоставляются `django.contrib.auth` платформой аутентификации, которая поставляется Django.


## Регистрация моделей
---

Чтобы добавить в админку наши модели для редактирования, нам нужно отредактировать файл _admin.py_. Он расположен внутри приложения:

```shell
from django.contrib import admin
from .models import Article

admin.site.register(Article)
```

Мы зарегистрировали нашу модель в админке, и при обновлении страницы у нас появится новый раздел:

![](https://cdn2.hexlet.io/derivations/image/original/eyJpZCI6IjBiMmU5N2ExMzhlM2IyNDgxNTliMDk1NmMwMDViYTU5LnBuZyIsInN0b3JhZ2UiOiJjYWNoZSJ9?signature=885b42c764e47b84a1f5e0bfc88f06a2a3664d5c0b4b028d536dbd04006ddf3d)

Теперь через новый раздел мы можем управлять данными в модели: добавлять, редактировать и удалять. Но если откроем список статей, увидим следующие названия:

![](https://cdn2.hexlet.io/derivations/image/original/eyJpZCI6IjlkMWExZGU1NDk4ODhkMWJhMzQyNTc0NzIzYzcyZThlLnBuZyIsInN0b3JhZ2UiOiJjYWNoZSJ9?signature=ff575b8bbd6cc84ae5a8dd00c8de3e2301d2b2607e6aa8e4718528f645f8da9f)

Такие названия задаются методом `__str__`, который по умолчанию состоит из названия класса и _id_ записи в базе данных. Чтобы привести данный список к более читаемому и понятному виду, нам нужно в классе модели переопределить данный метод:

```python
class Article(models.Model):
    name = models.CharField(max_length=200)
    body = models.TextField()
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)

    def __str__(self):
        return self.name
```

В данном примере мы указываем, что в качестве названия объекта нужно возвращать значение поля `name`. Так в качестве названия мы можем использовать любые поля, их комбинации или брать поля из связанных моделей. Теперь наш список будет выглядеть более читаемым для человека:

![](https://cdn2.hexlet.io/derivations/image/original/eyJpZCI6Ijg2MjRkNGY5NGVhNWQ2ZmIwNjQ0YmEwZmEzMzJiYTYyLnBuZyIsInN0b3JhZ2UiOiJjYWNoZSJ9?signature=6e3611f463fe64d689c04c3d1e7dfc9b70a4c0d9b0d121066f563a474be64bdb)


## Настройка отображения
---

Возможности Django Admin на этом не заканчиваются. Например, при помощи дополнительных параметров можно производить фильтрации списков по параметрам, ограничивать список выдачи по авторам, организовывать поиск.

Попробуем добавить поисковую форму, чтобы можно было найти нужную статью по названию. Для этого изменим содержание файла _admin.py_:

```python
from django.contrib import admin

from .models import Article


class ArticleAdmin(admin.ModelAdmin):
    search_fields = ["name", "body"]


admin.site.register(Article, ArticleAdmin)
```

Мы добавили класс, который описывает дополнительные свойства для отображения и работы с нашей моделью в разделе администратора. В данном случае мы указали поле `search_fields`, в которое передали списком названия полей. По ним будет осуществляться поиск. Всю остальную работу по добавлению поля для ввода поискового запроса, контекстному поиску по выбранным полям на себя берет Django Admin:

![](https://cdn2.hexlet.io/derivations/image/original/eyJpZCI6IjUzYzUxZjJjYjNhMTBjMjU5NDY3MjcyMDZkNTgzOGU0LnBuZyIsInN0b3JhZ2UiOiJjYWNoZSJ9?signature=3f79ab31190ef43fd6375c2263d1782a2c59153f628c787f3bd8f385aa87a707)

Мы можем улучшить читаемость нашего кода, если воспользуемся декоратором `@admin.register()`. Он позволяет связать модель с классом и провести регистрацию модели в разделе администратора:

```python
from django.contrib import admin

from .models import Article


@admin.register(Article)
class ArticleAdmin(admin.ModelAdmin):
    search_fields = ["name", "body"]
```

Еще добавим отображение в списке статей даты публикации и фильтрацию по данному полю:

```python
from django.contrib import admin
from django.contrib.admin import DateFieldListFilter

from .models import Article


@admin.register(Article)
class ArticleAdmin(admin.ModelAdmin):
    list_display = (
        "name",
        "created_at",
    )  # Перечисляем поля, отображаемые в таблице списка статей
    search_fields = ["name", "body"]
    list_filter = (
        ("created_at", DateFieldListFilter),
    )  # Перечисляем поля для фильтрации
```

![](https://cdn2.hexlet.io/derivations/image/original/eyJpZCI6IjQyMGIyMThhM2EwMjhmNDQxZDdkNDYyN2I3ZmY3NmUwLnBuZyIsInN0b3JhZ2UiOiJjYWNoZSJ9?signature=f89d74e247478535e0b6f2d86d074f9389dd7d00aa7328e395c92cef65ced986)
