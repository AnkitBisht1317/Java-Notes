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
## 1. Public Classs
if a class declear as public then we can access that class anywhere.

### Error
![Image](https://github.com/user-attachments/assets/53fbf0e0-3727-40b9-8889-e64c857a64a8)
### Without Error
![Image](https://github.com/user-attachments/assets/732e3a2c-85d5-4334-a411-166ec59646da)
if class Demo1 is not public then while compile Demo2 class will get compile time error (pack1.Demo1 is not in pack1 : cannot be accessed outside pakage)

## 2. Default Class
if a class declear default then we access the class only current package. that it outside package we cannot access.(it also known as package level access) 
### Error
![Image](https://github.com/user-attachments/assets/53fbf0e0-3727-40b9-8889-e64c857a64a8)

### Witout Error
![Image](https://github.com/user-attachments/assets/4ed911b2-7d93-4788-ad3e-4519f040fa89)
