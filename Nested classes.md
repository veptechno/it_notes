---
title: Nested classes
tags: Java, Basic, Nested, Inner, Class
---
# Вложенные классы
## Виды nested классов
* **Вложеннные (static nested)** - статический класс расположенный внутри другого класса
* **Внутренние (not-static nested)** - не статический класс внутри другого класса
* **Локальные (local)** - класс объявленный внутри другого класса и блока кода {}
* **Анонимные (anonymous)** - класс без явного указания имени экземпляра

### Вложенные классы
Из класса мы имеем доступ к любым статическим полям и методам внешнего класса. Для однозначного обращения к внешнему классу можно использовать *OuterClassName.variable*.
```java=
public class Outer3 {
    private static int prStOuterVar;
    private int outerVar;
      
    static class Nested3 { 
        int getStaticOuterVar() {
            return Outer3.prStOuterVar; //  ok
        }
        
        void setStaticOuterVariable(int var) {
            prStOuterVar = var; // ok
        }
        
        void error() {
            //outerVar = 5; // error
        }
    }
    
    public static void main(String[] args) {
        Outer3.Nested3 nestedObj = new Outer3.Nested3(); // экземпляр класса внутренний
        Outer3.prStOuterVar = 19;
        System.out.println("nestedObj.getStaticOuterVar() = "+nestedObj.getStaticOuterVar());//статическая переменная внешнего класса из экземпляра внутреннего
        
        // устанавливаем через экземпляр внутреннего класса
        nestedObj.setStaticOuterVariable(77);
        System.out.println("Outer3.prStOuterVar = "+ Outer3.prStOuterVar);
    }
}

/*
Вывод программы:
nestedObj.getStaticOuterVar() = 19
Outer3.prStOuterVar = 77
*/
```

### Внутренние классы
Из класса мы имеем доступ к любым полям и методам внешнего класса. Внутренний класс хранит ссылку на внешний экземпляр класса, поэтому для создания внутреннего класса необходимо создать экземпляр внешнего. 
Для однозначного обращения к внешнему классу можно использовать *OuterClassName.this.variable*.
В пределах внутреннего класса нельзя объявлять статические поля и методы (это связано с тем что, внутренний класс неявно связан с объектом своего внешнего класса).

```java=
OuterClass.InnerClass innerObject = outerObject.new InnerClass();
```

### Локальные классы
Внутренний класс может быть объявлен внутри метода или блока инициализации внешнего класса.
Внутренний класс в локальном методе не может быть помечен как private, protected, static и transient

```java=
public class Outer {
    void outerMethod() {
        System.out.println("Метод внешнего класса");
        // Внутренний класс является локальным для метода outerMethod()
        class Inner {
            public void innerMethod() {
                System.out.println("Метод внутреннего класса");
            }
        }
        Inner inner = new Inner();
        inner.innerMethod();
    }
 
    public static void main(String[] args) {
        Outer outer = new Outer();
        outer.outerMethod();
    }
}
```

Внутренний класс в локальном методе не может использовать локальные переменные внешнего метода до тех пор, пока локальная переменная не будет объявлена как финальная (final).
Например, следующий код сгенерирует ошибку компиляции (обратите внимание, что x не является финальной в outerMethod(), но innerMethod() путается получить к ней доступ):

```java=
public class Outer {
    void outerMethod() {
        int x = 98; //Должна быть final
        System.out.println("Метод внешнего класса");
        class Inner {
            public void innerMethod() {
                System.out.println("x = " + x);
            }
        }
        Inner inner = new Inner();
        inner.innerMethod();
    }
    public static void main(String[] args) {
        Outer outer = new Outer();
        outer.outerMethod();
    }
}
```

Основная причина, по которой необходимо объявлять локальную переменную как финальную заключается в том что, локальная переменная живёт в стеке до тех пор, пока метод находится в стеке. А в случае использования внутреннего класса возможна ситуация, когда экземпляр внутреннего класса живёт в куче и после выхода из метода, но ему может быть необходим доступ к переменной, объявленной в методе. Для этого, компилятор может сохранить копию локальной переменной, которая объявлена как финальная, в поле внутреннего класса для дальнейшего использования.

### Анонимные классы
Анонимные внутренние классы объявляются без указания имени класса. Они могут быть созданы как наследники определённого класса или реализацией интерфейса.
Анонимные классы созданные в методе также имеют доступ только к финализированным локальным переменным.
```java=
public class Outer {
    // Анонимный класс наследуется от класса Demo
    static Demo demo = new Demo() {
        @Override
        public void show() {
            super.show();
            System.out.println("Метод внутреннего анонимного класса");
        }
    };
    public static void main(String[] args) {
        demo.show();
    }
}
class Demo {
    public void show() {
        System.out.println("Метод суперкласса");
    }
}
```