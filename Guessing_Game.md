# Guessing Game in C
```c
#include <stdio.h>
int main()
{
	int secretNumber = 5;
	int guess;

	while(guess != secretNumber) {
		printf("Enter a number: ");
		scanf("%d", &guess);
	}
	printf("You Win!");

	return 0;
}
```
Output
```c
Enter a number: 2
Enter a number: 7
Enter a number: 5
You Win!
```
As you can see, you input 2 or 7 is not result but you input the number is 5 then into the result is You Win!
Now we add `guessCount`, `guessLimit` and `outOfGuess`
```c
int guessCount = 0;
int guessLimit = 3;
int outOfGuess = 0;
```
Template
```c
#include <stdio.h>
int main()
{
	int secretNumber = 5;
	int guess;
	int guessCount = 0;
	int guessLimit = 3;
	int outOfGuess = 0;

	while(guess != secretNumber && outOfGuess == 0) {
		if(guessCount < guessLimit) {
			printf("Enter a number: ");
			scanf("%d", &guess);
			guessCount++;
		} else {
			outOfGuess = 1;
		}
	}
	if (outOfGuess == 1)
	{
		printf("Out of guesses");
	} else {
		printf("You Win!");
	}

	return 0;
}
```
Output (if you input three times but doesn't result)
```c
Enter a number: 2
Enter a number: 2
Enter a number: 2
Out of guesses
```
But if you input the number is 5, the output is:
```c
Enter a number: 2
Enter a number: 1
Enter a number: 5
You Win!
```