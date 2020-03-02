---
title: Object
tags: Java, Basic, Object, Classes, Clone
---
# Класс Object
## Методы
* `Object clone()` - клонирует объект. Чтобы не было исключения *CloneNotSupportedException* необходимо имплементировать интерфейс маркер *Cloneable*
* `boolean equals(Object object)`
* `void finalize()` - вызывается перед сборкой мусора
* `final Class<?> getClass()` - возвращает класс объекта во время выполнения
* `int hashCode()`
* `final void notify()` - возобновляет выполнение потока, ожидающего вызывающего объекта
* `final void notifyAll()`
* `final void wait()` - ожидает другого потока исполнения
* `String toString()`

## Equals
*equals* порождает отношение эквивалентности. 
Оно обладает следующими свойствами:
1. ++Рефлексивность++. Должно выполняться `x.equals(x) == true` для `x != null`;
2. ++Симметричность++. Должно выполняться `x.equals(y) == true` тогда и только тогда, когда `y.equals(x) == true` для `x != null && y != null`;
3. ++Транзитивность++. Если `x.equals(y) == true && y.equals(z) == true`, то `x.equals(z) == true` для `x != null && y != null && z != null`.

## Clone
Должен быть имплементирован интерфейс Cloneable.
В Object метод объявлен как protected, но в наследнике его можно расширить до public.
Метод возвращает Object, поэтому его будет необходимо кастовать.

При клонировании конструктор класса не вызывается, вместо него вызывается метод clone.

