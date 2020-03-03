---
tags: Java, Basic, Collections, List
title: List Interface
---
# List\<E>
Данный интерфейс реализует [*Collection\<E>*](/d12QhvOUQU-Fl5p6sGT8Wg?view), [*Iterable\<E>*](/loXrkVXHRYeD-xMwmxqWRg?view).
В *java.util* есть частично реализованный список *AbstractList*.

## Методы
Все методы из [*Collection\<E>*](/d12QhvOUQU-Fl5p6sGT8Wg?view) плюс

* *Bulk Operations*

| Метод                                                     | Описание                                                      |
| --------------------------------------------------------- | ------------------------------------------------------------- |
| `boolean addAll(int index, Collection<? extends E> coll)` | Вставляет все элементы коллекции начиная с указанного индекса |
| `void replaceAll(UnaryOperator<E> operator)`              | Работает по принципу *map* в Stream API                       |

* *Sorting*

| Метод                                                     | Описание                                                      |
| --------------------------------------------------------- | ------------------------------------------------------------- |
| `void sort(Comparator<? super E> c)` | Сортирует лист |

* *Positional Access Operations*

Могут генерировать *IndexOutOfBoundsException*.
| Метод                            | Описание                                                                                                                   |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `E get(int index)`               | Возвращает элемент листа по индексу.                                                                                       |
| `E set(int index, E element)`    | Устанавливает значение элемента равным новому значению. Возвращает старое значение.                                        |
| `void add(int index, E element)` | Добавляет элемент по индексу сдвигая все остальные.                                                                        |
| `E remove(int index)`            | Удаляет элемент по индексу сдвигая остальные влево (важно помнить, что в Collection\<E> есть метод remove(Object element)) |
| `int indexOf(Object o)`          | Возвращает индекс элемента, иначе -1                                                                                       |
| `int lastIndexOf(Object o)`      | Возвращает индекс элемента с конца листа, иначе -1                                                                         |

* [*ListIterator*](/loXrkVXHRYeD-xMwmxqWRg)

| Метод                                     | Описание                                                 |
| ----------------------------------------- | -------------------------------------------------------- |
| `ListIterator<E> listIterator()`          | Возвращает ListIterator\<E> начиная с 0 индекса          |
| `ListIterator<E> listIterator(int index)` | Возвращает ListIterator\<E> начиная с указанного индекса |

* Другие методы

| Метод                                         | Описание                       |
| --------------------------------------------- | ------------------------------ |
| `List<E> subList(int fromIndex, int toIndex)` | Возвращает представление указанного подсписка (изменения в подсписке влияют на родителя) |
| `Spliterator<E> spliterator()`                                              |                  Возвращает сплитератор со свойством ORDERED              |


## Реализации
* [ArrayList](/DpaTujW8Q3qAoJ4OEWewBg)
* [LinkedList](/ydKATRG5Rn-DRMpocZEdkg)
* [Stack](/zqhsf2NzSQOTtJ4OxKH4Eg)
* [Vector](/tsVthe2uQV-ZP-0oSnhtUg)

==По факту интерес представляет только *ArrayList*, так как *Stack* и *Vector* были до Java 1.2 и у них почти все методы синхронизированы, а *LinkedList* почти во всём проигрывает по скорости *ArrayList*'у.==