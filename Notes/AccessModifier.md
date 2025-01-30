## Class Level Modifier 
whenever we are writting own class we have provide same information about our file to JVM like - 
1. that class is accessable any where or not
2. child class creation is possible or not
3. object creation is possible or not
we can specifie this information using apropiate modifier.

the only aplicable modifier for top class are:-
```
public
defalut
final
abstract
strictfp
```
Inner class aplicable modifier are:-
```
public
defalut
final
abstract
strictfp
private
protected
static
```
## 1. Public Modifier
- if a class declear as public then we can access that class anywhere.

### Error
- if class Demo1 is not public then while compile Demo2 class will get compile time error (pack1.Demo1 is not in pack1 : cannot be accessed outside pakage) 
![Image](https://github.com/user-attachments/assets/53fbf0e0-3727-40b9-8889-e64c857a64a8)
### Without Error
![Image](https://github.com/user-attachments/assets/732e3a2c-85d5-4334-a411-166ec59646da)


## 2. Default Modifier
- if a class declear default then we access the class only current package. that it outside package we cannot access.(it also known as package level access) 
### Error
![Image](https://github.com/user-attachments/assets/53fbf0e0-3727-40b9-8889-e64c857a64a8)

### Witout Error
![Image](https://github.com/user-attachments/assets/f542c782-459c-4896-ad81-6d570af1e6e4)

## 3. Final Modifier 
- final is a modifieapplir applicable for classes,variable and method.
#### Final Method : 
- whatever method parent has by default available to the child using inheritance if the child not satisfied parent method implimantation then child is allowed 
  redefine the method based on there requirement this process is called overriding.
- if parent class method declear as final we not overrride the method in child class.
### Error
- we declear parent class as final so we don't override final class in parent that's why error occures. if we remove final keyword in parent class then error remove
![Image](https://github.com/user-attachments/assets/8000eaa4-748d-49c7-b453-afb50e4478ed)

#### Final Class : 
- If a class declear as final we can not extends functionality of that class. that is we can not create child class of that class.
- Inheritance not possible using final class.

### Error
![Image](https://github.com/user-attachments/assets/d1534b31-8980-4d68-98d6-7fe40c0ce8c2)
###### Note : 
- every method parsent in final class also a final , but every variable parsent inside final class in not be final.
- Final modifier is secure.
- Disadvantage of final modifier is we can not implimantation Inheritance and Polymorphism which is key concepts of OOPS.
- If no specific requirement then not use final keyword. 

## 3. Abstract Modifier : 
- abstract is a modifier applicable for class and method but not for variable.

#### Abstract Method : 
- Even thus we don't know about implementation still we can declare a method with abstract method.
- In abstract method declaration is available but implementation is not . it's declaration ends with semicolon.

``` java
public abstract void m1(); ✅
public abstract void m1() ❌
```
- Child class is reponsible to provide implementation to parent class abstract method.
``` java
abstract class vechile{
abstract public int requiredWheel();
}
class Bus extends vechile{
public int  requiredWheel(){
return 7;
}
}
```
- By default abstract method in parent class we provided guidelines for child class. that is which method compulsory child has to implement.
- Abstract method never talk about implemantation if any modifier not talk about implemantation that is from illegal combination for abstract modifierrs.
  ```
  final
  native
  synchronized
  static
  private
  strictfp
  ```
#### Abstract Class :
- For any java class if we not allow to create object(Because of partial implementation) such type of class is called abstract class.
- Abstract class instantiation is not possible.
```java
abstract class Animal {
abstract void makeSound();
}
class Dog extends Animal {
void makeSound() {
System.out.println("Woof!");
}
}
public class Main {
public static void main(String[] args) {
// Animal a = new Animal(); // ❌ ERROR: Cannot instantiate an abstract class
Dog dog = new Dog(); // ✅ Instantiating a concrete subclass
dog.makeSound(); // Output: Woof!
}
}
```
- if a class contain atleast one abstract method that compulsory we declare class as abstract class otherwise get compile time error.
- Abstract class can contain zero number abstract method.
  ```java
  abstract HTTPServer{
  doGET();
  doPOST();
  }
  ```
  - If we are extends abstract class then each and every abstract method of parent class should provide implementation otherwise we declare child class is abstract.in this case next level child class provide to implementation.
 ```java
abstract class HTTPServer {
 abstract void doGET();
 abstract void doPOST();
}
abstract class SecureHTTPServer extends HTTPServer {
abstract void doGET();
}
```
## 4 .Private Modifier : 
- If a member is private then we access that member only within the class , outside the class we can not access.
- Abstrsct method sholud be available to the child class to provide implementation whereas the provate method not available to the child class . Hence private abstract combination is illegal for method.

## 5. Protected Member : 
         protected = default + child 
- If member declare as protected then we access that member any where that current package but outside the package access only child class.
- we can access protected member within the current package anywhere using parent and child class refrence.
- But access protected member iin outside package only in the child class . 

## 6. Synchronized Modifier : 
- Synchronized is a modifier applicable for method and block but not classes and variable.
- If multiple thread try to operate at a time on the same java object then there is chance of data inconsistancy problem this is raised condition we can overcome this problem by using synchronized keyword. 
