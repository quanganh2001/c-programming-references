# Basic Calculator in C
```c
#include <stdio.h>
#include <math.h>
int main()
{
    double num1;
    double num2;
    printf("Enter first number: ");
    scanf("%lf", &num1);
    printf("Enter second number: ");
    scanf("%lf", &num2);

    printf("Answer: %lf", num1 + num2);
    return 0;
}
```
Output
```c
Enter first number: 1.2
Enter second number: 2.5
Answer: 3.700000
```
We use `%lf` for format specifier for `double` respectively.