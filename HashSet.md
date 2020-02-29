---
tags: Java, Basic, Collections, Set, HashSet
title: HashSet
---
# HashSet\<E>
Расширяет *AbstractSet\<E>* и реализует *Set\<E>*.
Построен на хэш таблице. Внутри себя использует HashMap\<E, Object>.

## Конструкторы
* `HashSet()` - по умолчанию размер 16
* `HashSet(int capacity)`
* `HashSet(int capacity, float loadFactor)` - loadFactor от 0.0 до 1.0. По умолчанию 0.75.
* `HashSet(Collection<? extends E> collection)`

## Методы

Все методы из Collection\<E>.
