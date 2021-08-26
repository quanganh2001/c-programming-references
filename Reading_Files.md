# Reading Files in C
Syntax: `r`

Example:
```c
#include <stdio.h>
int main()
{
	FILE * fpointer = fopen("employees.txt", "r");
	
	fclose(fpointer);
	return 0;
}
```
As you can see, `employees.txt` is does not change.
```c
#include <stdio.h>
int main()
{
	char line[255];
	FILE * fpointer = fopen("employees.txt", "r");

	fgets(line, 255, fpointer);
	
	fclose(fpointer);
	return 0;
}
```
Output
```c
Jim, Salesman
```
Let add `fgets(line, 255, fpointer);` one more time, the output is:
```c
Pam, Receptionist
```