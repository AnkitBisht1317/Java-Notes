# OVERRIDING 
- Whatever method parent has by default available to child to inheritance, if child not satisfy with parent class implementation then child allowed to redefine that method based on it's requriment this process is called overriding.
- Parent class method which is overriden called overriden method , and child class method which is overriding is called overriding method.
```java
class Parent {
    void show() {
        System.out.println("This is the parent class");
    }
}
class Child extends Parent {
    @Override
    void show() {
        System.out.println("This is the child class (Overridden Method)");
    }
}
public class Main {
    public static void main(String[] args) {
        Parent parentObj = new Parent();
        Child childObj = new Child();
        parentObj.show(); // Output: This is the parent class
        childObj.show();  // Output: This is the child class (Overridden Method)
    }
}
```
- In overriding method revolution always take care by JVM based on run time object and hence overriding is called as RUN TIME POLYMORPHISM/DYNAMIC POLYMORPHISM.

### RULES : 
- In Overriding method name and argument type must be same
- In overriding return ttype must be same but this is rule is applicable  1.4 version only for 1.5 version onwards we can taken covariant return type.
- Parent class private method not available to the child hence override concept method not applicable for private method.
- Based on our requriment we can define excatly same private method in child class it is valid but not overriding
- parent class abstract method we should overred in child class to implementation.
- while overriding we can not reduce scope of access modifier but we increase the scope.

                    ------------------------------------------------
                    |            parent | child                     |
                    -------------------------------------------------
                    |            public | public                    |
                    |         protected | protected/public          |
                    |           default | default/protected/public  |
                    -------------------------------------------------

- We can not override static method on non-static otherwise we will get complie time error , vice versa.
- if both static then no complie time error , but it is not overriding it known method hiding.
