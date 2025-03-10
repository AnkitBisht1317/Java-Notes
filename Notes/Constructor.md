# CONSTRUCTOR 
- Once we create object compulsory we perform initization then only the object in a position to respond properly.
- Whenever we create a object some piece od code will be excuted to perform initialization of object thi piece of code nothig but constructor.
- Hence the main purpose of constructor is to perform initialization of an object.
```java
class Student {
    String name;
    int age;
    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
    public static void main(String[] args) {
        Student s1 = new Student("Alice", 20);
        s1.display();
    }
}
```
- The main purpose of construtor is to initialization of an object but not to create object.
- By default if we declare return type of constructor then we wont't get complie error, complier treated it as a method.
- the only modifier use as constructor public,protected,privateand default.
 
