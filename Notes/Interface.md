# INTERFACE : 
I have defined the interface in 3 ways.
1. Any service reqirement specification it consider as an interface.
   - Example - JDBC API access requirement specification to delevop database driver database vander is responsible JDBC API.
             - Servlet API access requirement specification to develop web server , web server vander responsible to implement servlet API.
     
2. From the client's perspective, an interface defines the set of services they expect to receive. From the service provider's perspective, an interface defines the set of services they are offering. Therefore, any agreement or contract between the client and the service provider is referred to as an interface.
    - Example -Through the bank ATM's GUI screen, the bank showcases the set of services it offers. At the same time, the same GUI screen represents the set of services that the customer is willing to accept. Therefore, this GUI screen acts as a contract or agreement between the customer and the bank, ensuring that both parties are aligned on the services being provided and accessed. It serves as a common interface that facilitates the interaction and defines the terms of the transaction.

3. Inside Interface every method is always abstract whether we are declaer or not , Hence interface is consider as 100% pure abstract class.

###### summarise definition 
Any service requirement specification or any contract between client and service provider or 100% pure abstract class in nothing as Interface.

- Whenever we implement any interface for each every method of that interface we have to provide implemeantation otherwise we have to declear class as abstract then next level child class responsibility to provide implementation.
- Every interface method always public and abstract whether we declare or not , Hence we are declare interface method compulsory we should declare as public otherwise we will get compile time error.
```java
interface MyInterface {
    void show();  
    void display();
}
abstract class MyAbstractClass implements MyInterface {  
    public void show() {  // when we implement abstract method then public modifier use
        System.out.println("Show method implemented");
    }
    // display() is not implemented, so we must declare the class as abstract.
}

class MyConcreteClass extends MyAbstractClass {
    public void display() {  // Now providing implementation for display()
        System.out.println("Display method implemented");
    }
    
    public static void main(String[] args) {
        MyConcreteClass obj = new MyConcreteClass();
        obj.show();
        obj.display();
    }
}
```
## Extends vs Implements
- A class can extends only one class at a time.
- An interface can extends any number of interface at a time.
- A class implements any number of interface at a time.
- A class extends another class and can implements any number of interface at a time.
- if we extends and implements at a time then we should extends first and then implements otherwise we get error.
