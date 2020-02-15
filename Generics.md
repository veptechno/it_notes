---
title: Generics
tags: Java, Basic, Generic
---
# Обобщения

[Видео с ютуба](https://youtu.be/mNyQYTp-Njw)

Компилятор удаляет все сведения о типах во время компиляции (это процесс называется стиранием). 
Вместо класса обобщённым может быть интерфейс.

1. Нельзя создавать массивы и объекты используя обобщённый тип (`new T()`).
2. Нельзя создавать массив из обощённый типов (`new Gen<Integer>[10];`) из-за Heap pollution. **Однако можно использовать vararg.**
3. Нельзя создать обощённое исключение (сотрётся информация для try-catch)
4. Нельзя параметризовать Enum
5. Нельзя параметризовывать анонимные классы

```java=
class Gen<T> {
    T ob;

    Gen(T o) {
        ob = o;
    }

    T getOb() {
        return ob;
    }

    void showType() {
        System.out.println(ob.getClass().getName());
    }
    
    //Использовать Т в статических методах нельзя (нужно создавать для них отдельный тип)
}
```

По умолчанию `T extends Object`. И `T` имеет только методы от `Object`.

## Ограниченные типы

```java=
<T extends super_class> //Ограничение сверху
<T extends super_class & interface>
```

## Wildcard (?)

Если в методе нужно принять generic с неизвестным типом, то можно использовать ?. Его также можно ограничивать (extends (*включает суперкласс*) и super (*не включает сам подкласс*)). Однако он уже СРАЗУ ограничен тем, чем ограничен тип в объявлении класса.

```java=
void sameAvg(Stats<?> ob) {

}
```

 ## Обобщённые методы и конструкторы
 
```java=
[static] <T extends Comparable<T>, V extends T> boolean name(T x, V[] y) { /*...*/ }

//Вызов
name(2, new int[] {1, 2, 3});

//Можно указать явно типы, но это нужно очень редко
class.<type, type>name(...);
```

## Raw type (сырые типы)

Это обощённый класс без указания типа. При указании сырого типа отключается проверка на generic во всем классе!

## instanceof
```java=
ob instanceof Gen<?> //можно
ob instanceof Gen //?
ob instanceof Gen<Integer> //нельзя
```

## Type Erasure (стирание)

До стирания
```java=
class Holder<T> {
    private T value;
    
    public Holder(T t) {
        this.value = t;
    }
    
    public T get() {
        return value;
    }
}

//Использование
Holder<Integer> holder = new Holder<>(10);
Integer integer = holder.get();
```

После стирания
```java=
class Holder {
    private Object value;
    
    public Holder(Object t) {
        this.value = t;
    }
    
    public Object get() {
        return value;
    }
}

//Использование
Holder holder = new Holder(10);
Integer integer = (Integer) holder.get();
```

**Если у дженерика есть границы то он стирается в верхнюю границу (extends).**

При стирании могут создаваться bridge методы [видео с ютуба](https://youtu.be/mNyQYTp-Njw?t=393).


## Heap pollution

[Видео с ютуба](https://youtu.be/mNyQYTp-Njw?t=745)

Это ситуация, когда по ссылке одного параметризованного типа хранится другой параметризованный тип (`List<String> = List<Integer>`). Дженерики были разработаны так, чтобы избежать её.

Но такая ситуация возможна с массивами (`Number[] numbers = new Integer[10]`). Поэтому нельзя создавать массивы дженериков.


## extends vs super (PECS)

Producer-extends, consumer-super.
Поставщик-extends, поглотитель-super.

Если лист параметризован `? extends class`, то мы можем оттуда только доставать. Если `? super class` то мы можем туда класть всё, что class и всё что наследуется.