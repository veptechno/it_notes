---
tags: Java, Basic, String, StringBuilder, StringBuffer
title: StringBuilder and StringBuffer
---
# Видоизменяемые строки

* Реализуют интерфейс CharSequence. 
* У них не переопределённы методы equals, это стоит учитывать.
* Внутри состоят из массива символов, размером на 16 больше чем строка (при создании)


## StringBuffer

* Синхронизирован
* При создании резервирует дополнительно 16 символов
* При увеличении строки увеличивает буфер в 2 раза и добавляет 2

### Конструкторы
* `StringBuffer()` - резервирует массив под 16 символов
* `StringBuffer(length)` - буфер явно задаётся
* `StringBuffer(string)` - резервирует string.length() + 16
* `StringBuffer(charSequence)` - аналогично

### Методы
* `length()` - длина реальной строки
* `capacity()` - размер буфера
* `ensureCapacity(min_buffer_size)` - указывается минимальный размер буфера (меньше он не станет)
* `setLength(length)` - устанавливает длину самой строки (если меньше существующей, то символы отбросятся, если больше то вставятся пустые символы)
* `charAt(index)`
* `setCharAt(index, char)`
* `getChars(начало_источника, конец источника(не включая), адресат[], начало адресата)`
* `append()`
* `insert(index, string)` - при вставке расширяет строку
* `reverse()`
* `delete(from, to)`
* `deleteCharAt(index)`
* `replace(startIndex, endIndex, string)`
* `substring()`

## StringBuilder

* Не синхронизирован
* С 5 джавы
* Всё остальное точно также