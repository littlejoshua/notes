## compound variable
- type modifier **(```*``` or ```&```)**: applies to variable, not the base type.
- __```*```__ and __```&```__ have multiple meanings, as modifier or operator
- when comeing with base type, they are modifiers, meaning __pointer type (```*```)__ and __reference type (```&```)__
- when coming alone, they are operators,  __dereference operator (```*```)__ and __address-of operator (```&```)__
- anything can have an address, so reference to any object is valid. Reference modifier is not necessarily only used with pointer.
```cpp
int a = 1; 
int &ra = a; // create a reference to integer
ra++; // a is increamented since ra is just a reference of it
cout << ra << endl; // the result is the same as if output a
cout << &a << " " << &ra << endl; // both a and ra have the same address
```

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

## use of ```extern```
- __non__-```const``` case
```cpp
int abc = 1; // where it is defined
```
```cpp
extern int abc; // where it is used, in another file
cout << abc << endl;
```
- ```const``` case is different, ```extern``` is required where it is defined. Because by default ```const``` is __local__ to a file.
```cpp
extern const int abc2 = 1; // where it is defined
```
```cpp
extern const int abc2; // where it is used, in another file
cout << abc2 << endl;
```

## use of ```const```
-```const``` reference is actually __a reference to__ ```const```
- binding ```const``` to reference, actually only restricts what we can operate __through the reference___, but not the original object that this reference refers to.

## reference
the type of a reference and the object to which the reference refersmust match, with exceptions
1. we can initialize a reference to ```const``` from any expression that can be converted. we can bind __a reference to ```const```__ to a non-```const``` object, a literal, or a more general expression. This code is valid:
```cpp
double dval = 3.14; 
const int &ri = dval; 
// in fact, a temporary const int is created from the double first, then this temp was assigned to ri
```
so the above code is like
```cpp
const int temp = dval; // create a temporary const int from the double
const int &ri = temp; // bind ri to that temporary
```
however in this case, if we modify ```dval``` value, ```ri``` will not be affeceted. because ```ri``` and ```dval``` have different address. 
**Similarly for pointers, Pointer to ```const``` can be used to point to non-```const``` object**
2. 

## ```const``` pointer
- pointer is object, unlike reference which is a _name, or **alias**, to an existing object_.
```cpp
int errNumb = 0;
int *const curErr = &errNumb; // curErr will always point to errNumb
const double pi = 3.14159;
const double *const pip = &pi; // pip is a const pointer to a const object
```
```const``` pointer is not allowed to change the object it points to.

## ```constexpr``` constant expression
an expression whose value cannot change and that can be evaluated at compile time.


