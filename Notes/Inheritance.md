# INHERITANCE(IS - A Relationship) : 
- Inheritance where a child class (or subclass) derives properties and behaviors (methods) from a parent class (or superclass). It helps establishing a relationship between classes.
- The main advantage if inheritance is code reusability.
- By using extends keyword we can implementation inheritance.
```java
class Animal {
    void sound() {
        System.out.println("Some sound");
    }
}
// Child class inheriting from Animal
class Dog extends Animal {
    void sound() {
        System.out.println("Woof!");
    }
}
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();  
        dog.sound(); 
    }
}
```
- child refrence we called parent or child but the refrence we only all only parent not child.
- Every class in java is a child class of object either directly or indirectly so that object class method available every java class.

## Types Of Inheritance : 
Java supports three types of inheritance:

1. Single Inheritance
A child class inherits from a single parent class.

```java
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}
class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks.");
    }
}
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat();  // Inherited method
        dog.bark();
    }
}
```

2. Multilevel Inheritance
A child class inherits from a parent class, and another child class inherits from it (forming a chain).

```java
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}
class Mammal extends Animal {
    void walk() {
        System.out.println("Mammals can walk.");
    }
}
class Dog extends Mammal {
    void bark() {
        System.out.println("Dog barks.");
    }
}
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat();  // Inherited from Animal
        dog.walk(); // Inherited from Mammal
        dog.bark(); // Defined in Dog
    }
}
```

3. Hierarchical Inheritance
A single parent class has multiple child classes.

```java
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}
class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks.");
    }
}
class Cat extends Animal {
    void meow() {
        System.out.println("Cat meows.");
    }
}
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat();  // Inherited method
        dog.bark();

        Cat cat = new Cat();
        cat.eat();  // Inherited method
        cat.meow();
    }
}
```

#### Question - why java can not support for multiple inheritance ?
Ans - A java class can not extends more the one class at a time  , there may be chance of ambigute problem hence java can not support multiple inheritance.
- But interface con extends any no of class at a time so interfaace supprot multiple inheritance.
