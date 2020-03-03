---
tags: Java, Basic, Collections, Collection, Bulk
title: Collection Interface
---
# Интерфейс Collection\<E>
Является частью [Collections Framework](/sriRjK5tQHG3qlMBndTUkQ).
Все коллекции реализуют этот интерфейс. К коллекциям относятся [List](/D14lbmObQh6VoCf9ShVBrQ), [Queue](/QkE8wOPNTXOjCpQJ34CreA), [Set](/-uew1P9dTNCudmZx6Rax7w). 
[Map](/CGxPIhaCQCyDZKV4DY59fA) к коллекциям не относятся.
Коллекция наследуюется от [`Iterable<E>`](/loXrkVXHRYeD-xMwmxqWRg)).
Есть частично реализованная коллекция в классе *AbstractCollection*.

:::info
Интерфейс содержит Bulk Operations (пакетные операции). 
В БД под этим понимаются команды работающие не с отдельными строками, а делает всё пакетом. 
В Collection\<E> под этими операциями понимаются *containsAll*, *addAll*, *removeAll*, *retainAll*
:::

В интерфейсе содержится не так много методов.

| Метод                                                  | Описание                                                                                                |
| ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| `public int size()`                                    | Возвращает размер коллекции. Если элементов больше Integer.MAX_VALUE, то возвращается Integer.MAX_VALUE |
| `public boolean isEmpty()`                             | *true* если коллекция пуста                                                                             |
| `public boolean contains(Object o)`                    | Принимает Object, не обобщённый тип.                                                                    |
| `public Object[] toArray()`                            | Возвращает массив объектов                                                                              |
| `public <T> T[] toArray(T[] a)`                        | Передаваемый массив нужен для определения типа массива                                                  |
| `public boolean add(E e)`                              | Добавляет элемент в коллекцию. Возвращает *true* если коллекция изменилась.                             |
| `public boolean remove(Object obj)`                    | Удаляет один подходящий элемент. *true* если коллекция изменилась                                       |
| `public boolean containsAll(Collection<?> c)`          | *true* если все элементы из c входят в текущую коллекцию                                                |
| `public boolean addAll(Collection<? extends E> c)`     | Добавляет элементы из c в ткущую коллекцию                                                              |
| `public boolean removeAll(Collection<?> c)`            | Удаляет все элементы из текущей коллекции, которые содержаться в c.                                     |
| `public boolean retainAll(Collection<?> c)`            | Оставляет только те элементы, которые есть в c.                                                         |
| `public void clear()`                                  | Очищает коллекцию                                                                                       |
| `public boolean removeIf(Predicate<? super E> filter)` | Удаляет все элементы проходящие filter. С Java 8                                                        |
| `public Stream<E> stream()`                            | Возвращает Stream по коллекции                                                                          |
| `Stream<E> parallelStream()`                           | Возвращает параллельный Stream по коллекции                                                             |
