---
tags: Java, Basic, java.lang, Number, Double, Float, Integer, Long, Byte
title: java.lang
---
# Пакет java.lang

Этот пакет автоматически импортируется.

## Оболочки примитивных типов

### Number 
Абстрактный класс, который наследуют Double, Float, Byte, Short, Integer и Long. Есть методы возвращающие каждый примитив (`byteValue()` или `intValue()`).

### Double и Float 
У них есть конструктор принимающий строку.
Реализуют Comparable<>.

В них определяются следующие константы
* BYTES - размер в байтах типа данных
* MAX_EXPONENT
* MAX_VALUE
* MIN_EXPONENT
* MIN_NORMAL
* MIN_VALUE
* NaN
* POSITIVE_INFINITY
* NEGATIVE_INFINITY

Методы:
* isInfinity
* isNan
* static max 
* static min
* static double parseDouble(string) - парсит по основанию 10
* static Double valueOf(string) - аналогично

### Byte, Short, Int, Long

В java 8 появились статические методы у Int и Long, которые позволяют работать с примитивами как будто они unsigned.
Реализуют Comparable<>.

#### Byte
Методы
* `static compare(byte1, byte2)` - для lambda
* `static byte decode(string)` - принимает строку. Строка может содержать информацию о разрядности (*0x12A*)
* `static Byte valueOf(string[, base])`
* `static byte parseByte(string[, base])` - число должно быть представлена в 10 виде

#### Short
Методы
* Тоже самое, что и в Byte
* `static Short reverseBytes(short)`

#### Integer
Методы
* Тоже самое, что и в Byte
* Методы для печати Integer с разным основанием

### Character
* Не является Number.
* Реализуют Comparable<>.

В них определяются следующие константы
* BYTES - размер в байтах типа данных
* MAX_VALUE
* MIN_VALUE

Методы:
* Character(char)
* char charValue()
* Также есть множество методов для определения принадлежности символов к разным группам и преобразовании их

### Boolean
## Void
## Process
Абстрактный класс инкапсулирующий процесс
## Runtime
Инкапсулирует исполнящую среду JVM.
Можно получить по Runtime.getRuntime().
Есть отдельный Note.

## System
Содержит коллекцию статических методов и полей.
Есть отдельный Note.
## Math
Отдельный Note.