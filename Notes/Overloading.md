# OVERLOADING : 
- Two mwthod are set to be overloaded if only if both method same name different argument type.
- In C language method overloading concept not available hence we can not declare same name but different argument type, if there is change in arrgument type compulsory go for new mwthod which increase complexity of programming.
- But in java we declare multiple method same name but different argument type ,  such type method are called overloaded method.
- Hence overloading concept in java reduced complexity of programming.

```java
class MathOperations {
    int add(int a, int b) {
        return a + b;
    }
    int add(int a, int b, int c) {
        return a + b + c;
    }
    double add(double a, double b) {
        return a + b;
    }
}
public class OverloadingExample {
    public static void main(String[] args) {
        MathOperations math = new MathOperations();
        System.out.println(math.add(5, 10));      
        System.out.println(math.add(5, 10, 15));  
        System.out.println(math.add(5.5, 2.2)); 
    }
}
```

- In overloading method resolution always take palce by complier based on refrence type as overloading also known as complie type polymorphism.
  
