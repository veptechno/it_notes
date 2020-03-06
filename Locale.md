---
tags: Java, Basic, java.util, Locale
title: Locale
---
# Класс Locale

Класс хранящий информацию о регионе. Используется для работы в интернациональных средах. Например используется для правильного вывода даты, времени и чисел.

Для наиболее часто употребимых региональных настроек есть заданные константы (*CANADA*, *CHINA*, *ITALY* и т.п. (России нет)).

## Создание

* `Locale(String language)` - language - стандартный код языка (ru)
* `Locale(String language, String country)` - country - стандартный код страны (RU)

```java=
new Locale("ru", "RU");
```

## Методы

* `static void setDefault(Locale default)` - устанавливает дефолтную локаль для машины
* `static Locale getDefault()` - возвращает дефолтную для машины локаль
* `String getDisplayCountry()`
* `String getDisplayLanguage()`
* `String getDisplayName()`