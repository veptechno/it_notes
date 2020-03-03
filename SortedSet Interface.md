---
tags: Java, Basic, Collections, Set, SortedSet
title: SortedSet Interface
---
# SortedSet\<E>
Данный интерфейс наследуется от [*Set\<E>*](/-uew1P9dTNCudmZx6Rax7w).
Множество, которое позволяет итерироваться по отсортированному множеству. Множество сортируется по возрастанию.

## Методы
Все методы из Collection плюс


| Метод                                             | Описание                                                |
| ------------------------------------------------- | ------------------------------------------------------- |
| `E first()`                                       | Возвращает наименьший элемент                           |
| `E last()`                                        | Возвращает максимальный элемент                         |
| `SortedSet<E> subSet(E fromElement, E toElement)` | Возвращает SortedSet                                    |
| `SortedSet<E> headSet(E toElement)`               | Возвращает SortedSet (набор в котором все элементы меньше текущего)       |
| `SortedSet<E> tailSet(E fromElement)`             | Возвращает SortedSet (набор в котором все элементы больше или равны текущему)  |
| `Comparator<? super E> comparator()`              | Возвращает компаратор, который используется в множестве |


## Реализации
* java.util.TreeSet
