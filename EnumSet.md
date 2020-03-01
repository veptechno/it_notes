---
tags: Java, Basic, Collections, Set, EnumSet
title: EnumSet
---
# EnumSet\<E extends Enum\<E>>
Расширяет *AbstractSet\<E>* и реализует *Set\<E>*.
Если элементов в Enum меньше или равно 64, то используется *RegularEnumSet*, иначе *JumboEnumSet*. Нужно для оптимизации хранения по ключу.

## Конструкторы
Конструкторов нет, но есть статические методы для создания множеств
* `EnumSet<E> allOf(Class<E> elementType)` - множество содержащее все элементы из Enum
* Другие методы создающие множества из переданных элементов
