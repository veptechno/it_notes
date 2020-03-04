---
tags: Java, Basic, Collections, Map, HashMap
title: HashMap
---
# HashMap\<K, V>
Наследуется от *AbstractMap* и реализует *Map*.
Хранит данные используя хеш-таблицу. Каждое значение представляет из себя вложенный класс Node<K, V> и у него есть ссылка на следующий элемент, если у них совпадают хеш-коды.

## Конструкторы
* `HashMap()`
* `HashMap(Map<? extends K, ? extends V> map)`
* `HashMap(int capacity)`
* `HashMap(int capacity, float loadFactor)` - loadFactor указывает коэффициент заполнения. По умолчанию 0.75 (от 0.0 до 1.0)