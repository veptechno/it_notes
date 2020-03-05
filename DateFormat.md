---
tags: Java, Basic, java.text, Date, DateFormat, SimpleDateFormat
title: DateFormat and SimpleDateFormat
---
# Классы DateFormat and SimpleDateFormat

Для форматирования *[Date](/xZZuD5L1TI-9W6q_MgKqLA) к строке используется метод `format(Date)`.

Для парсинга используется метод `parse(Date)`.

## DateFormat

Является абстрактным классом, но содержит несколько статических методов возвращающих реализации *DateFormat*.

* `getDateTimeInstance()`
* `getTimeInstance()`
* `getDateInstance()`

Также эти методы принимают константы стиля вывода *FULL*, *LONG*, *MEDIUM*, *SHORT* и *DEFAULT* (=*MEDIUM*). А также принимают *[Locale](/HZ3ofsHxR2y8PEnAiAqKVw)*.

```java=
DateFormat dateFormat = DateFormat.getDateInstance(DateFormat.FULL);
System.out.println(dateFormat.format(new Date())); 
//Thursday, March 5, 2020
```

## SimpleDateFormat

Данный класс позволяет создавать шаблоны для форматирования и парсинга дат.

### Конструкторы
* SimpleDateFormat()
* SimpleDateFormat(String pattern)
* SimpleDateFormat(String pattern, Locale locale)

[Синтаксис паттерна](http://divancoder.ru/2017/12/simpledateformat/).

**Примеры паттернов**
* "yyyy.MM.dd G 'at' HH:mm:ss z"
* "EEE, MMM d, ''yy"
* "h:mm a"
* "hh 'o''clock' a, zzzz"
* "K:mm a, z"
* "yyyyy.MMMMM.dd GGG hh:mm aaa"
* "EEE, d MMM yyyy HH:mm:ss Z"
* "yyMMddHHmmssZ"
* "yyyy-MM-dd'T'HH:mm:ss.SSSZ"
* "YYYY-'W'ww-u"
