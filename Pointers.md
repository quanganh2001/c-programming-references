# Pointers in C
## 1. Introduction
* What is pointer ?
	* A variable contains the address in memory of another variable.
	```c
	int var = 5;
	int* ptr = &var;
	printf("And the value")
	```
	* Operator `&`: address of a variable
	* Operator `*`: content of the variable pointed by the pointer
	* Type of data stored in the variable pointed by a pointer must be specific
	* Pointer is used only for pointing to a variable
* Syntax:
	* Type `*`pointer name;
	* Examples:
	* `int* i_pointer;`
	* `float* i_pointer;`
	* `double* i_pointer;`
## 2. Pointer Initialization
* Initialize a pointer when you declared
```c
int* i_pointer =&number;
```
* Pointer to null refers to nowhere in memory: 
```c
int* i_pointer = NULL; //i_pointer is now 0
```
## 3. Accessing a value through a pointer
* To access the value of the variable pointed by the pointer:
	* Operator: *
	* Example:
```c
int number = 10;
int* i_pointer =&number;
int result = *i_pointer + 5;
```
## 4. Passing and returning pointers to/from functions
* Function
	-	Name
	-	(Input) Parameters: Name + Datatype
	-	Return data type: `void`
* Pointers
	-	Name
	-	Type that it points to.

Function declaration: Create the file `declare_function.h`
```c
void greeting (char *a)
{
	printf("%s \n", a);
}
```
Function call: Code of the following template code:
```c
#include <stdio.h>
#include "declare_function.h"
int main()
{
    // // array declaration
    char B[] = {"How are you?"};
    greeting(B);
    return 0;
}
```
Output
```txt
How are you?
```
* Return pointers from functions:
Function declaration: create file `return_pointers.h`
```c
int* increase_elements(int arr[], int size)
{
	for (int i = 0; i < size; i++)
	{
		arr[i] = arr[i] + 1;
	}
	return arr;
}
```
Now create the .c file and code of the following template code:
```c
#include <stdio.h>
#include "return_pointers.h"
int main()
{
    // // array declaration
    int B[] = {1, 2, 3, 4, 5};
    int *p;
    p = increase_elements(B, 5);
    for (int i = 0; i < 5; i++)
    {
        printf("%d", *p+1);
    }
    printf("\n");
    return 0;
}
```
Output: 
```txt
33333
```
## 5. Void Pointers
* Can point to other variable of any type
* Often used with functions:
	* Return more than one value
	* Transfer arrays or strings
* Used in dynamic memory allocation
## 6. Pointers to Constant
* Use const keyword when declaring a pointer: value pointed by the pointer must not be changed
* Declaration:
```c
long var = 9999L;
const long* pvar = &var;
```
* Point to the value that must not be changed

```c
*pvar = 19L; //error:expression must be a modifiable value
```
* The pointer is not constant, thus we can change it.
```c
long newvar = 19L; 
pvar = &newvar;
```
## 7. Constant Pointers
* The address stored in the pointer cannot be changed
```c
long var = 9999L;
long *const pvar = &var;
```
* But the value pointed by a const pointer can be changed.
```c
int main()
{
    int var1 = 5;
    int var2 = 10;
    int* const p = &var1;//a constant pointer refering to an address all the time
    *p = 8;//posible to update the variable pointed by p
    printf("Value of p is %d, and value pointed by p is %d", p, *p);
    p = &var2;//error here since p is a constant pointer
    return 0;
}

```
## 8. Constant Pointers to Constants
* The address stored in the pointer and pointer itself cannot be changed
```c
long var = 9999L; 
const long *const pvar = &var;
```
## 9. Operation with Pointers
* Pointer arithmetic
	* Increasing
	* Decreasing
