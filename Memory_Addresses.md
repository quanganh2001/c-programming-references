# Memory Addresses in C
Syntax: `%p`
Example:
```c
#include <stdio.h>
int main()
{
	int age = 30;
	double gpa = 3.4;
	char grade = 'A';

	printf("%p", &age);

	return 0;
}
```
Output
`0061ff10`
Example for age, gpa and grade:
```c
#include <stdio.h>
int main()
{
	int age = 30;
	double gpa = 3.4;
	char grade = 'A';

	printf("age: %p\ngpa: %p\ngrade: %p", &age, &gpa, &grade);

	return 0;
}
```
Output:
```c
age: 0061ff1c
gpa: 0061ff10
grade: 0061ff0f
```