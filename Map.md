---
tags: Java, Basic, Collections, Map, SortedMap, NavigableMap
title: Map
---
# Интерфейсы отображений

## Map\<K, V>
### Методы
**++Query Operations++**
| Метод                                 | Комментарии                                                                                                |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| `int size()`                          |                                                                                                         |
| `boolean isEmpty()`                   |                                                                                                         |
| `boolean containsKey(Object key)`     |                                                                                                         |
| `boolean containsValue(Object value)` |                                                                                                         |
| `V get(Object key)`                   | Возвращает значение по ключу или *null* если его нет                                                    |
| `V put(K key, V value)`               | Если значение уже лежало в коллекции, то оно заменяется. Возвращает предыдущее значение, которое лежало |
| `V remove(Object key)`                | Удаляет элемент из коллекции. Возвращает предыдущее значение, которое лежало                            |

**++Bulk Operations++**

| Метод                                          | Комментарии |
| ---------------------------------------------- | -------- |
| `void putAll(Map<? extends K, ? extends V> m)` |          |
| `void clear()`                                 |          |

**++Set Operations++**

| Метод                             | Комментарии |
| --------------------------------- | -------- |
| `Set<K> keySet()`                 |          |
| `Collection<V> values()`          |          |
| `Set<Map.Entry<K, V>> entrySet()` |          |

**++Java 8++**

| Метод                                                                                      | Комментарии                                                                                                                                                 |
| ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `V getOrDefault(Object key, V defaultValue)`                                               |                                                                                                                                                             |
| `void forEach(BiConsumer<? super K, ? super V> action)`                                    | Применяет action ко всем элементам. Первое - ключ, второе - значение                                                                                        |
| `void replaceAll(BiFunction<? super K, ? super V, ? extends V> function)`                  | Первое - ключ, второе - значение, третье возвращается в коллекцию                                                                                           |
| `V putIfAbsent(K key, V value)`                                                            | absent - отсутствовать. Кладёт если значения нет                                                                                                            |
| `boolean remove(Object key, Object value)`                                                 | Удаляет, если полностью совпадает. Возращает *true* если удалён                                                                                             |
| `V replace(K key, V value)`                                                                | Заменяет значение, если элемент присутсвует в коллекции, иначе ничего не меняется. Возвращает предыдущее значение если произошла замена                     |
| `boolean replace(K key, V oldValue, V newValue)`                                           | Заменяет значения, если элемент присутствует в коллекции, иначе ничего не меняется. Возвращает *true* если произошла замена                                 |
| `V computeIfAbsent(K key, Function<? super K, ? extends V> mappingFunction)`               | Если ключ отсутствует, то кладётся значение полученное применением mappingFunction к ключу                                                                  |
| `computeIfPresent(K key, BiFunction<? super K, ? super V, ? extends V> remappingFunction)` | Если ключ присутствует, то кладётся значение полученное применением mappingFunction к ключу и значению. Если функция возвращает null, то значение удаляется |
| `V compute(K key, BiFunction<? super K, ? super V, ? extends V> remappingFunction)`        | Вставляет значение полученное применением функции к старому значению (если нет, то null) и ключу                                                            |
| `V merge(K key, V value, BiFunction<? super V, ? super V, ? extends V> remappingFunction)` | Если ключ отсутствует, то вводится новая пара key-value, иначе значение заменяется на результат *remappingFunction*                                         |

### Map.Entry
Представляет из себя пару "ключ-значение". Имеет связь с Map (то есть можно в паре изменить value и оно поменяется в отображении).

### Реализации Map
* EnumMap
* HashMap
* WeakHashMap
* LinkedHashMap
* IdentityHashMap
* TreeMap

## SortedMap\<K, V>
Расширяет *Map\<K, V>*. 
Позволяет упорядочивать ключи по Comparator\<K> или по натуральному порядку.
### Методы

| Метод                                       | Комментарии |
| ------------------------------------------- | ----------- |
| `Comparator<? super K> comparator()`        |    Возвращает компаратор используемый в map         |
| `SortedMap<K,V> subMap(K fromKey, K toKey)` |             |
| `SortedMap<K,V> headMap(K toKey)`           |    Подмапа не включая последнего элемента         |
| `SortedMap<K,V> tailMap(K fromKey)`         |             |
| `K firstKey()`                              | Ключ с наименьшим значением           |
| `K lastKey()`                               |    Ключ с наибольшим значением         |
| `Set<K> keySet()`                           |    Множество ключей. Итератор будет обходить по возрастанию         |
| `Collection<V> values()`                    |    Коллекция значений         |
| `Set<Map.Entry<K, V>> entrySet()`           |       Множество пар. Итератор будет обходить по возрастанию      |

## NavigableMap\<K, V>
Расширяет *SortedMap\<K, V>*. 
Позволяет извлекать ключи максимально близкие к какому то значению.
### Методы

| Метод                                | Комментарии                                                 |
| ------------------------------------ | ----------------------------------------------------------- |
| `Map.Entry<K,V> lowerEntry(K key)`   | Entry с ключём строго меньше переданного, иначе *null*      |
| `K lowerKey(K key)`                  |                                                             |
| `Map.Entry<K,V> floorEntry(K key)`   | Entry с ключём меньшим или равным переданному, иначе *null* |
| `K floorKey(K key)`                  |                                                             |
| `Map.Entry<K,V> higherEntry(K key)`  | Entry с ключём строго больше переданного, иначе *null*      |
| `K higherKey(K key)`                 |                                                             |
| `Map.Entry<K,V> ceilingEntry(K key)` | Entry с ключём большим или равным переданному, иначе *null* |
| `K ceilingKey(K key)`                |                                                             |
| `Map.Entry<K,V> firstEntry()`        | Entry с наименьшим ключем                                   |
| `Map.Entry<K,V> lastEntry()`         | Entry с наибольшим ключем                                   |
| `Map.Entry<K,V> pollFirstEntry()`    | Возвращает и удаляет                                        |
| `Map.Entry<K,V> pollLastEntry()`     | Возвращает и удаляет                                        |
| `NavigableMap<K,V> descendingMap()`  |                                                             |
| `NavigableSet<K> navigableKeySet()`  |                                                             |