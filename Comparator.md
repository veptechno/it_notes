---
tags: Java, Basic, Collections, Comparator
title: Comparator
---
# Интерфейс Comparator\<T>
Располагается в пакете *java.util*, в отличие от *Comparable* который лежит в *java.lang*.

Является ++функциональным интерфейсом++.
```java=
(o1, o2) -> {
    return 0;
}
```

:::success
Правило для определения знака сравнения compare(x, y):
* x < y = compare(x, y) < 0
* x == y = compare(x, y) == 0
* x > y = compare(x, y) > 0
:::

## Методы

| Метод                                                                   | Комментарий                                                                                                        |
| ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| `int compare(T o1, T o2)`                                               |                                                                                                                    |
| `Comparator<T> reversed()`                                              | Возвращает компаратор изменяющий порядок сравнения на обратный                                                     |
| `static <T> Comparator<T> nullsFirst(Comparator<? super T> comparator)` | Рассматривает значения *null* как самые наименьшие                                                                 |
| `static <T> Comparator<T> nullsLast(Comparator<? super T> comparator)`  | Рассматривает значения *null* как самые наименьшие                                                                 |
| `Comparator<T> thenComparing(Comparator<? super T> other)`              | Возвращает компаратор с поведением, что если первый компаратор вернул 0, то идёт проверка с использованием второго |
