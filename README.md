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

**ASCII Code:**

| **ASCII**值 | **控制字符** | **ASCII**值 | **字符**  | **ASCII**值 | **字符** | **ASCII**值 | **字符** |
|------------|----------|------------|---------|------------|--------|------------|--------|
| 0          | NUT      | 32         | (space) | 64         | @      | 96         | 、      |
| 1          | SOH      | 33         | !       | 65         | A      | 97         | a      |
| 2          | STX      | 34         | "       | 66         | B      | 98         | b      |
| 3          | ETX      | 35         | #       | 67         | C      | 99         | c      |
| 4          | EOT      | 36         | $       | 68         | D      | 100        | d      |
| 5          | ENQ      | 37         | %       | 69         | E      | 101        | e      |
| 6          | ACK      | 38         | &       | 70         | F      | 102        | f      |
| 7          | BEL      | 39         | ,       | 71         | G      | 103        | g      |
| 8          | BS       | 40         | (       | 72         | H      | 104        | h      |
| 9          | HT       | 41         | )       | 73         | I      | 105        | i      |
| 10         | LF       | 42         | *       | 74         | J      | 106        | j      |
| 11         | VT       | 43         | +       | 75         | K      | 107        | k      |
| 12         | FF       | 44         | ,       | 76         | L      | 108        | l      |
| 13         | CR       | 45         | -       | 77         | M      | 109        | m      |
| 14         | SO       | 46         | .       | 78         | N      | 110        | n      |
| 15         | SI       | 47         | /       | 79         | O      | 111        | o      |
| 16         | DLE      | 48         | 0       | 80         | P      | 112        | p      |
| 17         | DCI      | 49         | 1       | 81         | Q      | 113        | q      |
| 18         | DC2      | 50         | 2       | 82         | R      | 114        | r      |
| 19         | DC3      | 51         | 3       | 83         | S      | 115        | s      |
| 20         | DC4      | 52         | 4       | 84         | T      | 116        | t      |
| 21         | NAK      | 53         | 5       | 85         | U      | 117        | u      |
| 22         | SYN      | 54         | 6       | 86         | V      | 118        | v      |
| 23         | TB       | 55         | 7       | 87         | W      | 119        | w      |
| 24         | CAN      | 56         | 8       | 88         | X      | 120        | x      |
| 25         | EM       | 57         | 9       | 89         | Y      | 121        | y      |
| 26         | SUB      | 58         | :       | 90         | Z      | 122        | z      |
| 27         | ESC      | 59         | ;       | 91         | [      | 123        | {      |
| 28         | FS       | 60         | <       | 92         | /      | 124        | \      |       |
| 29         | GS       | 61         | =       | 93         | ]      | 125        | }      |
| 30         | RS       | 62         | >       | 94         | ^      | 126        | `      |
| 31         | US       | 63         | ?       | 95         | _      | 127        | DEL    |

The ASCII code is roughly composed of the following two parts:

- **ASCII Non-Printing Control Characters:** Numbers 0-31 on the ASCII table are assigned to control characters used to control some peripherals like printers.
- **ASCII Printing Characters:** Numbers 32-126 are assigned to characters that can be found on the keyboard and appear when viewing or printing the document.

### 2.5 Escape Character
**Effect:** Used to represent some ASCII characters that cannot be displayed.


| **Escape Character** | **Meaning**                                                                  | **ASCII**（decimal）  |
|----------------------|------------------------------------------------------------------------------|---------------------|
| \a                   | alert                                                                        | 007                 |
| \b                   | Backspace (BS), move the current position to the previous column             | 008                 |
| \f                   | Form feed (FF), move the current position to the beginning of the next page  | 012                 |
| **\n**               | Line feed (LF), move the current position to the beginning of the next line  | **010**             |
| \r                   | Carriage return (CR), move the current position to the beginning of the line | 013                 |
| **\t**               | Horizontal tab (HT) (jump to the next TAB position                           | **009**             |
| \v                   | Vertical Tabulation (VT)                                                     | 011                 |
| **\\\\**             | Represents a backslash character "\"                                         | **092**             |
| \'                   | Represents a single quote character                                          | 039                 |
| \"                   | Represents a double quote character                                          | 034                 |
| \?                   | Represents a question mark                                                   | 063                 |
| \0                   | Number 0                                                                     | 000                 |
| \ddd                 | Octal escape character, d range 0~7                                          | 3-digit octal       |
| \xhh                 | Hexadecimal escape character, h range 0~9, a~f, A~F                          | 3-digit hexadecimal |

**Example**

```c++
int main() {
    
   cout << "\\" << endl;
   cout << "\tHello" << endl;
   cout << "\n" << endl;
   
   system("pause");
   
   return 0;
}
```