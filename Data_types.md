# Data types in C
## 1. Basic Types:
- `int`
- `float`
- `double`
- `char`
- `void`
## 2. Example
```c
int average;
float gpa_2020;
```
1. Integer
`int age = 40;`
2. Double
`double gpa = 3.6;`
3. Char
`char grade = 'A';`
`char phrase[] = "Giraffe Academy";`
## 3. Basic Data Types
### 3.1. Integer variables
- Declaration: `int name; // comments`
- An integer is any whole number without a decimal point 
### 3.2. Print out integer variables
- Using `printf()` function (from studio library)
- `%d`: integer conversion specification
- Syntax: *printf(format. expression1, expression2,...);*
- Example: 
```c
int temp = 10;
printf("twice is %d is %d \n", temp, 2*temp);
```
Output
```c
twice 10 is 20
```
### 3.3. Ranges of Integer Variables
[See at tutorial spoint](https://www.tutorialspoint.com/cprogramming/c_data_types.htm)
### 3.4. Integer Constants in Decimal
- int constant: `int i =100;`
- Long const: `long i = 100l;`
- Unsigned int constant: `unsigned i = 100u;`
- Unsigned long constant: `unsigned i = 100ul;` or `unsigned i = 100lu;`
### 3.5.  Integer Constants in Other Numbering System
- Octal int constant:
```c
#include <stdio.h>
int main()
{
    int temp = 023;
    printf("temp = %d \n", temp);
    
    return 0;
}
```
Output
`temp = 19`
- Hexa int constant
```c
#include <stdio.h>
int main()
{
    int temp = 0x23;
    printf("temp = %d \n", temp);
    
    return 0;
}
```
Output
```c
temp = 35;
```
- Binary constant
```c
#include <stdio.h>
int main()
{
    int temp = 0b0101;
    printf("temp = %d \n", temp);
    
    return 0;
}
```
Output
`temp = 5;`
### 3.6. Floating Point Values
- Floating-point numbers:
	- Using decimal point
	- 5.0 is floating-point number
	- 5 is an integer number
[Values float in C see more them.](https://imgur.com/a/d0FGVS7)
### 3.7. Declaration
- `float temp = 2.5f;`
- `double temp1 = 12e2;`
- `long double temp2 = 1.89L;`
### 3.8. Print out a floating-point number
- Syntax: *%[width].[precision][modifier]f*
	- *Width: minimum number of characters to be printed*
	- *Precision: number of digit to be printed after decimal point*
	- *Modifier: add L for printing out long double value*
- Example
```c
float temp = 21.12345;
printf("temp = %3.5f \n", temp);
```
*Result:* `temp = 21.12345`
### 3.9. Character Variables
- Single byte: one character
- keyword: *char*
- Example:
```c
char a = 'A'; // By a character in a pair of single quotes
char b = 65; // By a number in the ASCII table
```
### 3.10. Print out Characters
- Syntax: `%c`
- Example:
```c
#include <stdio.h>
int main()
{
    char temp = 65;
    printf("temp = %c \n", temp);
    
    return 0;
}
```
Output: `temp = A`
### 3.11. Void Types
- No value
- Use cases:
	- Funtion return as void
	- Function has void argument
	- Pointer to void
### 3.12. Complex Number types
- Form: a + bi
- Include header file: <complex.h>
### 3.13. Constants
- A variable with fixed value `const float Pi = 3.14159f;//a fixed variable definition so this occupies memory`
- Macro is an alternative way to write fixed conventional values using `#define`:
`#define PI 3.14159f;//the pre-processor replaces PI with 3.14159f before compilation`
## 4. Notes
- Choose correct data types:
	- Appropriate range of values
	- Correct type