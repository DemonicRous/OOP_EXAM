## Статический класс

> **Статический класс** — это класс, который не может быть создан с помощью ключевого слова new. Это означает, что нельзя создать экземпляр статического класса.

### Особенности использования статических классов:

- Статические классы могут содержать только статические методы и переменные.
- Статические методы могут обращаться к статическим переменным и методам без создания экземпляра класса.
- Статические переменные принадлежат классу, а не его экземплярам.
- Статический класс не имеет доступа к нестатическим членам других классов.
- Статические классы используются для хранения вспомогательных методов и констант.

Вот несколько примеров использования статических классов:

> **1. Пример статического класса с методами:**

```java
public class MyUtils {
    public static int add(int a, int b) {
        return a + b;
    }
}
```

В этом примере класс `MyUtils` содержит статический метод `add`, который принимает два аргумента и возвращает их сумму. Метод `add` можно вызвать без создания экземпляра класса `MyUtils`:

```java
System.out.println(MyUtils.add(5, 3)); // выведет 8
```

> **2. Пример статического класса с константами:**

```java
public final class Constants {
    private Constants() { } // предотвращает создание экземпляров

    public static final int MAX_VALUE = 100;
    public static final String NAME = "John Doe";
}
```

Этот класс содержит две статические константы: `MAX_VALUE` и `NAME`. Эти константы можно использовать в любом месте программы, где доступен класс `Constants`:

```java
int maxValue = Constants.MAX_VALUE;
String name = Constants.NAME;
```

> **3. Пример использования статического класса в качестве утилиты:**

```java
public static class MathUtils {
    public static double squareRoot(double x) {
        // вычисление квадратного корня
    }

    public static boolean isPrime(int n) {
        // проверка числа на простоту
    }
}
```
Класс MathUtils содержит два статических метода: squareRoot и isPrime. Эти методы можно вызывать без создания экземпляра класса MathUtils:
```java
double sqrt = MathUtils.squareRoot(4); // квадратный корень из 4 равен 2
boolean prime = MathUtils.isPrime(7); // число 7 простое
```


