---
title: Enum
tags: Java, Basic, Enum
---
# Перечисления

```java=
enum Apple { 
    Jonathan, GoldenDel, RedDel, Winesap, Cortland
}
```

Перечисления можно использовать в switch. Причём указывать тип перечисления не надо. То есть вместо `Apple.Jonathan` просто пишется `Jonathan`.
```java=
switch (ар) { 
    case Jonathan: 11 ... 
    case Winesap : / / ... 
```

## Методы

```java=
public static тип_перечисления [] values()
public static тип_перечисления valueOf(String строка)
public final int ordinal() // порядковый номер в списке констант
public final int compareTo(тип_перечисления e) // сравнивает порядковые номера
public boolean equals(object a)
```