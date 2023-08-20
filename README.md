# Cpp-Tutorial

# C++ Basic Programming

## 1. Head First C++

### 1.1 Comment

**Effect:** Add some comments and explanations in the code to make it easier for oneself or other programmers to read
the code.

**Two Formats:**

1. **Single Line Comment:**
    - Usually placed above a line of code, or at the end of a statement, to describe the line of code
2. **Multiline Comment:**
    - Usually placed above a piece of code, **give an overall description of the code**

> Notice:
> When the compiler compiles the code, it will ignore the content of the comment.

### 1.2 Variable

**Effect:** Give a specified memory space a name to facilitate the operation of this memory
**Grammar:** dataType variableName = initialValue;
**Example:**

```c++
#include<iostream>
using namespace std;

int main() {
    int a = 10;

    cout << "a = " << a << endl;
    
    return 0;
}
```

> Notice:
> When C++ creates a variable, it must give the variable an initial value, otherwise an error will be reported.

### 1.3 Constant

**Effect:** Used to record unchangeable data in the program.
There are two ways to define constants in C++:

1. **#define macroConstant:** #define constantName constantValue
    - Usually defined above the source file, representing a constant
2. **const modifiedVariable:** const dataType constantName = constantValue
    - Usually, the keyword const is added before the variable definition to modify the variable as a constant and cannot
      be modified.
      **Example:**

```c++
//1、Macro constant
#define day 7

int main() {

   cout << "There are " << day << " in a week" << endl;
   //day = 8;  //error: Macro constants cannot be modified
   
   //2、const modifies this variable
   const int month = 12;
   cout << "There are " << month << " months a year" << endl;
   //month = 24; //error: Constants cannot be modified

return 0;
}
```

### 1.4 Keywords

**Effect:** Keywords are pre-reserved words (identifiers) in C++
> Notice: When defining variables or constants, do not use keywords.

**The following are C++ keywords:**

| asm        | do           | if               | return      | typedef  |
|------------|--------------|------------------|-------------|----------|
| auto       | double       | inline           | short       | typeid   |
| bool       | dynamic_cast | int              | signed      | typename |
| break      | else         | long             | sizeof      | union    |
| case       | enum         | mutable          | static      | unsigned |
| catch      | explicit     | namespace        | static_cast | using    |
| char       | export       | new              | struct      | virtual  |
| class      | extern       | operator         | switch      | void     |
| const      | false        | private          | template    | volatile |
| const_cast | float        | protected        | this        | wchar_t  |
| continue   | for          | public           | throw       | while    |
| default    | friend       | register         | true        |          |
| delete     | goto         | reinterpret_cast | try         |          |

### 1.5 Identifier Naming Rules

**Effect:** C++ has its own set of rules when naming identifiers (variables, constants).

* Identifiers cannot be keywords
* Identifiers can only consist of letters, numbers, and underscores
* The first character must be a letter or underscore
* Letters in identifiers are case-sensitive

## 2. Data Type

C++ requires that when creating a variable or constant, the corresponding data type must be specified, otherwise memory
cannot be allocated to the variable.

### 2.1 Integer

**Effect:** The integer variable represents the data of integer type.

There are several ways to represent integer types in C++, **the difference is that the memory space occupied is
different**:

| **Data Type**                      | **Occupied Space**                                                        | Range of Values  |
|-------------------------------|-------------------------------------------------------------|------------------|
| short (short integer)         | 2 bytes                                                     | (-2^15 ~ 2^15-1) |
| int (integer)                 | 4 bytes                                                     | (-2^31 ~ 2^31-1) |
| long (long integer)           | 4 bytes in Windows, 4 bytes(32 bits), 8 bytes(64 bits) in Linux | (-2^31 ~ 2^31-1) |
| long long (long long integer) | 8 bytes                                                     | (-2^63 ~ 2^63-1) |


### 2.2 keyword sizeof

**Effect:** Use the sizeof keyword to calculate the memory size occupied by the data type.
**Grammar** sizeof(dataType/variable)
**Example:**

```c++
int main() {

   cout << "short: " << sizeof(short) << endl;
   
   cout << "int: " << sizeof(int) << endl;
   
   cout << "long: " << sizeof(long) << endl;
   
   cout << "long long: " << sizeof(long long) << endl;
   
   return 0;
}
```
> The Summary of Integer: 
> short < int <= long <= long long

### 2.3 Real (Floating Point)
**Effect:** Used for decimal.

Floating-point variables are divided into two types:
1. Single precision float
2. double precision

The difference between the float and double is that the range of significant numbers expressed is different:

| **Data Type** | **Occupied Space** | **Significant Digit Range** |
|---------------|--------------------|-----------------------------|
| float         | 4 bytes            | 7 Significant Digits        |
| double        | 8 bytes            | 15 to 16 Significant Digits |

**Example:**

```c++
int main() {
    float f1 = 3.14f;
    double d1 = 3.14;
   
    cout << f1 << endl;
    cout << d1<< endl;
   
    cout << "float  sizeof = " << sizeof(f1) << endl;
    cout << "double sizeof = " << sizeof(d1) << endl;
   
    // Scientific notation
    float f2 = 3e2; // 3 * 10 ^ 2 
    cout << "f2 = " << f2 << endl;
   
    float f3 = 3e-2;  // 3 * 0.1 ^ 2
    cout << "f3 = " << f3 << endl;
   
    system("pause");
   
    return 0;
}
```


### 2.4 Character Type
**Effect:** Character variables are used to display a single character

**Grammar** `char ch = 'a';`
> Notice:
> 
> 1. Character variables in C and C++ only occupy 1 byte.
> 2. A character variable does not store the character itself in the memory, but puts the corresponding ASCII code into the storage unit.

**Example:**

```c++
int main() {
    char ch = 'a';
    cout << ch << endl;
    cout << sizeof(char) << endl;
   
    //ch = "abcde"; //Error,double quotes are not allowed
    //ch = 'abcde'; //Error, Only one character can be quoted within single quotes
   
    cout << (int)ch << endl;  // View the ASCII code corresponding to the character a
    ch = 97; // Directly use ASCII to assign values character variables
    cout << ch << endl;
   
    system("pause");
   
    return 0;
}
```