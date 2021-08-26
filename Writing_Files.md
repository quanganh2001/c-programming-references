# Writing Files in C
## 1. Syntax

```c
#include <stdio.h>
int main()
{
	FILE * fpointer = fopen("employees.txt", "w");
	
	fclose(fpointer);
	return 0;
}
```
Now run the code, as you can see, it will creates files `employees.txt`
Now add code
```c
fprintf(fpointer, "Jim, Salesman\nPam, Receptionist\nOscar, Accounting");
```
run the code, you can see txt is overwrite files:
```txt
Jim, Salesman
Pam, Receptionist
Oscar, Accounting
```
Let's change the code and change into `"a"`
```c
fprintf(fpointer, "\nKelly, Customer Service");
```

```c
#include <stdio.h>
int main()
{
	FILE * fpointer = fopen("employees.txt", "a");

	fprintf(fpointer, "\nKelly, Customer Service");
	
	fclose(fpointer);
	return 0;
}
```
Run the code, you can see the txt files is now add lines
```txt
Jim, Salesman
Pam, Receptionist
Oscar, Accounting
Kelly, Customer Service
```