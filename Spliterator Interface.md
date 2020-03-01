---
tags: Java, Basic, Spliterator, Iterator
title: Interfaces Spliterator
---
# Spliterator\<T>
Это итератор-разделитель введённый в Java 8.
Каждый класс реализующий [Iterable\<T>](https://hackmd.io/loXrkVXHRYeD-xMwmxqWRg?view) может вернуть Spliterator\<T>.

## Характеристики
У сплитератора есть характеристики, такие как
* ORDERED
* DISTINCT
* SORTED
* SIZED 
* NONNULL
* IMMUTABLE 
* CONCURRENT 
* SUBSIZED

Они могут использовать для контроля и оптимизации вычислений

## Методы

| Метод                                               | Описание                                                                                                                   |
| --------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `boolean tryAdvance(Consumer<? super T> action)`    | Выполняет для следующего элемента *action*. Возвращает false если следующего элемента нет                                  |
| `void forEachRemaining(Consumer<? super T> action)` | Выполняет для всех оставшихся элементов *action*                                                                           |
| `Spliterator<T> trySplit()`                         | Разделяет оставшиеся элементы по двум сплитераторам, возвращает новый сплитератор или если невозможно разделение то *null* |
| `long estimateSize()`                               | Оценивает оставшееся количество элементов, если невозможно то *Long.MAX_VALUE*                                             |
| `long getExactSizeIfKnown()`                        | -1 если неизвестно                                                                                                         |

## Работа с примитивами
В Spliterator есть методы для работы с примитивами.