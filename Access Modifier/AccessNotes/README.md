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
- final is a modifier applicable for classes,variable and method.
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
