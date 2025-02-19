# Encapsulation : 
- The process of binding data and corresponding method into a single unit is nothing but Encapsulation.
- If any component follows data hodding and abstraction such type of component said to be encapsulation component.
                              ###[Encapsulation = Data Hidding + Abstraction]
- The main advantage of encapsulation are achive security, enhancement become easy, maintainability of application.
- The main advantage of encapsulation is we can achive security but disadvantage of encapsulation is it increase length of the code and slow down excution.
```java
class Person {
    // Private variables (cannot be accessed directly outside the class)
    private String name;
    private int age;
    // Public getter method to access the private variable
    public String getName() {
        return name;
    }
    // Public setter method to modify the private variable
    public void setName(String newName) {
        name = newName;
    }
    // Public getter for age
    public int getAge() {
        return age;
    }
    // Public setter for age
    public void setAge(int newAge) {
        if (newAge > 0) { // Simple validation
            age = newAge;
        } else {
            System.out.println("Age must be positive!");
        }
    }
}
// Main class
public class EncapsulationExample {
    public static void main(String[] args) {
        Person p = new Person();
        // Setting values using setters
        p.setName("John");
        p.setAge(25);
        // Getting values using getters
        System.out.println("Name: " + p.getName());
        System.out.println("Age: " + p.getAge());
    }
}
```
