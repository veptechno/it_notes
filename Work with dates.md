---
tags: Java, Basic, Dates, Date
title: Work with dates
---
# Работа с датами

## Класс [Date](/xZZuD5L1TI-9W6q_MgKqLA)

Класс *Date* инкапсулирует текущую дату и время. Однако на данный момент многие методы являются *deprecated* и вместо него используется *Calendar* и *DateFormat*.

Для этой даты есть даже отдельное название — “Unix-время”.

| Хранение                          | Форматирование                                      | Парсинг                                             |
| --------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| *[Date](/xZZuD5L1TI-9W6q_MgKqLA)* | *[DateFormat](/O-U9N8YQQTaO2MU60rsIfQ?sync=&type=)* | *[DateFormat](/O-U9N8YQQTaO2MU60rsIfQ?sync=&type=)* |

## [Calendar](/EH3POGlpRLiiz3xgQQ2cGw)

Класс введённый в JDK 1.1. Он умеет работать с датами в более удобном формате (в формате отдельных компонент даты). 

| Хранение | Форматирование (через *Date*) | Парсинг (через *Date*) |
| -------- | -------- | -------- |
| *[Calendar](/EH3POGlpRLiiz3xgQQ2cGw)*     | *[DateFormat](/O-U9N8YQQTaO2MU60rsIfQ?sync=&type=)* | *[DateFormat](/O-U9N8YQQTaO2MU60rsIfQ?sync=&type=)* |

Для работы с временными зонами используется [TimeZone Class](/v7q_akKXTo6NFPwTdCC4Ug?sync=&type=).

## JDK 8

В пакете [*java.time*](/Rwk7r-qCT62lpYmHw2ts3g) существует новое API для работы со временем и датой.

| Хранение        | Формат              | Парсинг             |
| --------------- | ------------------- | ------------------- |
| *Instant*       | *DateTimeFormatter* | *DateTimeFormatter* |
| *LocalDate*     |                     |                     |
| *LocalTime*     |                     |                     |
| *LocalDateTime* |                     |                     |
| *ZonedDateTime* |                     |                     |

*Clock* нужен для тестирования разных временных зон и прочего.

## Ссылки

Статьи в общем про работу со временем с хабра ([1](https://habr.com/en/post/274811/), [2](https://habr.com/en/post/274905/))

Хорошая [статья](https://urvanov.ru/2016/06/16/java-8-%d0%b4%d0%b0%d1%82%d0%b0-%d0%b8-%d0%b2%d1%80%d0%b5%d0%bc%d1%8f/).

Задачи на [codewars](https://www.codewars.com/kata/search/java?tags=Dates%2FTime).