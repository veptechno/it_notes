---
tags: Java, Basic, Collections, Map, HashMap, IdentityHashMap
title: IdentityHashMap
---
# IdentityHashMap\<K, V>
IdentityHashMap - это структура данных, реализующая интерфейс Map, но использующая сравнение ссылок вместо метода equals() при сравнении ключей (значений). Другими словами, в IdentityHashMap два ключа k1 и k2 будут рассматриваться равными, если выполняется условие k1 == k2.

## Конструкторы
* `IdentityHashMap()`
* `IdentityHashMap(int expectedMaxSize)`
* `IdentityHashMap(Map<? extends K, ? extends V> map)`