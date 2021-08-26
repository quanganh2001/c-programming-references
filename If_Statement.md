# If_else statement C
## 1. Syntax
```c
if (test expression) 
{
   // code
}
```
## 2. How if statement works?
The `if` statement evaluates the test expression inside the parenthesis `()`.
- If the test expression is evaluated to true, statements inside the body of `if` are executed.
- If the test expression is evaluated to false, statements inside the body of `if` are not executed.
Example
```c
// Program to display a number if it is negative

#include <stdio.h>
int main() {
    int number;

    printf("Enter an integer: ");
    scanf("%d", &number);

    // true if number is less than 0
    if (number < 0) {
        printf("You entered %d.\n", number);
    }

    printf("The if statement is easy.");

    return 0;
}
```
**Output 1**

Enter an integer: -2
You entered -2.
The if statement is easy.

When the user enters -2, the test expression `number<0` is evaluated to true. Hence, You entered -2 is displayed on the screen.

**Output 2**

Enter an integer: 5
The if statement is easy.

When the user enters 5, the test expression `number<0` is evaluated to false and the statement inside the body of `if` is not executed

---

## 3. C if...else Statement

The `if` statement may have an optional `else` block. The syntax of the `if..else` statement is:

```c
if (test expression) {
    // run code if test expression is true
}
else {
    // run code if test expression is false
}
```

---

### 3.1 How if...else statement works?

If the test expression is evaluated to true,

-   statements inside the body of `if` are executed.
-   statements inside the body of `else` are skipped from execution.

If the test expression is evaluated to false,

-   statements inside the body of `else` are executed
-   statements inside the body of `if` are skipped from execution.

![How if...else statement works in C programming?](https://cdn.programiz.com/sites/tutorial2program/files/how-if-else-works-c-programming.jpg "Working of if...else statement")

Working of if...else Statement

---

### 3.2 Example 2: if...else statement

```c
// Check whether an integer is odd or even

#include <stdio.h>
int main() {
    int number;
    printf("Enter an integer: ");
    scanf("%d", &number);

    // True if the remainder is 0
    if  (number%2 == 0) {
        printf("%d is an even integer.",number);
    }
    else {
        printf("%d is an odd integer.",number);
    }

    return 0;
}
```

**Output**

Enter an integer: 7
7 is an odd integer.

When the user enters 7, the test expression `number%2==0` is evaluated to false. Hence, the statement inside the body of `else` is executed.

---

## 4. C if...else Ladder

The `if...else` statement executes two different codes depending upon whether the test expression is true or false. Sometimes, a choice has to be made from more than 2 possibilities.

The if...else ladder allows you to check between multiple test expressions and execute different statements.

---

### 4.1 Syntax of if...else Ladder

```c
if (test expression1) {
   // statement(s)
}
else if(test expression2) {
   // statement(s)
}
else if (test expression3) {
   // statement(s)
}
.
.
else {
   // statement(s)
}
```

---

### 4.2. Example 3: C if...else Ladder

```c
// Program to relate two integers using =, > or < symbol

#include <stdio.h>
int main() {
    int number1, number2;
    printf("Enter two integers: ");
    scanf("%d %d", &number1, &number2);

    //checks if the two integers are equal.
    if(number1 == number2) {
        printf("Result: %d = %d",number1,number2);
    }

    //checks if number1 is greater than number2.
    else if (number1 > number2) {
        printf("Result: %d > %d", number1, number2);
    }

    //checks if both test expressions are false
    else {
        printf("Result: %d < %d",number1, number2);
    }

    return 0;
}
```

**Output**

Enter two integers: 12
23
Result: 12 < 23

---

## 5. Nested if...else

It is possible to include an `if...else` statement inside the body of another `if...else` statement.

---

### 5.1 Example 4: Nested if...else

This program given below relates two integers using either `<`, `>` and `=` similar to the `if...else` ladder's example. However, we will use a nested `if...else` statement to solve this problem.

```c
#include <stdio.h>
int main() {
    int number1, number2;
    printf("Enter two integers: ");
    scanf("%d %d", &number1, &number2);

    if (number1 >= number2) {
      if (number1 == number2) {
        printf("Result: %d = %d",number1,number2);
      }
      else {
        printf("Result: %d > %d", number1, number2);
      }
    }
    else {
        printf("Result: %d < %d",number1, number2);
    }

    return 0;
}
```

---

If the body of an `if...else` statement has only one statement, you do not need to use brackets `{}`.

For example, this code

```c
if (a > b) {
    print("Hello");
}
print("Hi");
```

is equivalent to

```c
if (a > b)
    print("Hello");
print("Hi");
```