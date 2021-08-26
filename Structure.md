<center>Data Structure in C</center>

# I. Structure
## 1. Why Structure
- How to keep different data aspects of items together?
- Examples:
	- Track students of Basic Programming class with their attributes:
		- Student ID
		- Name
		- Mark
	- Manage properties of each book:
		- Title
		- Author
		- Subject
		- Book ID
		- Publishing year
## 2. Structures
- A user-defined data type
- Combine a limited number of data elements into a unified data unit (corresponding to a record in general)
- Data elements are in arbitrary types
- Example:
	A record about a book in a library has properties:
		- Title
		- Author
		- Subject
		- Book ID
		- Publishing year
	--> a structure named Book
## 3. Declaring structure
- Syntax:
	- Declaring a struct
	```c
	struct Book
	{
		char*t title;
		char* author;
		char* subject;
		char* ID;
		int year;
	};
	```
	- Declaring a struct variable
	```c
	struct Book fiction1;
	```
## 4. Initializing Structures
```c
struct Book fiction1=
{
	"Harry Potter", "JKRowling", "fiction", "Fi123", 2005
};
```
## 5. Accessing Structures
- Accessing a member of a struct: "." operator
```txt
variable_name.attribute
```

```c
struct Book fiction1;
fiction1.title = "Harry Potter";
fiction1.author = "JWRowling";
fiction1.subject = "fiction";
fiction1.ID = "Fi123";
fiction1.year = 2005;

printf("The book fiction1 information: \n");
printf("Title: %s \n", fiction1.title);
printf("Author: %s \n", fiction1.author);
printf("Book ID: %s \n", fiction1.ID);
printf("Publishing year: %d \n", fiction1.year);
```
Example
```c
// Example for structure in C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
struct Book {
    char* title;
    char* author;
    char* subject;
    char* ID;
    int year;
};
int main()
{
    struct Book fiction1 = {"Harry Potter", "JWRowling", "fiction", "Fi123", 2005};
    struct Book book1; /* Declare book1 of type book */
    book1.title = "C Programming";
    book1.year = 6495407;
    printf("The book fiction1 information: \n");
    printf("Title: %s \n", fiction1.title);
    printf("Author: %s \n", fiction1.author);
    printf("Book ID: %s \n", fiction1.ID);
    printf("Publishing year: %d \n", fiction1.year);
    return 0;
}
```
Output
```txt
The book fiction1 information: 
Title: Harry Potter 
Author: JWRowling 
Book ID: Fi123 
Publishing year: 2005
```
## 6. typedef
- How to declare 5 books has the same struct?
```c
struct Book fiction1;
struct Book fiction2;
struct Book fiction3;
struct Book fiction4;
struct Book fiction5;
```
- `typedef`: give a shorter name for the struct
```c
typedef struct book bk;
bk fiction1;
bk fiction2;
...
```
- Another way to use typedef:
```c
typedef struct
{
	char* title;
	char* author:
	char* subject;
	char* ID;
	int year;
} Book;

Book fiction2;
Book fiction3;
Book fiction4;
```
## 7. Size of a struct
```c
Book ficiton1=
{
"Harry Potter", "JWRowling", "fiction", "Fi123", 2005
};

printf("Size of book struct is %lu \n", sizeof(Book));
```
**Notes**
- Struct variables cannot be compared
- Members of struct variables can be compared
## 8. Array of structs
- Declaration:
```c
Book fiction[5];
```
- Accessing to members of struct elements
```c
Book fiction[5];
fiction[1].title = "The Little Prince";
ficiton[1].author = "Antoine de Saint-Exupéry";
```
## 9. Pointers to Structures
- A pointer to a structure:
	- contains address of the structure
	```c
	Book* p = &fiction1;
	```
	- Can be used to access to member of struct:
	```c
	printf("Title of the book is %s \n", (*p).title);
	```
	Or
	```c
	printf("Title of the book is %s \n", p->title);
	```
