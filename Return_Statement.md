# Return Statement in C
```c
#include <stdio.h>
#include <stdlib.h>

double cube(double num) {
	double result = num * num * num;
	return result;
}

int main()
{
	printf("Answer: %.2f", cube(7.0));

	return 0;
}
```
Or
```c
#include <stdio.h>
#include <stdlib.h>

double cube(double num);

int main()
{
	printf("Answer: %.2f", cube(7.0));

	return 0;
}
double cube(double num) {
	return num * num * num;
}
```
The result is 343.00