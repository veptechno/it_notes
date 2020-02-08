---
title: wait/notify
tags: Java, Basic, Wait, Notify, Thread
---
# Wait/Notify

Это методы из класса Object. 
Все они должны вызываться из синхронизированного контекста.

* Метод `wait()` вынуждает вызывающий поток исполнения уступить монитор и перейти в состояние ожидания до тех пор, пока какой-нибудь другой поток исполнения не войдет в тот же монитор и не вызовет метод `notify()`. 
* Метод `notify()` возобновляет исполнение потока, из которого был вызван метод `wait()` для того же самого объекта. 
* Метод `notifyAll()` возобновляет исполнение всех потоков,  из  которых был вызван метод `wait()` для того же самого объекта. Одному из этих потоков предоставляется доступ. 