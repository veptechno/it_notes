---
tags: Java, Basic, java.util, Date
title: Date Class
---
# Класс Date

Является частично устаревшим классом. Рекомендуется прочитать то, как работать с [датами](/UhUhjK-lT1iYnl6Zb1WJ9A).

Реализует интерфейс *Comparable*.

Не является immutable.

## Конструкторы

* `Date()` - инициализация с текущей датой;
* `Date(long ms)` - количество миллисекунд с 1 января 1970 года.

## Методы

Методов очень мало. По факту это просто хранение количество миллисекунд. 

* `long getTime()`
* `void setTime(long time)`
* `String toString()` - возвращает результат в виде по умолчанию (Wed Mar 04 22:38:12 MSK 2020)
* `boolean after(Date date)` - *true* если вызывающий объект содержит более позднюю дату
* `boolean before(Date date)` - по аналогии