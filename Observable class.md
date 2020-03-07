---
tags: Java, Basic, Observable, Observer, java.util
title: Observable and Observer classes
---
# Observable класс

Служит для создания подклассов, за которыми могут наблюдать другие части программы. Наблюдающие подклассы должны реализовывать интерфейс *Observer*.

Для того, чтобы уведомить наблюдателей надо вызвать `setChanged()`, а затем `notifyObservers()`. После этих действий у слушателей вызывается метод `update()`. Можно передавать аргумент.

## Методы

К публичным методам можно отнести `addObserver(Observer)`, `deleteObserver(Observer)` и `deleteObservers()`. Эти методы вызываются обычно внешними классами для подписки на обновления.

К protected методам можно отнести `setChanged()`, `notifyObservers([Object])`. Эти методы вызываются внутри при изменении состояния объекта. ==`notifyObservers([Object])` по факту public.==

# Интерфейс Observer

Для того, чтобы подписать объект на *Observable* нужно, чтобы он реализовывал интерфейс *Observer*.

## Методы

`void update(Observable, Object)` - *Object* может быть *null* если был вызван `notifyObservers()`.