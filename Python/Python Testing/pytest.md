---
title: pytest
date of creation: 2025-06-02T18:09:00
tags:
  - Test
  - Tests
  - Developing
  - Framework
  - Framework/Python
  - Python/Framework
  - Python
  - Python/Tests
  - Python/OOP/Tests
read status: true
completion status: true
aliases:
  - python pytest
---
# pytest
---

Фреймворк `pytest` помогает легко писать небольшие тесты и масштабируется для поддержки сложного функционального тестирования приложений и библиотек.

Вот пример простого теста:
```python
def inc(x):
	return x + 1


def test_answer():
	assert inc(3) == 5
```

Чтобы запустить его, выполните:
```bash
$ pytest
=========================== test session starts===========================
platform linux -- Python 3.x.y, pytest-5.x.y, py-1.x.y, pluggy-0.x.y
cachedir: $PYTHON_PREFIX/.pytest_cache
rootdir: $REGENDOC_TMPDIR
collected 1 item

test_sample.py F                                                     [100%]

================================= FAILURES ===============================
_______________________________ test_answer ______________________________

    def test_answer():
>       assert inc(3) == 5
E       assert 4 == 5
E        +  where 4 = inc(3)

test_sample.py:6: AssertionError
============================ 1 failed in 0.12s ===========================
```

Поскольку `pytest` детально анализирует результат выполнения оператора `assert`, можно использовать только простые и понятные конструкции. Больше примеров можно найти тут [Установка и начало работы](https://pytest-docs-ru.readthedocs.io/ru/latest/getting-started.html#getstarted).


## Возможности `pytest`

- подробный разбор упавших проверок [assert](https://pytest-docs-ru.readthedocs.io/ru/latest/assert.html#id1) (не нужно помнить имена `self.assert*`);
    
- [автообнаружение](https://pytest-docs-ru.readthedocs.io/ru/latest/goodpractices.html#test-discovery) тестовых модулей и функций;
    
- использование [модульных фикстур](https://pytest-docs-ru.readthedocs.io/ru/latest/fixture.html#fixture) для управления небольшими или параметризованными тестовыми ресурсами см. также [[pytest-фикстуры]];
    
- запуск тестовых наборов, написанных с использованием [unittest](https://pytest-docs-ru.readthedocs.io/ru/latest/unittest.html#unittest) (включая пробные) и [nose](https://pytest-docs-ru.readthedocs.io/ru/latest/nose.html#noseintegration);
    
- совместим с Python 3.5+ и PyPy 3;
    
- у `pytest` есть большой набор (315 + [внешних плагинов](http://plugincompat.herokuapp.com/)) и процветающее сообщество.


## Документация
---

Полная документация: [Оглавление](https://pytest-docs-ru.readthedocs.io/ru/latest/contents.html#toc).


## Баги/Запросы на улучшение
---

Пожалуйста, используйте [GitHub issue tracker](https://github.com/pytest-dev/pytest/issues) ,чтобы сообщить о багах или внести предложения об улучшении `pytest`.

## Журнал изменений (`changelog`)
---

Информация об исправленных багах и улучшениях: [журнал изменений](https://pytest-docs-ru.readthedocs.io/ru/latest/changelog.html#changelog).


## Поддержка `pytest`
---

[Open Collective](https://opencollective.com/) - это онлайн-платформа для финансирования проектов с открытым кодом. Она предоставляет прозрачные инструменты для сбора средств и обмена финансами.

Это платформа выбора для частных лиц и компаний, которые хотят сделать одноразовые или ежемесячные пожертвования непосредственно на проект.

Узнайте больше на [pytest collective](https://opencollective.com/pytest).

## `pytest` для предприятий
---

Доступно в рамках подписки на [Tidelift](https://tidelift.com/).

Разработчики `pytest` и тысяч других пакетов работают с `Tidelift`, чтобы обеспечить коммерческую поддержку и обслуживание зависимостей с открытым исходным кодом, которые вы используете для создания своих приложений. Экономьте время, снижайте риск и улучшайте работоспособность кода, одновременно оплачивая разработчикам именно те зависимости, которые вы используете.

[Подробнее](https://tidelift.com/subscription/pkg/pypi-pytest?utm_source=pypi-pytest&utm_medium=referral&utm_campaign=enterprise&utm_term=repo)


### Безопасность
---

Безопасность никогда не была слабым местом `pytest`, однако вы можете использовать [Tidelift security contact](https://tidelift.com/security), чтобы сообщить о найденной уязвимости в сфере безопасности. `Tidelift` будет координировать обнаружение и исправление таких багов.


## Лицензия
---

Copyright Holger Krekel and others, 2004-2020.

Распространяемый в соответствии с условиями лицензии [MIT](https://github.com/pytest-dev/pytest/blob/master/LICENSE) , `pytest` является бесплатным программным обеспечением с открытым исходным кодом.
