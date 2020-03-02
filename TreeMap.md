---
tags: Java, Basic, Collections, Map, SortedMap, NavigableMap, TreeMap
title: TreeMap
---
# TreeMap\<K, V>
Расширяет *AbstractMap\<K, V>* и реализует *NavigableMap\<K, V>*.
Построен на красно-черных деревьях.
## Сложность
:::info
Операции, как добавление, удаление и поиск, занимают O (Log n) время
:::

## Конструкторы
* `TreeMap()` - по умолчанию размер 16
* `TreeMap(Comparator<? super E> comparator)`
* `TreeMap(Map<? extends K, ? extends V> map)`
* `TreeMap(SortedMap<K, ? extends V> map)`

## Методы

Все методы из *NavigableMap\<K, V>*.
