---
title: Enum
tags: Java, Basic, Enum
---
# Перечисления

```java=
enum Apple { 
    JONATHAN, GOLDENDEL, REDDEL, WINESAP, CORTLAND;
}
```

Перечисления можно использовать в switch. Причём указывать тип перечисления не надо. То есть вместо `Apple.JONATHAN` просто пишется `JONATHAN`.
```java=
switch (ар) { 
    case JONATHAN: 11 ... 
    case WINESAP : / / ... 
```

Перечисления неявно наследуются от *Enum<>*, поэтому нельзя ещё от чего нибудь унаследовать *enum*. Также нельзя наследоваться от *enum* - он неявно объявляется *final*.

==Нельзя задать конструктор с модификатором *public*.==

## Методы

```java=
public static тип_перечисления [] values()
public static тип_перечисления valueOf(String строка)
public final int ordinal() // порядковый номер в списке констант
public final int compareTo(тип_перечисления e) // сравнивает порядковые номера
public boolean equals(object a)
```

У перечисления можно создавать свои методы, а также переопределять их для конкретных объектов Enum. 

```java=
enum Apple {
    JONATHAN("Jonathan"), GOLDENDEL("GoldenDel"), REDDEL("RedDel"), WINESAP("Winesap") {
        @Override
        public void printName() {
            System.out.printf("My name is %s%n", name);
        }
    }, CORTLAND("Cortland");

    protected String name;

    Apple(String name) {
        this.name = name;
    }
    
    public void printName() {
        System.out.println(name);
    }
}
```

## Порядок инициализации

Объекты класса *enum* создаются все вместе в **момент первого обращения к классу**.
Причём порядок вызовов следующий:

1. Блок инициализации объекта
2. Конструктор объекта
3. ...
4. Статический блок инициализации