---
tags: Java, Basic, Collections, Map, LinkedHashMap
title: LinkedHashMap
---
# LinkedHashMap\<K, V>
Класс LinkedHashMap расширяет [HashMap](https://hackmd.io/C-yEPF-BSzqzNsUAGej_Bg). 
Позволяет с помощью итератора обходить элементы в том порядке, в котором были добавлены элементы или в порядке в котором к ним был осуществлён доступ (последний элемент = последний доступ). Внутри себя реализует двусвязный список.

## Конструкторы
* `LinkedHashMap()` - initialCapacity - 16, loadFactor - 0.75
* `LinkedHashMap(Map<? extends K, ? extends V> m)`
* `LinkedHashMap(int initialCapacity)`
* `LinkedHashMap(int initialCapacity, float loadFactor)` - loadFactor указывает коэффициент заполнения. По умолчанию 0.75 (от 0.0 до 1.0)
* `LinkedHashMap(int initialCapacity, float loadFactor, boolean accessOrder)` - the ordering mode - true for access-order, false for insertion-order 

## Пример
### Создание с обходом в порядке ++добавления++
```java=
LinkedHashMap<String, Integer> map = new LinkedHashMap<>();

        map.put("one", 1);
        map.put("two", 2);
        map.put("three", 3);

        System.out.println(map); // {one=1, two=2, three=3}
```

### Создание с обходом в порядке ++доступа++
```java=
LinkedHashMap<String, Integer> map = new LinkedHashMap<>(16, 0.75f, true);

map.put("one", 1);
map.put("two", 2);
map.put("three", 3);

System.out.println(map); //{one=1, two=2, three=3}

map.get("two");

System.out.println(map); //{one=1, three=3, two=2}
```