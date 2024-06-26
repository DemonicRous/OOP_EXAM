> **Final** — это ключевое слово в Java, которое используется для объявления переменной или метода как неизменяемого. Если final применяется к переменной, то её значение не может быть изменено после инициализации.

> 1. **Инициализация final переменных при объявлении:**

Пример:
   ```java
   final int myAge = 25;
   System.out.println(myAge); // выведет 25
   ```

   В этом примере переменная myAge объявляется как final и сразу же инициализируется значением 25. После этого её значение нельзя изменить.

> 2. **Инициализация final переменных с помощью конструктора:**

Пример:
```java
class Person {
final String name;

        Person(String name) {
            this.name = name;
        }
    }

    public class Main {
        public static void main(String[] args) {
            Person person = new Person("Иван");
            System.out.println(person.name); // выведет "Иван"
        }
    }
```

   В этом примере класс `Person` имеет `final` переменную `name`, которая инициализируется в конструкторе. Это гарантирует, что имя человека будет неизменным после создания объекта.

3. **Использование `final` для методов:**

   Если метод объявлен как `final`, его нельзя переопределить в подклассах. Это полезно для обеспечения неизменности поведения метода.

4. **Применение `final` к классам:**

   Объявляя класс как `final`, мы запрещаем его наследование. Это может быть полезно, если мы хотим предотвратить создание подклассов.

Важно отметить, что `final` не делает переменную или метод неизменной во время выполнения программы. Он только запрещает изменение значения переменной после её инициализации и предотвращает переопределение метода в подклассе.