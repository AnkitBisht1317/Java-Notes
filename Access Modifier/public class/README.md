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
if s class declear as public then we can access that class anywhere.

# Error

# Without Error

if class Demo1 is not public then while compile Demo2 class will get compile time error (pack1.Demo1 is not in pack1 : cannot be accessed outside pakage)
