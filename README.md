# Cpp-Tutorial

# C++ Basic Programming
## 1. Head First C++

### 1.1 Comment
**Effect:** Add some comments and explanations in the code to make it easier for oneself or other programmers to read the code.

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
>Notice:
> When C++ creates a variable, it must give the variable an initial value, otherwise an error will be reported.

### 1.3 Constant
**Effect:** Used to record unchangeable data in the program.
There are two ways to define constants in C++:
1. **#define macroConstant:** #define constantName constantValue
   - Usually defined above the source file, representing a constant
2. **const modifiedVariable:** const dataType constantName = constantValue
    - Usually, the keyword const is added before the variable definition to modify the variable as a constant and cannot be modified.
**Example:**
```c++
//1、宏常量
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
| ---------- | ------------ | ---------------- | ----------- | -------- |
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