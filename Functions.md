# Functions in C
## Types of Function
There are two types of function in C programming:
  -   [Standard library functions](https://www.programiz.com/c-programming/library-function "C Library Functions")
 -   [User-defined functions](https://www.programiz.com/c-programming/c-user-defined-functions "C user-defined functions")
### Standard library functions
The standard library functions are built-in functions in C programming.

These functions are defined in header files. For example,

-   The `printf()` is a standard library function to send formatted output to the screen (display output on the screen). This function is defined in the `stdio.h` header file.  
    Hence, to use the `printf()`function, we need to include the `stdio.h` header file using `#include <stdio.h>`.
-   The `sqrt()` function calculates the square root of a number. The function is defined in the `math.h` header file.  

You can visit [standard library functions in C programming](https://www.programiz.com/c-programming/library-function "C Library Functions") to learn more.
### User-defined function
You can also create functions as per your need. Such functions created by the user are known as user-defined functions.
Example:
```c
#include <stdio.h>
#include <stdlib.h>
int main()
{
	sayHi();
	return 0;
}

void sayHi () {
	printf("Hello user! \n");
}
```
When the compiler encounters `sayHi();`, control of the program jumps to
`void sayHi()_`
Output
`Hello user!`