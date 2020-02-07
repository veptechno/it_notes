---
title: Exceptions
tags: Java, Basic, Exceptions
---
# Исключения
## Иерархия классов
Throwable -> Exception -> RuntimeException
\\> Error

## try-with-resources
Объекты внутри () должны реализовывать интерфейс *AutoCloseable*
```java=
try(
InputStream is = new FileInputStream("c:/file.txt");
OutputStream os = new FileOutputStream("c:/output.txt")
)
{
    is.read(…)
    os.write(…);
}
```

## RuntimeException из пакета java.lang


| Исключение                      | Описание                                                                                                                       |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| ArithmeticException             | Например деление на ноль                                                                                                       |
| ArrayIndexOutOfBoundsException  | Выход индекса за пределы массива                                                                                               |
| ArrayStoreException             | Присваивание объекту массива объекта несовместимого типа                                                                       |
| ClassCastException              | Неверное приведение типов                                                                                                      |
| EnumConstantNotPresentException | Попытка воспользоваться неопределённым значением перечисления                                                                  |
| IllegalArgumentException        | Употребление недопустмого аргумента при вызове метда                                                                           |
| IllegalMonitorStateException    | Например ожидание незаблокированного потока исполнения                                                                         |
| IllegalStateException           | Неверное состояние среды или приложения (метод был вызван в неподходящий момент времени)                                       |
| IllegalThreadStateException     | Несовместимость запрашиваемой операции с текущим состоянием потока исполнения (например повторный вызов метода start у Thread) |
| IndexOutOfBoundsException       | Индекс вне контейнера (любого)                                                                                                 |
| NegativeArraySizeException      | Отрицательный размер массива                                                                                                   |
| NullPointerException            | Неверное использование пустой ссылки                                                                                           |
| NumberFormatException           | Неверное преобразование символьной строки в число                                                                              |
| SecurityException               | Попытка нарушения безопасности                                                                                                 |
| StringIndexOutOfBounds          | Попытка индексации за пределами символьной строки                                                                              |
| TypeNotPresentException         | Тип не найден                                                                                                                  |
| UnsupportedOperatoinException   | Обнаружена неподдерживаемая операция                                                                                           |

## Exception из пакета java.lang


| Исключение                   | Описание                                      |
| ---------------------------- | --------------------------------------------- |
| ClassNotFoundException       | Класс не найден                               |
| CloneNotSupportException     | Не реализован интерфейс Cloneable             |
| IllegalAccessException       | Доступ к классу не разрешён                   |
| InstantionException          | Попытка создать объект абстрактного класса    |
| InterruptedException         | Один поток исполнения прерван другим потоком  |
| NoSuchFieldException         | Запрашиваемое поле не существует              |
| NoSuchMethodException        | Запрашиваемый метод не существует             |
| ReflectiveOperationException | Суперкласс исключений, связанных с рефлексией |


## Цепочки исключений

С jdk 1.4 стало возможным указывать исключение, которое было причиной другого исключения (указывать причину ошибки).
Для этого есть 2 конструктора и методы
```java=
Throwable(Throwable причина_исключения)
Throwable(String сообщение, Throwable причина_исключения)

Throwable getCause()
Throwable initCause(Throwable причина_исключения)
```
