## Инкапсуляция

> **Инкапсуляция** — это принцип, который позволяет скрыть детали реализации объекта от внешнего мира и предоставить только необходимые методы для взаимодействия с ним. Это помогает защитить данные и логику объекта от нежелательных изменений и обеспечивает безопасность и надежность кода.

### Пример на Java:

```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Метод для получения имени
    public String getName() {
        return name;
    }

    // Метод для установки возраста
    public void setAge(int age) {
        if (age >= 0) {
            this.age = age;
        } else {
            throw new IllegalArgumentException("Возраст должен быть неотрицательным");
        }
    }
}
```

В этом примере класс `Person` инкапсулирует данные о человеке (`name` и `age`), предоставляя только методы для их чтения и изменения. Это позволяет контролировать доступ к данным и предотвращать их неправильное использование.

## Наследование

> **Наследование** — это механизм, позволяющий одному классу наследовать свойства и методы другого класса. Это упрощает код и позволяет повторно использовать уже написанный код.

### Пример на Java:

```java
abstract class Animal {
    protected String species;

    Animal(String species) {
        this.species = species;
    }

    abstract void makeSound();
}

class Dog extends Animal {
    Dog(String species) {
        super(species);
    }

    @Override
    void makeSound() {
        System.out.println("Гав-гав!");
    }
}
```

Здесь класс `Dog` наследует свойства и методы класса `Animal`, что позволяет ему иметь вид животного и издавать характерный звук.

## Полиморфизм

> **Полиморфизм** - это принцип объектно-ориентированного программирования, который позволяет использовать один и тот же интерфейс для разных типов данных. Это позволяет писать более гибкий и универсальный код.

### Пример на Java:

```java
interface Animal {
    void makeSound();
}

class Dog implements Animal {
    public void makeSound() {
        System.out.println("Woof!");
    }
}

class Cat implements Animal {
    public void makeSound() {
        System.out.println("Meow!");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.makeSound(); // выводит "Woof!"

        Animal cat = new Cat();
        cat.makeSound(); // выводит "Meow!"
    }
}
```

В этом примере интерфейс `Animal` определяет метод `makeSound()`, который должен быть реализован в каждом классе, реализующем этот интерфейс. Классы `Dog` и `Cat` реализуют этот метод по-разному, что позволяет им вести себя по-разному при вызове метода `makeSound()`. Таким образом, один и тот же код может работать с разными типами данных, что делает его более универсальным и гибким.

## Абстракция 

> **Абстракция** — это принцип, который позволяет выделить общие свойства и характеристики объектов или процессов и игнорировать несущественные детали. Это помогает упростить понимание сложных систем и сделать код более читаемым и поддерживаемым.

### Пример на Java:

```java
interface Shape {
    double getArea();
}

class Rectangle implements Shape {
    private double length;
    private double width;

    public Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    @Override
    public double getArea() {
        return length * width;
    }
}

class Circle implements Shape {
    private double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    @Override
    public double getArea() {
        return Math.PI * radius * radius;
    }
}
```

В этом примере интерфейс `Shape` определяет метод `getArea()`, который должен быть реализован в каждом классе, реализующем этот интерфейс. Классы `Rectangle` и `Circle` реализуют этот метод по-разному, но оба класса могут использоваться в коде, где требуется вычислить площадь фигуры. Таким образом, код, использующий интерфейс `Shape`, может работать с разными типами фигур без необходимости знать их конкретные реализации.