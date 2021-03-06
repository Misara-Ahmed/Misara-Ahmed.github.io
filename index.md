<font size="6">First: "&" Operator </font>

-The "&" symbol is used as an operator in C++.\
-It is used in 2 different places, one as a bitwise and operator and one as a pointer address of operator.

**_<font size="4">1-Bitwise AND: </font>_**

The bitwise AND operator (&) compares each bit of the first operand to that bit of the second operand.
If both bits are 1, the bit is set to 1. Otherwise, the bit is set to 0.\
Both operands to the bitwise AND operator must be of integral types.\
_Example_
```
#include <iostream> 
using namespace std;
int main() {  
unsigned short a = 0x5555;      // pattern 0101  
unsigned short b = 0xAAAA;      // pattern 1010

cout << hex << ( a & b ) << endl;
}
```

_Output_\
`0`

**_<font size="4">2-Address Of operator: </font>_**

C++ provides two-pointer operators, which are Address of Operator (&) and Indirection Operator (*).\
A pointer is a variable that contains the address of another variable or you can say that a variable that contains the address of another variable is said to "point to" the other variable. A variable can be any data type including an object, structure or again pointer itself.\
The address of Operator (&), and it is the complement of *. It is a unary operator that returns the address of the variable(r-value) specified by its operand.\
_Example_
```
#include <iostream>
using namespace std;

int main () {
int  var;
int  *ptr;
int  val;

var = 3000;

// take the address of var
ptr = &var;

// take the value available at ptr
val = *ptr;
cout << "Value of var :" << var << endl;
cout << "Value of ptr :" << ptr << endl;
cout << "Value of val :" << val << endl;

return 0;
}
```
_Output_
```
Value of var :3000
Value of ptr :0xbff64494
Value of val :3000
```


<font size="6">Second: "const" Keyword </font>

-the _**const**_ keyword specifies that the object or variable is not modifiable.

**_<font size="4">Syntax:</font>_**
```
const declaration ;
member-function const ;
```

**_<font size="4"> Const values:</font>_**\
The **_const_** keyword specifies that a variable's value is constant and tells the compiler to prevent the programmer from modifying it.
```
int main() {
   const int i = 5;
   i = 10;   // C3892
   i++;   // C2105
}
```
In C++, you can use the **_const_** keyword instead of the #define preprocessor directive to define constant values. Values defined with const are subject to type checking, and can be used in place of constant expressions.\
In C++, you can specify the size of an array with a **_const_** variable as follows:
```
const int maxarray = 255;
char store_char[maxarray];
```
In C++, constant values default to internal linkage, which allows them to appear in header files.\
The **_const_** keyword can also be used in pointer declarations.
```
int main() {
   char *mybuf = 0, *yourbuf;
   char *const aptr = mybuf;
   *aptr = 'a';   // OK
   aptr = yourbuf;   // C3892
}
```
A pointer to a variable declared as **_const_** can be assigned only to a pointer that is also declared as **_const_**.
```
#include <stdio.h>
int main() {
   const char *mybuf = "test";
   char *yourbuf = "test2";
   printf_s("%s\n", mybuf);

   const char *bptr = mybuf;   // Pointer to constant data
   printf_s("%s\n", bptr);

   // *bptr = 'a';   // Error
}
```
You can use pointers to constant data as function parameters to prevent the function from modifying a parameter passed through a pointer.

For objects that are declared as **_const_**, you can only call constant member functions. This ensures that the constant object is never modified.
```
birthday.getMonth();    // Okay
birthday.setMonth( 4 ); // Error
```
You can call either constant or nonconstant member functions for a nonconstant object. You can also overload a member function using the const keyword; this allows a different version of the function to be called for constant and nonconstant objects.

You cannot declare constructors or destructors with the **_const_** keyword.