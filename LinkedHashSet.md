---
tags: Java, Basic, Collections, Set, LinkedHashSet
title: LinkedHashSet
---
# LinkedHashSet\<E>
Расширяет *HashSet\<E>* и реализует *Set\<E>*.
Хранит указатель на первый элемент и в каждом элементе хранит следующий. Используется для этого *LinkedHashMap\<E>*.

## Конструкторы
* `LinkedHashSet()` - по умолчанию размер 16
* `LinkedHashSet(int capacity)`
* `LinkedHashSet(int capacity, float loadFactor)` - loadFactor от 0.0 до 1.0. По умолчанию 0.75.
* `LinkedHashSet(Collection<? extends E> collection)`

## Методы

Все методы из Collection\<E>.
