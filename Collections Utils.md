---
tags: Java, Basic, Collections, Utils
title: Collections Utils
---
# Collections Utils

В каркасе коллекций есть класс *Collections* содержащий алгоритмы для работы с коллекциями. Содержится в пакете *java.util*.

## Методы
:::warning
Типы generic'ов упрощены для краткости
:::

### Algorithms

| Метод                                                         | Комментарии                                                                                                                                                                                       |
| ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `void sort(List<T> list)`                                     | Вызывает `list.sort(null)`, где *null* это *Comparator*. *T* должен реализовывать *Comparable*                                                                                                    |
| `void sort(List<T> list, Comparator<T> c)`                    | Сортирует *list* с использованием компаратора                                                                                                                                                     |
| `int binarySearch(List<? extends Comparable<T>> list, T key)` | Ищет индекс элемента в **отсортированном** списке. Возвращает индекс элемента если найден, иначе возвращает -(insertion point). insertion point - индекс куда можно было бы вставить этот элемент |
| `int binarySearch(List<T> list, T key, Comparator<T> c)`      | Аналогично предыдущему методу за исключением, что компаратор не natural                                                                                                                           |
| `void reverse(List<?> list)`                                  | Меняет порядок элементов. Работает за линейное время                                                                                                                                              |
| `void shuffle(List<?> list)`                                  | Мешает лист                                                                                                                                                                                       |
| `void swap(List<?> list, int i, int j)`                       | Меняет элементы листа местами. i и j индексы                                                                                                                                                      |
| `void fill(List<T> list, T obj)`                              | Заменяет все элементы листа элементами *obj*                                                                                                                                                      |
| `T min(Collection<T> coll)`                                   | Находит минимум в коллекции. T должен быть *Comparable*                                                                                                                                           |
| `T max(Collection<T> coll)`                                   | Находит максимум в коллекции. T должен быть *Comparable*                                                                                                                                          |
| `T min(Collection<T> coll, Comparator<T> comp)`               | Находит минимум в коллекции                                                                                                                                                                       |
| `T max(Collection<T> coll, Comparator<T> comp)`               | Находит максимум в коллекции                                                                                                                                                                      |
| `boolean replaceAll(List<T> list, T oldVal, T newVal)`        | Заменяет все вхождения элемента *oldVal* на *newVal*                                                                                                                                              |
| `int indexOfSubList(List<?> source, List<?> target)`          |                                                                                                                                                                                                   |

### Unmodifiable Wrappers

Для всех коллекций и map есть метод по типу *unmodifiableCollection*, который возвращает неизменяемую коллекцию.

### Synch Wrappers

Для всех коллекций и map есть метод по типу *synchronizedCollection*, который возвращает синхронизированную коллекцию. (Я так понимаю не из concurrent).

### Dynamically typesafe collection wrappers

В рантайме проверяют, что в коллекцию действительно передаются объекты правильного типа (возможно пережиток прошлого или для динамечского определения типа).

### Empty collections

Для каждого типа коллекции можно получить пустую коллекцию в которую нельзя ничего добавить. *emptyCollection*.

### Singleton collections

Можно создать лист или мапу хранящие только один элемент. Например `singletonList`.

### Другие методы

| Метод                                      | Комментарий                            |
| ------------------------------------------ | -------------------------------------- |
| `int frequency(Collection<?> c, Object o)` | Частота появления элемента в коллекции |
