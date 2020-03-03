---
tags: Java, Basic, Collections, List, ArrayList
title: ArrayList
---
# ArrayList\<E>
Расширяет *AbstractList\<E>* и реализует [*List\<E>*](/D14lbmObQh6VoCf9ShVBrQ).

## Особенности
* При заполнении внутреннего массива он изменении *oldCapacity * 3 / 2 + 1*;
* Сам *ArrayList* не уменьшается. Нужно вызывать `trimToSize()`;

## Конструкторы
* `ArrayList()` - создаётся пустой внутренний массив
* `ArrayList(int initialCapacity)`
* `ArrayList(Collection<? extends E> collection)`

## Методы

Все методы из [*List\<E>*](/D14lbmObQh6VoCf9ShVBrQ) и [*Collection\<E>*](/d12QhvOUQU-Fl5p6sGT8Wg?view).

### Управление размерами


| Метод                                  | Описание                                                |
| -------------------------------------- | ------------------------------------------------------- |
| `void trimToSize()`                    | Уменьшает внутренний массив до реальных размеров списка. **ArrayList сам размер не уменьшает** |
| `void ensureCapacity(int minCapacity)` | Увеличивает внутренний массив до minCapacity            |
