# Constant in C
A constant is a value or variable that can't be changed in the program, for example: 10, 20, 'a', 3.4, "c programming" etc.
There are different types of constants in C programming.
## List of Constants in C
| Constant                        | Example          |
|---------------------------------|------------------|
| Decimal Constant                | 10, 20, 450      |
| Real or Floating-point Constant | 10.2, 12.5       |
| Octal Constant                  | 021, 033, 046    |
| Hexadecimal Constant            | 0x2a, 0x7b, 0xaa |
| Character Constant              | 'a', 'b', 'x'    |
### 2 Ways to define constant in C
There are two ways to define constant in C programming
	[1. C Const keyword](#Constant)
	[2. C define preprocesor](#Define)
	
### 1. C Const keyword
<a name="Constant"></a>

The const keyword is used to define constant in C programming. Example:
`const float PI =3.14;`
Now, the value of PI variable can't be changed.
```c
#include<stdio.h>    
int main(){    
    const float PI=3.14;    
    printf("The value of PI is: %f",PI);    
    return 0;  
}     
```
Output
`The value of PI is 3.140000`
### C define preprocesor 
<a name="Define"></a>

Visit here for: [define preprocessor directive](https://www.javatpoint.com/c-preprocessor-define)
