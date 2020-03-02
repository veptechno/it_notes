---
tags: Java, Basic, Collections, Map, WeakHashMap
title: WeakHashMap
---
# WeakHashMap\<K, V>
[Про слабые ссылки.](https://hackmd.io/RhERTZ6TTMiul1nbtDknXg)
Класс WeakHashMap является реализацией интерфейса Map, который хранит только слабые ссылки в качестве ключей. Это позвоялет сборщику мусора удалять элемент структуры в том случае, если на ключ элемента типа “ключ – значение” за пределами таблицы никто не ссылается.
Хранит данные используя хеш-таблицу. Каждое значение представляет из себя вложенный класс Entry<K, V> и у него есть ссылка на следующий элемент, если у них совпадают хеш-коды.

## Конструкторы
* `WeakHashMap()`
* `WeakHashMap(Map<? extends K, ? extends V> m)`
* `WeakHashMap(int initialCapacity)`
* `WeakHashMap(int initialCapacity, float loadFactor)` - loadFactor указывает коэффициент заполнения. По умолчанию 0.75 (от 0.0 до 1.0)

## Пример
```java=
WeakHashMap<String, Integer> map = new WeakHashMap<>();

map.put(new String("one"), 1);
map.put(new String("two"), 2);
map.put(new String("three"), 3);

System.out.println(map.size()); // 3
Runtime.getRuntime().gc();
System.out.println(map.size()); // 0
```