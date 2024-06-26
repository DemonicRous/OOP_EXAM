## Геттеры и сеттеры

> **Геттеры и сеттеры** — это методы, которые используются для получения (`getter`) и установки (`setter`) значений полей класса. Они позволяют контролировать доступ к полям класса и обеспечивают инкапсуляцию данных.

В Java геттеры и сеттеры обычно объявляются с использованием следующих соглашений об именах:
- `Геттер`: имя метода начинается со слова «`get`», за которым следует имя поля в верхнем регистре;
- `Сеттер`: имя метода начинается со слова «`set`», за которым следует имя поля в нижнем регистре.

Вот пример использования геттеров и сеттеров для доступа к полю класса:

```java
public class MyClass {
    private int myField; // приватное поле

    public int getMyField() { // геттер
        return myField;
    }

    public void setMyField(int value) { // сеттер
        myField = value;
    }
}
```

Использование `геттеров` и `сеттеров` позволяет скрыть детали реализации класса от внешнего мира и обеспечивает гибкость при изменении логики работы класса в будущем.