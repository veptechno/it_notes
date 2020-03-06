---
tags: Java, Basic, Random, java.util
title: Random
---
# Random

В пакете *java.util* представлен класс *Random* для генерации псевдослучайных примитивов.

В методе `random()` класса *java.lang.Math* используется класс *Random*.

```java=
Random random = new Random(System.currentTimeMillis());
System.out.println(random.nextInt(100)); //57
```

## Создание

* `Random()`
* `Random(long начальное число)`

## Методы

* `setSeed(long начальное_число)`
* `nextInt()`, `nextInt(bound)`, `nextLong()`, `nextBoolean()`
* `nextBytes(byte[])` - заполняет массив байтов случайными значениями
* `nextDouble()`, `nextFloat()` - возвращает значения от 0.0 до 1.0
* `nextGaussian()` - возвращает значения из нормального распределения (начальная точка в 0.0)
* `doubles()`, `ints()`, `longs()` - возвращают стримы для примитивов