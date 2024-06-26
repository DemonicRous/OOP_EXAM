## Сигнатура метода в Java

> **Сигнатура метода в Java** — это часть объявления метода, которая включает в себя имя метода и типы параметров (если они есть). Сигнатура определяет, как метод может быть вызван и какие аргументы могут быть переданы ему.

Вот несколько примеров сигнатур методов:

> 1. `public static void main(String[] args)` — это сигнатура основного метода программы. Он не принимает никаких аргументов и не возвращает значения.

> 2. `public int add(int a, int b)` — это сигнатура метода, который принимает два целочисленных аргумента и возвращает их сумму.

> 3. `public boolean isEven(int number)` — это сигнатура метода, который проверяет, является ли число чётным, и возвращает логическое значение.
     
> 4. `public String getName()` — это сигнатура метода, который возвращает строку с именем объекта.
     
> 5. `public void setName(String name)` — это сигнатура метода, который устанавливает имя объекта.
     
> 6. `public double calculateArea(double radius)` — это сигнатура метода, который вычисляет площадь круга по его радиусу.
     
> 7. `public long getAge()` — это сигнатура метода, возвращающего возраст объекта.
     
> 8. `public void printMessage(String message)` — это сигнатура метода для вывода сообщения на экран.
     
> 9. `public List<String> getFriends()` — это сигнатура метода, возвращающего список друзей объекта.
     
> 10. `public void eat(Food food)` — это сигнатура метода, принимающего объект класса Food и выполняющего над ним действие «есть».

Важно понимать, что сигнатура метода определяет только его форму, но не реализацию. 

`Реализация метода` — это код, который выполняется при вызове метода.

Пример:

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

В этом примере метод `main` имеет сигнатуру `public static void main(String[] args)`. Это означает, что метод не принимает аргументов и не возвращает значение. При выполнении программы будет выведено сообщение «`Hello World!`».


















