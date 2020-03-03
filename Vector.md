---
tags: Java, Basic, Collections, List, Vector
title: Vector
---
# Vector\<E>
Расширяет *AbstractList\<E>* и реализует [*List\<E>*](/D14lbmObQh6VoCf9ShVBrQ).
:::warning
Считается устрашевшим классом после ввода Collections Framework (Java 1.2).
Все методы синхронизированы и есть ряд унаследованных методов не имеющих особого смысла.
:::

## Конструкторы
* `Vector()` - создаётся внутренний массив размером с 10 элементов
* `Vector(int initialCapacity)`
* `Vector(int initialCapacity, int increment)` - increment показывает насколько будет увеличиваться массив. По умолчанию увеличивается в 2 раза.
* `Vector(Collection<? extends E> collection)`