* Pointer comparisions
## 10. Pointer Arithmetic
* Four arithmetic operators: ++, --, +, -
* Incrementing a pointer:
```c
#include <stdio.h>

int main()
{
    int numbers[] = {2,4,6,8,10};
    int size = 5;
    int* p = numbers;
    for (int i =0; i<size;i++)
    {
        printf("The #%d element is %d \n", i,*p);
        p ++;//let p point to the next element.
    }
    return 0;
}
```
Output
```txt
The #0 element is 2                                                  
The #1 element is 4                                                  
The #2 element is 6                                                  
The #3 element is 8                                                  
The #4 element is 10
```
## 11. Pointer with Arrays and Strings
### 11.1. Pointer and 1D Arrays
* The 1-D array name is infact a const pointer to its first element
* Increase or reduce value of p to travel along the array elements
```c
#include <stdio.h>
int main()
{
    int A[] = {1,2,3,4,5};
    int* p = A;//p points to A[0]
    p++;//p points to A[1]
    printf("The next 3 element is %d \n", p[3]);/*p points to A[4] so p[3] now is 5*/
    A++;//error because A is a constant pointer
    return 0;
}
```
### 11.2. Pointer and String
* A pointer to char can be considered as a string
* Two arrays of char can not be assigned to each other, but two pointers to char can
```c
char *t = "This is an array of char";
char *s = t; /*equivalent to strcpy(s,t), s and t have same value and point to the same address*/
```
## 12. Manage Dynamic Memory using Pointers
### 12.1. Using Memory as You Go
* How to create an array of intergers (e.g: for students’ score) with size determined at runtime?
* --> Dynamic memory allocation: variables are stored at memory area called heap (not stack for static variables)
### 12.2. Allocate Dynamic Memory
* `malloc(size)` in `<stdlib.h>` library: standard function to allocate memory
	* Specify number of bytes you want to allocate
	* malloc() return the address of first bytes allocated
	```c
	int *ptr = (int*) malloc(10 * sizeof(int));
	```
	* If memory can not be allocated, malloc() returns NULL --> checking value returned by malloc() is a good practice
	```c
	if(ptr == NULL)
		printf("Memory can not be allocated! \n");
	```
* `calloc(num,size)` in `<stdlib.h>` library: similar to `malloc()` except it initializes num memory blocks with zero
### 12.3. Release Dynamic Memory
* You should always release memory when it is no longer used to prevent memory leaking
* Memory in stack (for normal variables) is released when the scope of variables is over
* Memory in heap is released automatically when the program ends --> sometimes too late --> better to release when you do not use it any more
* `free(pointer_to_memory)` function is the standard way to release memory
Example of using malloc() and free()
```c
#include <stdio.h>
#include <stdlib.h>

//using dynamic memory, compute the sum of n integers entered by user
int main()
{
    int n, i, *ptr, sum = 0;
    
    printf("Enter number of elements: ");
    scanf("%d", &n);
    
    ptr = (int*) malloc(n * sizeof(int)); // do not declare fixed size array anymore
    // if memory cannot be allocated
    if(ptr == NULL)
    {
        printf("Error! Memory not allocated!");
        exit(0);
    }
    
    printf("Enter elements: ");
    for (i = 0; i < n; i++)
    {
        scanf("%d", ptr + i);
        sum += *(ptr + i);
    }
    printf("Sum = %d", sum);
    // deallocating the memory
    free(ptr);
    
    return 0;
}
```
Output
```c
Enter number of elements: 5
Enter elements: 10
20
30
40
50
Sum = 150
```

```c
#include <stdio.h>
int main()
{
	int age = 30;
	printf("age's memory address: %p\n", &age);

	return 0;
}
```
Output
```c
age's memory address: 0061ff1c
````
For integer: `pGpa`
For character: `aVariables`
Example:
```c
#include <stdio.h>
int main()
{
	int age = 30;
	int * pAge = &age;
	double gpa = 3.4;
	double * pGpa = &gpa;
	char grade = 'A';
	char * aGrade = &grade;

	printf("age's memory address: %p\n", &age);

	return 0;
}
```