## Методы класса Object в Java

> Класс Object является базовым классом для всех классов в Java. Он предоставляет несколько методов, которые могут быть полезны при работе с объектами. Вот некоторые из них:

> 1. **Метод `toString`**:

Метод `toString` служит для получения представления данного объекта в виде строки. При попытке вывести строковое представления какого-нибудь объекта, как правило, будет выводиться полное имя класса. 

Например:

```java
public class Program{
      
    public static void main(String[] args) {
             
        Person tom = new Person("Tom");
        System.out.println(tom.toString()); // Будет выводить что-то наподобие Person@7960847b
    }
}
class Person {
     
    private String name;
     
    public Person(String name){
     
        this.name=name;
    }
}
```

Полученное мной значение (в данном случае `Person@7960847b`) вряд ли может служить хорошим строковым описанием объекта. Поэтому метод `toString()` нередко переопределяют. 

Например:

```java
public class Program{
      
    public static void main(String[] args) {
             
        Person tom = new Person("Tom");
        System.out.println(tom.toString()); // Person Tom
    }
}
class Person {
     
    private String name;
    
    public Person(String name){
     
        this.name=name;
    }
     
    @Override
    public String toString(){
          
        return "Person " + name;
    }
}
```

> 2. **Метод `hashCode`**:

Метод `hashCode` позволяет задать некоторое числовое значение, которое будет соответствовать данному объекту или его хэш-код. По данному числу, например, можно сравнивать объекты.

Например, выведем представление вышеопределенного объекта:

```java
Person tom = new Person("Tom");
System.out.println(tom.hashCode()); // 2036368507
```
Но мы можем задать свой алгоритм определения хэш-кода объекта:
```java
class Person {
     
    private String name;
    
    public Person(String name){
     
        this.name=name;
    }
     
    @Override
    public int hashCode(){
 
        return 10 * name.hashCode() + 20456;
    }
}
```
> 3. **Получение типа объекта и метод `getClass`**:

Метод `getClass` позволяет получить тип данного объекта:

```java
Person tom = new Person("Tom");
System.out.println(tom.getClass()); // class Person
```

> 4. **Метод `equals`**:

Метод `equals` сравнивает два объекта на равенство:

```java
public class Program{
      
    public static void main(String[] args) {
             
        Person tom = new Person("Tom");
        Person bob = new Person("Bob");
        System.out.println(tom.equals(bob)); // false
         
        Person tom2 = new Person("Tom");
        System.out.println(tom.equals(tom2)); // true
    }
}
class Person {
     
    private String name;
     
    public Person(String name){
     
        this.name=name;
    }
     
    @Override
    public boolean equals(Object obj){
         
        if (!(obj instanceof Person)) return false;
 
        Person p = (Person)obj;
        return this.name.equals(p.name);
    }
}
```
Метод equals принимает в качестве параметра объект любого типа, который мы затем приводим к текущему, если они являются объектами одного класса.
> 5. **`instanceof`**:

Оператор `instanceof` позволяет выяснить, является ли переданный в качестве параметра объект объектом определенного класса, в данном случае класса `Person`. Если объекты принадлежат к разным классам, то их сравнение не имеет смысла, и возвращается значение `false`.

Затем сравниваем по именам. Если они совпадают, возвращаем `true`, что будет говорить, что объекты равны.