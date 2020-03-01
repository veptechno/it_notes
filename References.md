---
tags: Java, Basic, Weak, Soft, Phantom, Reference
title: Strong, Soft, Weak and Phantom References
---
# Типы ссылок на Java объекты
[Статья про слабые ссылки в википедии.](https://ru.wikipedia.org/wiki/%D0%A1%D0%BB%D0%B0%D0%B1%D0%B0%D1%8F_%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0)

## Strong
Строгие ссылки используются всегда при связывании переменной с объектом. Пока есть строгая ссылка на объект он не будет собран GC.
```java=
String s = new String("abc"); //s - строгая ссылка
```

## Weak
*Слабые* ссылки представлены классом *java.lang.ref.WeakReference*. Как только остаётся только Weak ссылка, то объект будет жив только до следующей сборки.
Используются во всяких кешах (Хотя лучше подходят для этого Soft). Также есть [WeakHashMap](https://hackmd.io/0T5-ErJvSPmWKNIxUnzSeg) использующая данные ссылки.

```java=
String s = new String("abc");
WeakReference<String> ws = new WeakReference<>(s);
s = null; //Теперь на "abc" ссылается только ws
```

## Soft
*Мягкие* ссылки представлены классом *java.lang.ref.SoftReference*. Убираются GC только когда она нуждается в памяти. Имеет смысл использовать их для кеша (подходит лучше, чем Weak).
Создаётся также как и *WeakReference*.

## Phantom
*Фантомные* ссылки представлены классом java.lang.ref.PhantomReference.
Создаётся также как и *WeakReference*.
Для Basic достаточно сложно. По факту при ближайшей сборке объект удаляется и помещается в специальную очередь из которой можно узнать удалён он или нет. Тут [объяснение](http://samolisov.blogspot.com/2011/09/phantomreferences-java.html) и [тут](https://javarush.ru/groups/posts/2291-osobennosti-phantomreference). 

# Методы
* `T get()` - возращает объект на который указывает ссылка. Если он собран, то *null*
* `void clear()` - очищает ссылкуhttp://samolisov.blogspot.com/2011/09/phantomreferences-java.html