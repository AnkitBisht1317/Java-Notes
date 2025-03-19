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

## Type Of Constructor : 
- There are two type of constructor

### 1. Default Constructor :
- Compiler is responsible to generate default constructor(NOT JVM) if we wan't writing any constructor then only complier generate default constructor.
- It is always no argument constructor.
- The access modifier of default constructor excatly same as class(Public or default).
- It contain only one line super() it is no argument call to super class constructor.
- We can super() or this() only in first line is constructor then get compile time error.
- Within the constructor we can take super() or this() but not both at a time.
- We use super() or this() only inside a constructor.

```java
class Student {
    String name;
    int age;
    public Student() {
        System.out.println("Default constructor called!");
        name = "Unknown";
        age = 0;
    }
    public void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
    public static void main(String[] args) {
        Student s1 = new Student();
        s1.display(); // Output: Name: Unknown, Age: 0
    }
}
```
  |                        Super(),This()                                            |                                Super , this                                |
  |----------------------------------------------------------------------------------|----------------------------------------------------------------------------|
  | These are constructor called to call super class and current class constructor.|  These are keyword to refer super class and current class Instance member.|
  | Use in only in constructor in first line.                                      |  Use in anywhere but not static area.                                     |
  | Only one time in constructor.                                                  |  we can use any number of time.                                           |
 
  ### 2. Parameterized Constructor :
  - With a class we declare multiple constructor and all these constructor have same name but different type argument hence all these constructor consider as parameterized constructor.
  - Hence Overloading concept applicable for constructor.
```java
class Student {
    String name;
    int age;
    public Student(String studentName, int studentAge) {
        name = studentName;
        age = studentAge;
    }
    public void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }

    public static void main(String[] args) {
        Student s1 = new Student("Alice", 20);
        Student s2 = new Student("Bob", 22);
        s1.display(); // Output: Name: Alice, Age: 20
        s2.display(); // Output: Name: Bob, Age: 22
    }
}
```
- For constructor Inheritance and overriding concept are applicable.
- Every class in java including abstract class contain constructor but interface does not contain constructor.
