## Классы

> **Класс в Java** — это шаблон или план для создания объектов, которые представляют собой конкретные экземпляры класса. Класс определяет структуру и поведение своих экземпляров.

### Пример:

Представим, что мы хотим создать программу, которая будет работать с разными типами автомобилей. Мы можем определить класс `Car`, который будет описывать общие характеристики всех автомобилей:

```java
public class Car {
    private String model; // модель автомобиля
    private int year; // год выпуска
    private double price; // цена

    // методы класса
    public void setModel(String model) {
        this.model = model;
    }

    public String getModel() {
        return model;
    }

    public int getYear() {
        return year;
    }

    public double getPrice() {
        return price;
    }
}
```

В этом примере класс `Car` имеет три поля (`model`, `year` и `price`), которые определяют его структуру. Также класс содержит методы `setModel()`, `getModel()`, `getYear()` и `getPrice()`, которые определяют поведение класса.

Теперь мы можем создать экземпляр класса Car:

```java
Car myCar = new Car();
myCar.setModel("Toyota Corolla");
myCar.setYear(2018);
myCar.setPrice(15000.0);
System.out.println(myCar.getModel()); // Toyota Corolla
System.out.println(myCar.getYear()); // 2018
System.out.println(myCar.getPrice()); // 15000.0
```

Этот код создаёт объект `myCar` типа `Car` и присваивает ему значения полей. Затем он выводит значения этих полей на экран.

Таким образом, `класс` — это основа объектно-ориентированного программирования в Java. Он позволяет создавать объекты с общими характеристиками и поведением, а также упрощает повторное использование кода.