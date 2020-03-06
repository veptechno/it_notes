---
tags: Java, Basic, java.util, TimeZone, Dates
title: TimeZone Class
---
# TimeZone

Это абстрактный класс позволяющий с помощью статических методов получить объект инкапсулирующий хранение смещения часового пояса.

Используется вместе с классоми типа [*Calendar*](/UhUhjK-lT1iYnl6Zb1WJ9A).

## Получение

* `getTimeZone(String ID)` - ID это например "Asia/Barnaul". Список можно получить с помощью метода `getAvailableIDs()`.
* `getTimeZone(ZoneId zoneId)` - класс инкапсулирующий зону

# SimpleTimeZone

Класс позволяющий задавать кастомную зону с учётом летнего и зимнего времени.