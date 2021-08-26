# Deferencing Pointers in C
Example
```c
#include <stdio.h>
int main()
{
	int age = 30;
	int * pAge = &age;

	printf("%p", pAge);

	return 0;
}
```
Output
```c
0061ff18
```
If you change to `%d` or`*&age` or `*&*&`, the output is 30