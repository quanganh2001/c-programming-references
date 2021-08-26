# Arrays in C
# I. String
## 1. What is an Array?
- A data structure storing a fixed-size sequential collection of elements of the same type
## 2. Declating Arrays
- Array declaration:
	- Data type of items
	- Variable name
	- Array size: number of items
- 1D Arrays:
`int A[5];`
- 2D Arrays:
`int A[3][5];`
## 3. Initializing Arrays
- Initializing with array size
`int A[5] = {1, 2, 3, 4, 5};`
Five is the numbers of elements matches array size
- If array size is omitted, an array just big enough to hold the initializations created.
`int A[] = {1, 2, 3, 4, 5};`
## 4. Accessing Array Elements
- To access an element, you should define:
	- Array name
	- The location of the element in the array
- One-dimensional arrays
```c
// Array declatation
#include <stdio.h>
int main()
{
    int A[5] = {1, 2, 3, 4, 5};
    
    for (int i = 0; i < 5; i++) {
        printf("Element %d in the array is %d \n", i, A[i]);
    }
    
    return 0;
}
```
Output
```c
Element 0 in the array is 1          
Element 1 in the array is 2          
Element 2 in the array is 3          
Element 3 in the array is 4          
Element 4 in the array is 5
```
- 2-dimensional arrays
```c
#include <stdio.h>
int main()
{
	int A[2][5] = {{1, 2, 3, 4, 5}, {6, 7, 8, 9, 10}};
	for (int i = 0; i < 2; i++)
	{
		for (int j = 0; j < 5; j++)
		{
			printf("%d \t", A[i][j]);
		}
		printf("\n");
	}
	return 0;
}
```
Output
```c
1       2       3       4       5
6       7       8       9       10
```
If you input `int A[1][3]`, the output is `1       2       3`
However, you input `int A[0][1]` the ouput is nothing.
## 5. Arrays and Address
- Array name is a pointer to the first element of the array (detailed in the next session).
- 1-D array:
`int A[5];` 
- 2-D array:
`int A[2][3];`
- Print out address of array elements:
```c
#include <stdio.h>
int main()
{
	int A[2][3] = {
					{1, 2, 3},
					{4, 5, 6},
	};
	for (int j = 0; j < 2; j++)
	{
		for (int k = 0; k < 3; k++)
		{
			printf("%p \t", &A[j][k]);
		}
		printf("\n");
	}
	return 0;
}
```
Output
```c
0061ff00        0061ff04        0061ff08
0061ff0c        0061ff10        0061ff14
```
## 6. Passing Arrays to Functions
- As an unknown-size array
	- 1-D array: `void myfunction(int a[], int size)`
	- 2-D array: `void myfunction (int a[][3], int row`
- As a fixed size away
	- 1-D array: `void myfunction (int a(5))`
	- 2-D array: `void myfunction (int a(5))`
- As a pointer
	- 1-D array: `void myfunction (int *a)`
	- 2-D array: `void myfunction (int **a)`

Demo
```c
#include <stdio.h>
#include <stdlib.h>
int main()
{
    int luckyNumbers[] = {4, 8, 15, 16, 23, 42};
    printf("%d", luckyNumbers[0]);

    return 0;
}
```
Output: `4`
Similarity, if you input `luckyNumbes[1]`, the result is 8.
# II. Array
## 1. String concept
- A string
	- Sequence of characters
	- Is stored in array of type clear
![String in C](https://cdn.programiz.com/sites/tutorial2program/files/c-string-initialization.jpg)
## 2. Array of strings
```c
#include <stdio.h>
int main(void)
{
	char subject_name[5][30] = {"Linear Algebra", "Calculus", "Physics", "Computer Architecture", "Basic Programming"};

	int size = 5;
	for (int i = 0; i < size; i++)
	{
		printf("The subject %d is %s \n", i+1, subject_name[i]);
	}
	return 0;
}
```
Output
```c
The subject 1 is Linear Algebra
The subject 2 is Calculus
The subject 3 is Physics
The subject 4 is Computer Architecture
The subject 5 is Basic Programming
```
## 3. Standard Functions for Strings
* Declared in "string.h"
* Common functions

| Function | Uses |
| --------- | ----- |
| `strlen()` | computes string's length |
| `strcpy()` | copies a string to another |
| `strcat()` | Concatenates (joins) two strings |
| `strcmp()` | compares two strings |
| `strlwr()` | converts string to lowercase |
| `strupr()` | converts string to uppercase |

