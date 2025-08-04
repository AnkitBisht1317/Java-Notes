# Inner Class
- Sometime we can declare a class inside another class such type of classes are called inner class.
- Inner class concept interduce in 1.1 version to fix GUI bugs as part because of powerful feature and benefit of inner class slowly programmer start using in redular coding also.
- If one type of object cannot exist without another type of object, then we should use an inner class.
- University consist of sevral department without exist university there is no chance of exist department hence we have to declare department class inside university class.
- Based on position declaretion and behaviour all inner class are divided into four type.

### i) Normal or Regular Inner class 
- If we declare a named class directly inside another class without the static modifier, it is called a normal or regular inner class.
- Inside a non-static inner class, we cannot declare any static members. Therefore, we cannot declare a main() method inside it, and we cannot run a non-static inner class directly from the command line.
- We cannot access a non-static inner class directly from the static area of the outer class. We must first create an instance of the outer class, then use it to create the inner class object.
```java
class Outer {
    class Inner {
        void show() {
            System.out.println("Inner class method");
        }
    }

    public static void main(String[] args) {
        Outer outer = new Outer();
        Outer.Inner inner = outer.new Inner(); // Correct way
        inner.show();
    }
}
```
- We can access inner class code from the instance area of the outer class.
- We can access a non-static inner class from outside the outer class using an instance of the outer class.
```java
class Outer {
    class Inner {
        void show() {
            System.out.println("Inner class accessed from outside");
        }
    }
}

public class Test {
    public static void main(String[] args) {
        Outer outer = new Outer();
        Outer.Inner inner = outer.new Inner();
        inner.show();
    }
}
```
- The only applicable modifier for outer class are public, default, final, abstract, strictfp.
- But for inner class applicable modifier are public, default, final, abstract, strictfp, private, static.

### ii) Method Local Inner Class
-Sometimes we declare a class inside a method. Such a class is called a method-local inner class.
- The main purpose of a method-local inner class is to define method-specific functionality that is required repeatedly within that method.
- Method-local inner classes are best suited for situations where we want to achieve something similar to nested methods (which Java does not support directly).
- We can access a method-local inner class only within the method where it is declared. It cannot be accessed outside the method because its scope is limited to that method. Due to this limited scope, method-local inner classes are the most rarely used type of inner class.
```java
class Outer {
    void display() {
        class Message {
            void show() {
                System.out.println("Hello from method-local inner class");
            }
        }

        Message msg = new Message(); // ✅ Valid
        msg.show();
    }

    public static void main(String[] args) {
        new Outer().display();

        // ❌ Below line is invalid
        // Message m = new Message(); // Cannot access here
    }
}
```

### iii) Anonymous Inner Class
-  Sometime we declare inner class without name such type of inner class are called anonymous inner class.
-  THe main purpose of anonymous inner class is just for instance use (one time use).
-  Based on declareation and behaviour there are 3 typr of anonymous calsses.

```java
interface Greeting {
    void sayHello();
}

public class Main {
    public static void main(String[] args) {
        // Anonymous class implementing Greeting interface
        Greeting greeting = new Greeting() {
            @Override
            public void sayHello() {
                System.out.println("Hello from anonymous class!");
            }
        };

        greeting.sayHello(); // Output: Hello from anonymous class!
    }
}
```

### iv) Static inner Class
- Sometimes we can declare inner class with static modifier such type inner class are called static nested class.
- In the case of normal or regular inner class without exiting outer class object there is no chance of exiting inner class object that is inner class object is strongly assosicated with outer class object.
- But in the case of static nasted class without existing outer class object there may be chance of nested class object hence static class object is not strongly associted with outer class object.

```java
public class OuterClass {
    static int outerData = 50;

    // Static inner class
    static class InnerClass {
        void display() {
            System.out.println("Outer data: " + outerData);
        }
    }

    public static void main(String[] args) {
        // Creating object of static inner class without OuterClass object
        OuterClass.InnerClass inner = new OuterClass.InnerClass();
        inner.display(); // Output: Outer data: 50
    }
}
```




















