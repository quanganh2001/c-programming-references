# Variables in C
## 1. What is a variable ?
- A named area of computer memory 
- Objective: to store values 
-  Scope of validity: where its content can be accessed and manipulated
## 2. Variable Name
- Includes: letters and digits
- First character must be a letter
- The underscore "______" counts as a letter but don't use it as the first character
- Uppercase and lowercase are distinct
- Must not be a keywords 
## 3. Variable Declarations
- A variable must be declared before being used
- Declaration statement defines:
	- Name
	- Type
	- Description (if any)
- Example
`float average_gpa_2020_bi11; // average gpe of Bi11 Students` 
## 4. Variable Initialization
- After declaring a variable, initial value should be set to avoid junk value.
- Syntax: Type name = value;
- Example:
`int z = 50;` or
```c
int z;
z = 30;
```
## 5. Variable Assignment
- Change a variable by assignment operation "="
- Syntax: name = value;
- Example:
```c
int z;
z = 30;
z = 90;
z = -19;
```
## 6. Example Variables
```c
#include <stdio.h>
#include <stdlib.h>
int main()
{
	 char characterName[] = "Tom";
	 int characterAge = 67;

	 printf("There once was a man named %s\n", characterName);
	 printf("He was %d years old.\n", characterAge);

	 characterAge = 30;
	 printf("He really liked the name %s\n", characterName);
	 printf("But did not like being %d.\n", characterAge);
	 return 0;
}
```
