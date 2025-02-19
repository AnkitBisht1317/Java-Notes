# Adstraction :
- Hidding internal implementation and just highlight set of service what they offering is concept of abstraction.
- In bank ATM GUI screen bank people arre highlight teh set of service what they offering without highlight internal implementation.
- The main advantage of abstraction we are achive security because we con not highlight our internal implementation, without effecting outside person we can able to perfrom any type of change in our internal system  Henece enhancement become easy, it improve maintainability of application.
- By using interface and abstract class we can implemente abstraction.
``` java
abstract class Vehicle {
    // Abstract method (does not have a body)
    abstract void start();
    // Concrete method
    void stop() {
        System.out.println("Vehicle is stopping...");
    }
}
class Car extends Vehicle {
    void start() {
        System.out.println("Car is starting with a key...");
    }
}
public class AbstractionExample {
    public static void main(String[] args) {
        Vehicle myCar = new Car();
        myCar.start();  
        myCar.stop();  
    }
}
```