## 10. Operations with structures
- Structures member can be used as any other variables
- Assignment:
```c
Book fiction2 = fiction1;
```
- "&" operator:
```c
&fiction1 // return address of the struct variable fiction1
```
- Cannot add, compare or perform any other operations with struct variables
--> Write your own functions
## 11. Pointer to Struct
- Consider Struct as other built-in datatypes when declare a pointer to a struct variable
```c
struct Book fiction1 = {"Harry Potter", "JWRowling", "fiction", "Fi123", 2005};
struct Book* book_ptr = &fiction1;
```
- And access member of Struct via the pointer:
```c
printf("Book 1 title: %s\n", (*book_ptr).title);
```
- Or a more intuitive way:
```c
printf("Book 1 title: %s\n", book_ptr->title);
```
## 12. Dynamic Memory Allocation for Structures
```c
struct Book* tech1_ptr = (struct Book*)malloc(sizeof(struct Book));
tech1_ptr->title = "Programming in C (4th Edition) ";
tech1_ptr->author = "Stephen Kochan";
tech1_ptr->subject = "Basic Programming";
tech1_ptr->ID = "ProgC4";
tech1_ptr->year = 2014;

...

free(tech1_ptr);
```
## 13. Passing a Struct to a Function
- Like other datatype, Struct can play as a parameter of a function
```c
void print_book(struct Book aBook) {
	printf( "Book title: %s\n", aBook.title);
	printf( "Book author: %s\n", aBook.author);
	printf( "Book subject: %s\n", aBook.subject);
	printf( "Book book_id: %s\n", aBook.ID);
}
```
- Recall: the parameter is passed by value -> the function cannot change the original variable
## 14. Returning a struct from a function
```c
struct Book enter_book(){
	struct Book aBook;
	printf("Enter the book, title and year: ");
	aBook.title = malloc(100);
	scanf("%s %d", aBook.title, &aBook.year);
	return aBook;
}
```
# II. File Output and Output
## 1. Data and Permanent Storage
- Data kept in variables is stored in RAM and disappears once the program stops running
- -> A program needs to save data for later use -> it writes the data to a file in hard disk
- The data can then be read from the file at a later time
## 2. Filename
- Files on disk are identified by their filename
- Filenames must be unique in a folder
- Filename extensions are short sequences of characters at the end of a filename and after the last dot character
- Filename extensions usually indicate the type of data stored in the file
## 3. Text File vs. Binary File
| Text                                                       | Binary                                      |
|------------------------------------------------------------|---------------------------------------------|
| Data encoded as text using scheme such as ASCII or Unicode | Data in pure format (not yet encoded)       |
| Can be viewed by text reader applications (Notepad)        | Cannot be viewed by text reader application |
## 4. Procedure to Work with a File
- Step 1: Open the file
	- To create a connection between the program and the file
	- Opening an output file -> create a file on a disk, allow program to write on it.
	- Opening an input file -> allow program to read data from the file
- Step 2: Process the file
	- To write (or read) the output (or input) file
- Step 3: Close the file
	- To disconnect the file from the program
## 5. File IO Stream
- In C all input and output is done with streams
- Streams is nothing but a sequence of bytes of data
- A sequence of bytes flowing into the program is called input stream
- A sequence of bytes flowing out of the program is called output stream
## 6. Opening-File modes
| Mode | Description                                                                                                                                                                      |
|------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| r    | Opens an existing text file for reading purpose.                                                                                                                                 |
| w    | Opens a text file for writing. If it does not exist, then a new  file is created. Here your program will start writing content  from the beginning of the file                   |
| a    | Opens a text file for writing in appending mode. If it does  not exist, then a new file is created. Here your program will  start appending content in the existing file content |
| r+   | Opens a text file for both reading and writing.                                                                                                                                  |
| w+   | Opens a text file for both reading and writing. It first  truncates the file to zero length if it exists, otherwise creates  a file if it does not exist.                        |
| a+   | Opens a text file for both reading and writing. It creates  the file if it does not exist. The reading will start from the  beginning but writing can only be appended.          |

## 7. Reading a Text File
```c
#include <stdio.h>
#include <stdlib.h>
int main()
{
	char ch;
	FILE *fp = fopen("content_to_be_read.txt", "r"); // read mode
	if (fp == NULL)
	{
		printf("Error while opening the file.\n");
		exit(EXIT_FAILURE);
	}

	printf("The contents: \n");

	while((ch = fgetc(fp)) != EOF)
	printf("%c", ch);

	fclose(fp);
	return 0;
}
```
If you don't have txt file, it has the result
```txt
Error while opening the file.
```
If you created `content_to_be_read.txt` and input, the resuit is
```txt
Hello everybody!
```
## 8. Writing a Text File
```c
#include <stdio.h>
#include <stdlib.h>
int main()
{
	FILE *out_file = fopen("out.txt", "w"); // write only
	fprintf(out_file, "this is the content written out in 2021 \n");
	return 0;
}
```
Now run the code, it will create `out.txt` with content
```txt
this is the content written out in 2021 
```