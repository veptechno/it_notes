---
tags: Java, Basic, Collections, Deque
title: Deque Interface
---
# Deque\<E>
Данный интерфейс наследуется от [*Queue\<E>*](/QkE8wOPNTXOjCpQJ34CreA).
Работает по принципу FIFO (первым вошёл, первым вышел) или LIFO (последним вошёл, первым вышел).

## Методы

:::info
Перевод методов
**Добавление**
* add, addLast - добавить (в конец). **Кидает исключение**
* addFirst, push - добавить (в начало). **Кидает исключение**
* offer, offerLast - предложить (добавить в конец без исключения если нет места)
* offerFirst - предложить (добавить в начало без исключения если нет места)

**Удаление**
* remove, removeFirst, pop - удалить из головы и вернуть. **Кидает исключение**
* removeLast - удаляет из конца очереди. **Кидает исключение**
* poll, pollFirst - опросить (удаляет и возвращает элемент из головы, если его нет то возвращается null)
* pollLast - удаляет и возвращает элемент из хвоста, если коллекция пуста, то возвращает null

**Опрос**
* element, getFirst - посмотреть на элемент в голове. **Кидает исключение**
* getLast - посмотреть на элемент в хвосте. **Кидает исключение**
* peek, peekFirst - заглянуть, взглянуть на элемент в голове. Если элемента нет, то возвращает *null*
* peekLast - взглянуть на элемент в хвосте. Если элементов нет, то возвращает *null*
:::

Все методы из [*Collection\<E>*](/d12QhvOUQU-Fl5p6sGT8Wg?view) плюс

| Метод                | Описание                                                                                                                     |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `boolean offer(E e)` | Вставляет элемент в конец очереди. Если не удалось, то возвращает *false* (метод  `add(E e)` кидает *IllegalStateException*) |
| `E remove()`         | Возвращает элемент из головы очереди, если его нет, то кидает *NoSuchElementException*                                       |
| `E poll()`           | Возвращает элемент из головы очереди, если его нет, то *null*                                                                |
| `E element()`        | Не удаляя элемент возвращает элемент из головы. Если очередь пуста то кидается исключение                                    |
| `E peek()`           | Не удаляя элемент возвращает элемент из головы. Если очередь пуста то *null*                                                 |

## Реализации

* [LinkedList](/ydKATRG5Rn-DRMpocZEdkg)
* [ArrayDeque](/G18Hk4BNTvij1Lf37kw23Q)