# C-practice

Info gathered from:
https://www.w3schools.com/cpp/cpp_classes.asp

## Table of contents
1. [ Variables. ](#var)
2. [ Operators. ](#operator)
3. [ Strings. ](#string)
4. [ Switch. ](#switch)
5. [ Loops. ](#loops)
6. [ Continue. ](#continue)
7. [ Structures. ](#struct)
8. [ References. ](#ref)
9. [ Functions. ](#func)
10. [ Recursion. ](#recur)


<a name="var"></a>
## Variables

### C++ Variables
```
char	: (1 byte) single characters, such as 'a' or 'B'. Surrounded by single quotes
string	: (1 byte) text, such as "Hello World". Surrounded by double quotes
bool	: (1 byte) values with two states: true or false
int	: (2 or 4 byte)Integers, both positive and negative 123 & -123
float	: (4 byte)Float, both positive and negative 123.2 & -123.2
double	: (8 byte)Float, both positive and negative 123.2 & -123.2
```
```
It's possible to create multiply empty variables at the same time.
int x,y,z;
```
<a name="operator"></a>
## Operators

### Arithmetic Operators
```
+	: Addition
-	: Subtraction
*	: Multiplication
/	: Division
%	: Modulus
++	: Increment
--	: Decrement
```
### Assigment Operators
```
=	: Same as -> x = 5
+=  : Same as -> x = x + 3
-=  : Same as -> x = x - 3
*=  : Same as -> x = x * 3
/=  : Same as -> x = x / 3
%=  : Same as -> x = x % 3
&=  : Same as -> x = x & 3
|=  : Same as -> x = x | 3
^=  : Same as -> x = x ^ 3
>>= : Same as -> x = x >> 3
<<= : Same as -> x = x << 3
```

### Comparison Operators
```
==	: Equal to
!=  : Not equal
>   : Greater than
<   : Less than
>=  : Greater than or equal to
<=  : Less than or equal to
```

### Logical Operators
```
&&	: Logical and
||	: Logical or
!	: Logical not
```
<a name="string"></a>
## Strings

```
In order to use strings in the code, import string with:

#include <string>
```

### Short Hand if...Else(Ternary operator)
```
variable = (condition) ? expressionTrue : expressionFalse;
```
```
// Instead of this:

int time = 20;
if (time < 18) {
  cout << "Good day.";
} else {
  cout << "Good evening.";
}
```

```
// One can write this:

int time = 20;
string result = (time < 18) ? "Good day." : "Good evening.";
cout << result;
```
<a name="switch"></a>
## Switch

```
The switch expression is evaluated once.
The value of the expression is compared with the values of each case.
If there is a match, the associated block of code is executed.
The break and default keywords are optional.
The default keyword specifies some code to run if there is no case match.
```

```
switch(expression) {
  case x:
    // code block
    break;
	
  case y:
    // code block
    break;
	
  default:
    // code block
}
```

<a name="loops"></a>
## Loops

### While Loop

```
int i = 0;
while (i < 5) {
  cout << i << "\n";
  i++;
}
```

### Do While Loop

```
/*The example below uses a do/while loop.
The loop will always be executed at least once,
even if the condition is false,
because the code block is executed before the condition is tested:*/

int i = 0;
do {
  cout << i << "\n";
  i++;
}
while (i < 5);
```

### For Loop
```
for (int i = 0; i < 5; i++) {
  cout << i << "\n";
}
```

### For Each Loop
```
for (type variableName : arrayName) {
  // code block to be executed
}
```
```
// Example:

int myNumbers[5] = {10, 20, 30, 40, 50};
for (int i : myNumbers) {
  cout << i << "\n";
}
```
<a name="continue"></a>
## C++ Continue
```
The continue statement breaks one iteration (in the loop),
if a specified condition occurs,
and continues with the next iteration in the loop.
```
```
This example skips the value of 4:
for (int i = 0; i < 10; i++) {
  if (i == 4) {
    continue;
  }
  cout << i << "\n";
}
```
<a name="struct"></a>
## Structures (Struct)

### Single struct
```
struct {             // Structure declaration
  int myNum;         // Member (int variable)
  string myString;   // Member (string variable)
} myStructure;       // Structure variable
```
```
// Create a structure variable called myStructure
struct {
  int myNum;
  string myString;
} myStructure;

// Assign values to members of myStructure
myStructure.myNum = 1;
myStructure.myString = "Hello World!";

// Print members of myStructure
cout << myStructure.myNum << "\n";
cout << myStructure.myString << "\n";
```
### Multiple structs
```
struct {
  int myNum;
  string myString;
} myStruct1, myStruct2, myStruct3; 
// Multiple structure variables separated with commas
```

### Named Structures
```
struct myDataType { // This structure is named "myDataType"
  int myNum;
  string myString;
};
```
<a name="ref"></a>
## References

### Creating References
```
string food = "Pizza";  // food variable
string &meal = food;    // reference to food

cout << food << "\n";  // Outputs Pizza
cout << meal << "\n";  // Outputs Pizza
```

### Creating Pointers
```
A pointer is a variable that stores the memory address as its value.

string food = "Pizza";  // A food variable of type string
string* ptr = &food;    /* A pointer variable,
			   with the name ptr,
			   that stores the address of food */

// Output the value of food (Pizza)
cout << food << "\n";

// Output the memory address of food (0x6dfed4)
cout << &food << "\n";

// Output the memory address of food with the pointer (0x6dfed4)
cout << ptr << "\n";
```
### Dereference
```
/* In order to retrieve variable data from a pointer instead of the address,
do the following: */

string food = "Pizza";  // Variable declaration
string* ptr = &food;    // Pointer declaration

// Reference: Output the memory address of food with the pointer (0x6dfed4)
cout << ptr << "\n";

// Dereference: Output the value of food with the pointer (Pizza)
cout << *ptr << "\n";
```

## Functions 
```
void myFunction(string fname) {
  cout << fname << " Refsnes\n";
}

int main() {
  myFunction("Liam");
  return 0;
}

// Liam Refsnes
```

### Default parameters in a Function
```
void myFunction(string country = "Norway") {
  cout << country << "\n";
}

int main() {
  myFunction("Sweden");
  myFunction();
  return 0;
}

// Sweden
// Norway
```

### Pass By Reference
```
void swapNums(int &x, int &y) {
  int z = x;
  x = y;
  y = z;
}

int main() {
  int firstNum = 10;
  int secondNum = 20;

  cout << "Before swap: " << "\n";
  cout << firstNum << secondNum << "\n";

  // Call the function, which will change the values of firstNum and secondNum
  swapNums(firstNum, secondNum);

  cout << "After swap: " << "\n";
  cout << firstNum << secondNum << "\n";

  return 0;
}
```
<a name="func"></a>
### Function Overloading
```
int myFunction(int x)
float myFunction(float x)
double myFunction(double x, double y)
```

```
int plusFunc(int x, int y) {
  return x + y;
}

double plusFunc(double x, double y) {
  return x + y;
}

int main() {
  int myNum1 = plusFunc(8, 5);
  double myNum2 = plusFunc(4.3, 6.26);
  cout << "Int: " << myNum1 << "\n";
  cout << "Double: " << myNum2;
  return 0;
}
```
<a name="recur"></a>
### Recursion
Recursion is the technique of making a function call itself. This technique provides a way to break complicated problems down into simple problems which are easier to solve. <br>

Adding two numbers together is easy to do, but adding a range of numbers is more complicated. In the following example, recursion is used to add a range of numbers together by breaking it down into the simple task of adding two numbers:
```
// Example

int sum(int k) {
  if (k > 0) {
    return k + sum(k - 1);
  } else {
    return 0;
  }
}

int main() {
  int result = sum(10);
  cout << result;
  return 0;
}

/* Example Explained:
When the sum() function is called,
it adds parameter k to the sum of all numbers smaller than k and returns the result.
When k becomes 0, the function just returns 0.
When running, the program follows these steps:

10 + sum(9)
10 + ( 9 + sum(8) )
10 + ( 9 + ( 8 + sum(7) ) )
...
10 + 9 + 8 + 7 + 6 + 5 + 4 + 3 + 2 + 1 + sum(0)
10 + 9 + 8 + 7 + 6 + 5 + 4 + 3 + 2 + 1 + 0
Since the function does not call itself when k is 0,
the program stops there and returns the result. */
```
