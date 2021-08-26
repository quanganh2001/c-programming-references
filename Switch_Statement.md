# Switch statement
▪ Enables you to choose one course of action from a set of possible actions 
▪ Syntax:
```c
switch(integer_expression)
{
	case constant_expression_1:
		statement_1;
		break;
		...
	case constant_expression_n:
		staement_n;
		break;
	default:
		statements;
}
```
# Example
```c
#include <stdio.h>

int main()
{
    int month;
    printf("Please Enter the Month Number 1 to 12 (Consider 1 = Jan, and 12 = Dec): ");
    scanf("%d", &month);
    
    switch(month)
    {
        case 1:
        case 3:
        case 5:
        case 7:
        case 8:
        case 10:
        case 12:
            printf("\\nThis month has 31 Days.");
            break;
            
        case 4:
        case 6:
        case 9:
        case 11:
            printf("\\nThis month has 30 Days.");
            break;
        
        case 2:
            printf("\\nThis month has either 28 or 29 Days.");
            break;
            
        default:
            printf("\\nPlease enter Valid Number between 1 to 12");
    }
    return 0;
}
```
Output
```
Please Enter the Month Number 1 to 12 (Consider 1 = Jan, and 12 = Dec): 6
This month has 30 Days.
```