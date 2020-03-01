---
tags: Java, Basic, Collections, Set, SortedSet, NavigableSet, TreeSet
title: TreeSet
---
# TreeSet\<E>
Расширяет *AbstractSet\<E>* и реализует *NavigableSet\<E>*.
Построен на красно-черных деревьях. Внутри себя использует HashMap\<E, Object>.
## Сложность
:::info
Операции, как добавление, удаление и поиск, занимают O (Log n) время
:::

## Конструкторы
* `TreeSet()` - по умолчанию размер 16
* `TreeSet(Collection<? extends E> collection)`
* `TreeSet(Comparator<? super E> comparator)`
* `TreeSet(SortedSet<E> set)`

## Методы

Все методы из NavigableSet\<E>.
