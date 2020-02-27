---
title: String
tags: Java, Basic, String, Classes
---
# Строки
* Класс реализует интерфейсы *Serializable* и *CharSequence*. Поскольку он входит в пакет *java.lang*, его не нужно импортировать.
* Класс *String* в Java — это *final* класс, который не может иметь потомков.
* Класс *String* — *immutable* класс, то есть его объекты не могут быть изменены после создания. Любые операции над объектом *String*, результатом которых должен быть объект класса *String*, приведут к созданию нового объекта.
* Благодаря своей неизменности, объекты класса *String* являются потокобезопасными и могут быть использованы в многопоточной среде.
* Каждый объект в Java может быть преобразован в строку через метод *toString*, унаследованный всеми Java-классами от класса *Object*.
* Все объекты *String* созданные через кавычки хранятся в пуле строк.


## Конструкторы
* `String()`
* `String(char[] chars)`
* `String(char[] chars, int startIndex, int count)`
* `String(String string)`
* `String(byte[] bytes)` - из формата ISO-8859-1 (Charset можно указать самому)
* `String(StringBuffer buffer)`
* `String(StringBuilder builder)`


## Методы
* `equals(second_string)` - сравнение строк
* `equalsIgnoreCase(second_string)` - сравнение строк без учёта регистра
* `int length()`
* `char charAt(index)` - символ по индексу 
* `valueOf(obj)` - перевод любого объекта или примитива к строке
* `valueOf(char[], startIndex, length)`
* `join(CharSequence delimiter, CharSequence... elements)` - преобразует элементы в строку с разделителем `delimiter`
* `join(CharSequence delimiter, Iterable<? extends CharSequence> elements)` - преобразует коллекцию в строку с разделителем `delimiter`
* `split(String regex)` - разбиение на подстроки по регулярному выражению
* `indexOf(str)` - индекс подстроки
* `substring(start, end)` - последний символ не входит в подстроку. При этом полностью копируется массив символов.
* `toLowerCase()`
* `toUpperCase()`
* `replace(char oldChar, char newChar)`, `replace(CharSequence old, CharSequence new)`, `replaceAll(regex, replacement)`, `replaceFirst(regex, replacement)`
* `format("a = %s, b = %c, c = %d", "abc", 'f', 3)` - [документация по Formatter](https://docs.oracle.com/javase/7/docs/api/java/util/Formatter.html)
* `toCharArray()`
* `getChars(начало_источника, конец источника(не включая), адресат[], начало адресата)`
* `getBytes()`
* `intern()` - переводит строку в пул
* `startsWith()`
* `endsWith()`
* `concat(string)`
* `trim()`
* `contains(string)`
* `boolean matches(String regex)`
* `chars()` - возвращает IntStream

## Advanced

Jdk 9 - [youtube](https://www.youtube.com/watch?v=v2XLg4SvCF8)