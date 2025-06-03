---
title: DRF view
date of creation: 2025-06-03T19:42:00
tags:
  - DRF
  - Django
  - Backend
  - Framework
  - Python/Framework
  - Python/Backend
  - Web
read status: true
completion status: false
aliases:
---
# DRF view
---

## Представления, основанные на классах
---

DRF предоставляет класс `APIView`, который является подклассом класса Django `View`.

Классы `APIView` отличаются от обычных классов `View` следующим образом:

- Запросы, передаваемые методам обработчика, будут экземплярами `Request` DRF, а не экземплярами `HttpRequest` Django.
    
- Методы обработчика могут возвращать `Response` DRF, а не `HttpResponse` Django. Представление будет управлять согласованием содержимого и установкой правильного рендерера в ответе.
    
- Любые исключения `APIException` будут перехвачены и переведены в соответствующие ответы.
    
- Входящие запросы будут аутентифицированы, и перед отправкой запроса в метод-обработчик будут выполняться соответствующие проверки разрешений и/или дросселирования.
    

Использование класса `APIView` практически не отличается от использования обычного класса `View`. Как обычно, входящий запрос передается соответствующему методу-обработчику, такому как `.get()` или `.post()`. Кроме того, для класса может быть установлен ряд атрибутов, которые контролируют различные аспекты политики API.

```python
from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework import authentication, permissions
from django.contrib.auth.models import User

class ListUsers(APIView):
    """
    View to list all users in the system.

    * Requires token authentication.
    * Only admin users are able to access this view.
    """
    authentication_classes = [authentication.TokenAuthentication]
    permission_classes = [permissions.IsAdminUser]

    def get(self, request, format=None):
        """
        Return a list of all users.
        """
        usernames = [user.username for user in User.objects.all()]
        return Response(usernames)
```

**Примечание**: Полные методы, атрибуты и отношения между `APIView`, `GenericAPIView`, различными `Mixins` и `Viewsets` DRF могут быть изначально сложными. В дополнение к документации, представленной здесь, ресурс [Classy Django REST Framework](http://www.cdrf.co/) предоставляет просматриваемую ссылку с полными методами и атрибутами для каждого из представлений DRF, основанных на классах.
