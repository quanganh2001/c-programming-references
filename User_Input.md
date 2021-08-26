# User input in C
## Example of content
[1. C Output](#output)

[2. Interger Output](#integer_output)

[3. float and double Output](#float_and_double)

[4. Print characters](#characters)

[5. Integer Input/Output](#integer_input)

[6. Double Input/Output](#double_input)

### 1. C Output <a name ="output"></a>
```c
#include <stdio.h>    
int main()
{ 
    // Displays the string inside quotations
    printf("C Programming");
    return 0;
}
```
Output
```C Programming```
### 2. Integer Output <a name="integer_output"></a>
```c
#include <stdio.h>
int main()
{
    int num = 5;
    printf("Number = %d", num);
    return 0;
}
```
Output
`Number = 5`
### 3. float and double Output <a name="float_and_double"></a>
```c
#include <stdio.h>
int main()
{
    float number1 = 13.5;
    double number2 = 12.4;

    printf("number1 = %f\n", number1);
    printf("number2 = %lf", number2);
    return 0;
}
```
Output
```c
number1 = 13.500000
number2 = 12.400000
```
To print `float`, we use `%f` format specifier. Similarly, we use `%lf` to print `double` values.
### 4. Print characters <a name="characters"></a>
```c
#include <stdio.h>
int main()
{
    char chr = 'a';    
    printf("character = %c", chr);  
    return 0;
} 
```
Output
`character = a`
To print `char`, we use `%c` format specifier.
### 5. Integer Input/Output <a name="integer_input"></a>
```c
#include<stdio.h>
int main() {
    int a, b;
    printf("Enter number a: ");
    scanf("%d", &a);
    printf("Enter number b: ");
    scanf("%d", &b);
    printf("a + b = %d", a + b);
    return 0;
}
```
Output
```c
Enter number a: 6
Enter number b: 7
a + b = 13
```
### 6. Double Input/Output

###  <a name="double_input"></a>

```c
#include<stdio.h>
int main()
{
    double gpa;
    printf("Enter your GPA: ");
    scanf("%lf", &gpa);
    printf("Your GPA is %.2f", gpa);
    return 0;
}
```
Output
```c
Enter your GPA: 3.1
Your GPA is 3.10
```
