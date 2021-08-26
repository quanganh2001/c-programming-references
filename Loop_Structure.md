# Loop Structure in C
## 1. Definition of Loop
- A mechanism to repeat blocks of statements multiple times until some conditions are met
- Two main kinds of loops:
	- Counting loops
	- Conditional loops
## 2. Counting Loop - For Loop
- Execute a block of statements a given number of times
- Syntax:
```c
for(init; condition; increment)
{
	statements;
}
```
- *Init*: Initial iteration variable
- *Expression*: logical expression to check the iteration condition
- *Increment*: change the value of the iteration variable
Example
```c
#include <stdio.h>
int main(void)
{
    int x;
    
    for (x =1; x <=10; ++x)
    printf("\n%d", x);
        
    return 0;
}
```
Output
```c
1
2
3
4
5
6
7
8
9
10
```
- Multiple iterations
```c
for(int i = 1, j = 2 ; i<=5 ; i++, j = j+2) 
printf("\n %5d", i*j);
```
- Multiple conditions
```c
for(int i = 0,j=0; (i<10)&&(j<20); i++,j+=5) 
printf("\n %d", i);
```
## 3. Increment and Decrement Operators
- Increment operator:
	- Adds I to the variable it acts on: ++
	- Prefix: `++i`
	- Postfix: `i++`
- Decrement operator:
	- Subtract 1 to the variable it acts on: ++
	- Prefix: `--i`
	- Postfix: `i--`
## 4. Break statement
- Stop executing the code within the current loop and continue the first statement following the loop
- Example:
```c
#include <stdio.h>
int main()
{
	int x = 5;
	for (int i = 1; i<=x; i++)
	{
		if (i==3)
		break;
		
			printf("%d \n", i);
	}
	return 0;
}
```
Output
```c
1 
2 
```
```c
// 2d Array and Nested loop
#include <stdio.h>
int main()
{
	int nums[3][2] = {
					{1, 2},
					{3, 4},
					{5, 6}
					};
	printf("%d", nums[1][1]);

	return 0;
}
```
## 5. Nested loop
- The inner loop completes all ít iterations for each iteration of the outer loop
- Example:
```c
#include <stdio.h>
int main()
{
	int nums[3][2] = {
					{1, 2},
					{3, 4},
					{5, 6}
					};
	int i, j;
	for (i = 0; i < 3; i++)
	{
		for (j = 0; j < 2; j++)
		{
			printf("%d,", nums[i][j]);
		}
		printf("\n");
	}

	return 0;
}
```
Output
```c
1,2,
3,4,
5,6,
```
## 6. While loop
- Repeating a set of statements until a condition is met
- Check the condition before doing statements
- Syntax
```c
while(expression)
{
	statements;
}
Next statements;
```
- Example
```c
// Print numbers from 1 to 5
#include <stdio.h>
int main()
{
    int i = 1;
    
    while (i <= 5)
    {
        printf("%d\n", i);
        ++i;
    }
    return 0;
}
```
Output
```c
1
2
3
4
5
```
## 7. Do...while loop
- The condition is tested at the end of the loop
- Syntax
```c
do
{
	statements
}
while (expression)
```
- Output
```c
Enter a number: 1.3                                                  
Enter a number: 0                                                    
Sum = 1.30
```
## 8. Continue statements
The **continue** statement in C programming works somewhat like the **break** statement. Instead of forcing termination, it forces the next iteration of the loop to take place, skipping any code in between.
For the **for** loop, **continue** statement causes the conditional test and increment portions of the loop to execute. For the **while** and **do...while** loops, **continue** statement causes the program control to pass to the conditional tests.
Syntax: `continue;`
Example
```c
#include <stdio.h>
int main () {

   /* local variable definition */
   int a = 10;

   /* do loop execution */
   do {
   
      if( a == 15) {
         /* skip the iteration */
         a = a + 1;
         continue;
      }
		
      printf("value of a: %d\n", a);
      a++;
     
   } while( a < 20 );
 
   return 0;
}
```
When the above code is compiled and executed, it produces the following result:
```c
value of a: 10
value of a: 11
value of a: 12
value of a: 13
value of a: 14
value of a: 16
value of a: 17
value of a: 18
value of a: 19
```
## 9. Goto statement
- To escape nested loops completely
- Example:
```c
// Program to calculate the sum and average of positive numbers
// If the user enters a negative number, the sum and average are displayed.

#include <stdio.h>

int main() {

   const int maxInput = 100;
   int i;
   double number, average, sum = 0.0;

   for (i = 1; i <= maxInput; ++i) {
      printf("%d. Enter a number: ", i);
      scanf("%lf", &number);
      
      // go to jump if the user enters a negative number
      if (number < 0.0) {
         goto jump;
      }
      sum += number;
   }

jump:
   average = sum / (i - 1);
   printf("Sum = %.2f\n", sum);
   printf("Average = %.2f", average);

   return 0;
```
Output
```c
1\. Enter a number: 3
2. Enter a number: 4.3
3. Enter a number: 9.3
4. Enter a number: -2.9
Sum = 16.60
Average = 5.53
```
## 10. For loop
```c
#include <stdio.h>
int main()
{
	int luckyNumbers[] = {4, 8, 15, 16, 23, 42};

	int i;
	for (int i = 0; i < 6; i++)
	{
		printf("%d\n", luckyNumbers[i]);
	}

	return 0;
}
```
Output
```c
4
8
15
16
23
42
```