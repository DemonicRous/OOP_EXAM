> В Java каждый класс, даже если он не наследуется явно от другого класса, неявно наследуется от класса **Object**. Это означает, что любой пользовательский класс автоматически имеет доступ к методам и свойствам класса Object.

Вот несколько примеров использования методов класса Object в пользовательских классах:

1. **Метод `equals()`**: используется для сравнения объектов на равенство. Если два объекта равны по значению, метод возвращает `true`, иначе — `false`.
```java
public class Person {
    private String name;
    private int age;

    // ...

    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (!(obj instanceof Person)) return false;
        Person person = (Person) obj;
        return name.equals(person.name) && age == person.age;
    }
}
```
В этом примере метод `equals()` переопределяется для проверки равенства двух объектов класса Person.

2. **Метод `hashCode()`**: используется для генерации хэш-кода объекта. Хэш-код может быть использован для хранения и извлечения объектов из коллекций, таких как HashMap или HashSet.
```java
@Override
public int hashCode() {
    int result = 17;
    result = 31 * result + name.hashCode();
    result = 31 * result + age;
    return result;
}
```
Здесь метод `hashCode()` переопределён для генерации уникального хэш-кода на основе имени и возраста человека.

3. **Методы `toString()` и `clone()`**: используются для получения строкового представления объекта и создания его копии соответственно.
```java
@Override
public String toString() {
    return "Person{" +
            "name='" + name + '\'' +
            ", age=" + age +
            '}';
}

// Пример использования метода clone():
Person person1 = new Person("John", 25);
Person person2 = person1.clone();
System.out.println(person1); // Person{name='John', age=25}
System.out.println(person2); // Person{name='John', age=25}
```
Эти методы могут быть полезны при отладке или логировании.

4. **Метод `finalize()`**: вызывается непосредственно перед тем, как объект будет утилизирован сборщиком мусора. Этот метод может использоваться для выполнения дополнительных действий перед уничтожением объекта.
```java
protected void finalize() throws Throwable {
    super.finalize();
    // Выполняем необходимые действия перед уничтожением объекта
}
```
5. **Методы `wait()`, `notify()` и `notifyAll()`**: используются для синхронизации потоков. Эти методы позволяют одному потоку ждать, пока другой поток не выполнит определённое действие, после чего первый поток может продолжить выполнение.
```java
public class MyClass {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public static void main(String[] args) {
        MyClass myClass = new MyClass();
        new Thread(() -> {
            for (int i = 0; i < 10; i++) {
                myClass.increment();
            }
            myClass.notifyAll(); // Уведомляем основной поток о том, что работа выполнена
        }).start();

        while (true) {
            try {
                System.out.println("Waiting for thread to finish...");
                myClass.wait(); // Ждём, пока поток завершит работу
                break;
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }

        System.out.printf("Count is %d%n", myClass.count); // Выводим значение счётчика
    }
}
```
В этом примере основной поток ожидает, пока дополнительный поток увеличит счётчик 10 раз, после чего уведомляет основной поток об окончании работы. Основной поток выводит значение счётчика на экран.

Это лишь некоторые примеры использования методов класса `Object` в пользовательских классах. Класс `Object` предоставляет множество различных методов.