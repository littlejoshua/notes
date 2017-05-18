## compound variable
- type modifier **(```*``` or ```&```)**: applies to variable, not the base type.
- __```*```__ and __```&```__ have multiple meanings, as modifier or operator
- when comeing with base type, they are modifiers, meaning __pointer type (```*```)__ and __reference type (```&```)__
- when coming alone, they are operators,  __dereference operator (```*```)__ and __address-of operator (```&```)__

https://liam0205.me/2017/02/05/pointer-in-C-and-Cpp/
## declare and define
A __declaration__ makes a name known to the program. A file that wants to use a name defined elsewhere includes a declaration for that name. A __definition__ creates the associated entity.

A variable __declaration__ specifies the type and name of a variable. 
A variable __definition__ is a declaration. In addition to specifying the name and type, a definition also allocates storage and may provide the variable with an initial value.

To obtain a __declaration__ that is __not__ also a __definition__, we add the ```extern``` keyword and may not provide an explicit initializer:
```cpp
extern int i; // declares but does not define i
int j; // declares and defines j
```

##