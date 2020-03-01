---
tags: Java, Basic, Collections, Queue, PriorityQueue
title: PriorityQueue
---
# PriorityQueue\<E>
Расширяет *AbstractQueue\<E>* и реализует *Queue\<E>*.
Автоматически расширяется размер.
В PriorityQueue добавление/удаление элементов происходит за время O(log(n)). Очередь основана на сбалансированной [бинарной куче](https://habr.com/ru/post/112222/).
Всё сортируется по возрастанию.
:::warning
По факту, либо тип E должен быть Comparable\<E>, либо должен передаваться компаратор. 
В очередь можно положить один элемент без компаратора, но не более.
:::
:::warning
При обходе очереди с помощью итератора элементы будут не упорядочены по приоритету.
:::

## Конструкторы
* `PriorityQueue()` - создаётся внутренний массив размером 11 ячеек
* `PriorityQueue(int initialCapacity)`
* `PriorityQueue(int initialCapacity, Comparator<? super E> comparator)`
* `PriorityQueue(Collection<? extends E> collection)`
* `PriorityQueue(PriorityQueue<? extends E> c)`
* `PriorityQueue(SortedSet<? extends E> c)`

## Методы

Все методы из Queue\<E> и Collection\<E>.