# Numbers in C
Table of content
1. [Calculation](#Calculation)
2. [Power](#Power)
3. [Sqrt](#Sqrt)
4. [Ceil](#Ceil)
5. [Floor](#Floor)

## Calculation
```
#include <stdio.h>
int main()
{
    printf("%f \n", 8.9);
    printf("%f \n", 5.0 * 4.5);
    printf("%f \n", 5 + 4.5);
    printf("%f \n", 5 / 4.0);
    return 0;
}
```
Result:
`8.900000 
22.500000 
9.500000 
1.250000`
## Power
```
#include <stdio.h>
int main()
{
    printf("%f", pow(2, 3));
    return 0;
}
```
The result is 8
## Sqrt
Syntax: `sqrt()`
```
#include <stdio.h>
int main()
{
    printf("%f", sqrt(36));
    return 0;
}
```
The result is 6
## Ceil
In the C Programming Language, the **ceil function** returns the smallest integer that is greater than or equal to _x_ (ie: rounds up the nearest integer).
Example:
```
#include <stdio.h>
int main()
{
    printf("%f", ceil(36.356));
    return 0;
}
```
The result is 37
## Floor
In the C Programming Language, the **floor function** returns the largest integer that is smaller than or equal to _x_ (ie: rounds downs the nearest integer).
syntax: `floor()`
Example:
```
#include <stdio.h>
int main()
{
    printf("%f", floor(36.656));
    return 0;
}
```
The result is 36

	