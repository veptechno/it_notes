---
title: io
tags: Java, Basic, io, Input, Output, Stream
---
# Потоки ввода вывода

В основе всех классов, управляющих потоками байтов, находятся два абстрактных класса: **InputStream** (представляющий потоки ввода) и **OutputStream** (представляющий потоки вывода)

Но поскольку работать с байтами не очень удобно, то для работы с потоками символов были добавлены абстрактные классы **Reader** (для чтения потоков символов) и **Writer** (для записи потоков символов).

|                          | Поток ввода | Поток вывода |
| ------------------------ | ----------- | ------------ |
| **Работает с байтами**   | InputStream | OutputStream |
| **Работает с символами** | Reader      | Writer       |

*System.in* - InputStream
*System.out* - PrintStream (наследник OutputStream)

[Уроки по потокам ввода-вывода](https://metanit.com/java/tutorial/6.1.php)