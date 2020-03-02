---
tags: Java, Basic, Collections, Properties
title: Properties Class
---
# Properties Class

Находится в пакете *java.util*.

Используется в методе System.getProperties, возвращая [информацию](https://docs.oracle.com/javase/tutorial/essential/environment/sysprop.html) о системе, пользователе и так далее.

По факту это что то типа Map, но с 2 особенностями.
* Он позволяет задавать значения по умолчанию.
* Есть методы `store()` и `load()` позволяющие легко сохранять и загружать Properties.