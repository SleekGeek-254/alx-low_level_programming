Tasks
0. A library is not a luxury but one of the necessities of life
mandatory
Score: 0.0% (Checks completed: 0.0%)
Create the static library libmy.a containing all the functions listed below:

int _putchar(char c);
int _islower(int c);
int _isalpha(int c);
int _abs(int n);
int _isupper(int c);
int _isdigit(int c);
int _strlen(char *s);
void _puts(char *s);
char *_strcpy(char *dest, char *src);
int _atoi(char *s);
char *_strcat(char *dest, char *src);
char *_strncat(char *dest, char *src, int n);
char *_strncpy(char *dest, char *src, int n);
int _strcmp(char *s1, char *s2);
char *_memset(char *s, char b, unsigned int n);
char *_memcpy(char *dest, char *src, unsigned int n);
char *_strchr(char *s, char c);
unsigned int _strspn(char *s, char *accept);
char *_strpbrk(char *s, char *accept);
char *_strstr(char *haystack, char *needle);
If you haven’t coded all of the above functions create empty ones with the right prototype.
Don’t forget to push your main.h file to your repository. It should at least contain all the prototypes of the above functions.

julien@ubuntu:~/0x09. Static Librairies$ ar -t libmy.a 
0-isupper.o
0-memset.o
0-strcat.o
1-isdigit.o
1-memcpy.o
1-strncat.o
100-atoi.o
2-strchr.o
2-strlen.o
2-strncpy.o
3-islower.o
3-puts.o
3-strcmp.o
3-strspn.o
4-isalpha.o
4-strpbrk.o
5-strstr.o
6-abs.o
9-strcpy.o
_putchar.o
julien@ubuntu:~/0x09. Static Librairies$ nm libmy.a 

0-isupper.o:
0000000000000000 T _isupper

0-memset.o:
0000000000000000 T _memset

0-strcat.o:
0000000000000000 T _strcat

1-isdigit.o:
0000000000000000 T _isdigit

1-memcpy.o:
0000000000000000 T _memcpy

1-strncat.o:
0000000000000000 T _strncat

100-atoi.o:
0000000000000000 T _atoi

2-strchr.o:
0000000000000000 T _strchr

2-strlen.o:
0000000000000000 T _strlen

2-strncpy.o:
0000000000000000 T _strncpy

3-islower.o:
0000000000000000 T _islower

3-puts.o:
                 U _putchar
0000000000000000 T _puts

3-strcmp.o:
0000000000000000 T _strcmp

3-strspn.o:
0000000000000000 T _strspn

4-isalpha.o:
0000000000000000 T _isalpha

4-strpbrk.o:
0000000000000000 T _strpbrk

5-strstr.o:
0000000000000000 T _strstr

6-abs.o:
0000000000000000 T _abs

9-strcpy.o:
0000000000000000 T _strcpy

_putchar.o:
0000000000000000 T _putchar
                 U write
julien@ubuntu:~/0x09. Static Librairies$ cat main.c 
#include "main.h"

int main(void)
{
    _puts("\"At the end of the day, my goal was to be the best hacker\"\n\t- Kevin Mitnick");
    return (0);
}
julien@ubuntu:~/0x09. Static Librairies$ gcc -std=gnu89 main.c -L. -lmy -o quote
julien@ubuntu:~/0x09. Static Librairies$ ./quote 
"At the end of the day, my goal was to be the best hacker"
    - Kevin Mitnick
julien@ubuntu:~/0x09. Static Librairies$ 
Repo:

GitHub repository: alx-low_level_programming
Directory: 0x09-static_libraries
File: libmy.a, main.h
   
1. Without libraries what have we? We have no past and no future
mandatory
Score: 0.0% (Checks completed: 0.0%)
Create a script called create_static_lib.sh that creates a static library called liball.a from all the .c files that are in the current directory.

julien@ubuntu:~/0x09. Static Librairies$ ls *.c
0-isupper.c  0-strcat.c  1-isdigit.c  1-strncat.c  2-strlen.c   3-islower.c  3-strcmp.c  4-isalpha.c  5-strstr.c  9-strcpy.c  _putchar.c
0-memset.c   100-atoi.c  1-memcpy.c   2-strchr.c   2-strncpy.c  3-puts.c     3-strspn.c  4-strpbrk.c  6-abs.c
julien@ubuntu:~/0x09. Static Librairies$ ./create_static_lib.sh 
julien@ubuntu:~/0x09. Static Librairies$ ls *.a
liball.a
julien@ubuntu:~/0x09. Static Librairies$ ar -t liball.a
0-isupper.o
0-memset.o
0-strcat.o
100-atoi.o
1-isdigit.o
1-memcpy.o
1-strncat.o
2-strchr.o
2-strlen.o
2-strncpy.o
3-islower.o
3-puts.o
3-strcmp.o
3-strspn.o
4-isalpha.o
4-strpbrk.o
5-strstr.o
6-abs.o
9-strcpy.o
_putchar.o
julien@ubuntu:~/0x09. Static Librairies$ 
Repo:

GitHub repository: alx-low_level_programming
Directory: 0x09-static_libraries
File: create_static_lib.sh


Here's an overview of what you'll need to do:

Create a header file called main.h that includes the prototypes for all of the functions you'll be implementing.

Write the code for each of the functions listed in the task. You should create a separate .c file for each function. Be sure to follow the guidelines listed in the task, such as using the Betty style and not using global variables.

Once you've implemented all of the necessary functions, you'll need to compile them into a static library using the ar command. This will create a file called libmy.a that contains all of your functions.

To ensure that your library was created correctly, you can use the nm command to list the symbols in the library. This should show you a list of all of the functions that you implemented.

Finally, you'll need to test your library to make sure that it works as expected. You can do this by writing a main.c file that calls some of the functions you implemented and verifies that they produce the correct output.

Here's a more detailed breakdown of each step:

Step 1: Create main.h

Your main.h file should include the prototypes for all of the functions you'll be implementing. For example, you might have something like this:

scss
Copy code
#ifndef MAIN_H
#define MAIN_H

int _putchar(char c);
int _islower(int c);
int _isalpha(int c);
int _abs(int n);
int _isupper(int c);
int _isdigit(int c);
int _strlen(char *s);
void _puts(char *s);
char *_strcpy(char *dest, char *src);
int _atoi(char *s);
char *_strcat(char *dest, char *src);
char *_strncat(char *dest, char *src, int n);
char *_strncpy(char *dest, char *src, int n);
int _strcmp(char *s1, char *s2);
char *_memset(char *s, char b, unsigned int n);
char *_memcpy(char *dest, char *src, unsigned int n);
char *_strchr(char *s, char c);
unsigned int _strspn(char *s, char *accept);
char *_strpbrk(char *s, char *accept);
char *_strstr(char *haystack, char *needle);

#endif /* MAIN_H */
This file should be saved in the root directory of your project.

Step 2: Implement the functions

Next, you'll need to implement all of the functions listed in the task. You should create a separate .c file for each function. For example, you might have a file called _putchar.c that looks like this:

vbnet
Copy code
#include "main.h"

/**
 * _putchar - writes the character c to stdout
 * @c: The character to print
 *
 * Return: On success 1.
 * On error, -1 is returned, and errno is set appropriately.
 */
int _putchar(char c)
{
    return (write(1, &c, 1));
}
Be sure to follow the guidelines listed in the task, such as using the Betty style and not using global variables. You should also make sure that each function has the correct return type and takes the correct arguments.

Step 3: Compile the functions into a static library

Once you've implemented all of the necessary functions, you'll need to compile them into a static library using the `




Trevor Chiwo
Once you've implemented all of the necessary functions, you'll need to compile them into a static library using the `...


2 / 2

Compiling functions into a static library involves the following steps:

First, you need to create object files for each of the functions. An object file is a compiled binary file that contains the compiled code for a single function. You can create object files using a compiler like gcc.

Once you have object files for all the functions, you can use the ar command (short for "archiver") to create a static library. A static library is simply a collection of object files that are packaged together into a single file. To create a static library using ar, you would use a command like this:

Copy code
ar rcs libmylibrary.a myfunction1.o myfunction2.o myfunction3.o
This command creates a static library called libmylibrary.a, and includes the object files for myfunction1, myfunction2, and myfunction3.

The r option tells ar to replace any existing files in the archive with the new files. The c option tells ar to create a new archive if one doesn't already exist. And the s option tells ar to create an index of the symbols (i.e. function names) in the library, which can speed up linking later on.

Once you've created your static library, you can link it into your main program using the -l option with the linker (usually gcc). For example:

bash
Copy code
gcc -o myprogram myprogram.c -L/path/to/mylibrary -lmylibrary
This command links myprogram.c with the static library libmylibrary.a, which is located in the directory /path/to/mylibrary. The -l option tells the linker to look for a library with the given name (mylibrary), and the -L option tells it where to look for the library file.

Note that you'll also need to include any header files for your library functions in your main program's source code, using #include directives.




Trevor Chiwo
how do i "First, you need to create object files for each of the functions. An object file is a compiled binary file that contains the compiled code for a single function. You can create object files using a compiler like gcc."

To create object files for each of the functions, you can follow these steps:

Open a terminal or command prompt.

Navigate to the directory where your source code files are located using the cd command.

Run the following command to compile each of your source code files into an object file:

r
Copy code
gcc -c myfile.c -o myfile.o
Replace myfile.c with the name of your source code file and myfile.o with the name you want to give to the object file.

You'll need to repeat this command for each of your source code files, replacing the file names as appropriate.

Note that the -c flag tells gcc to compile the code without linking it, which produces an object file.

For example, if you have two source code files named add.c and subtract.c, you would run the following commands to compile them into object files:

csharp
Copy code
gcc -c add.c -o add.o
gcc -c subtract.c -o subtract.o
After running the commands, you should see new .o files in your directory. These are your object files, which contain the compiled code for each of your functions.

You can now use these object files to create a static library using the ar command as described in the previous steps.




Trevor Chiwo
what is 0-isupper.c

0-isupper.c is likely a file containing a function implementation for checking if a character is an uppercase letter. The 0 at the beginning of the filename is likely used as a naming convention to indicate that it is the first function in a series of related functions. The isupper function is typically used to check if a given character is an uppercase letter in the current locale, and it is usually defined in the ctype.h header file. The implementation of isupper may vary depending on the specific platform or compiler being used, but it typically involves checking the ASCII or Unicode value of the character against a range of values that correspond to uppercase letters.




Trevor Chiwo
wait is this like a standard? or how does it mean all that 

Yes, there are coding standards that developers can follow to write code that is consistent and easy to read. The use of prefixes like "is" and "get" for function names is a common convention used in many programming languages. For example, in C, it is common to prefix functions that return a boolean value with "is" to indicate that they are checking a condition, and functions that return a value with "get" to indicate that they are returning some data.

Similarly, the convention of using 0 and non-zero return values to indicate success or failure is also a widely used standard in programming. By following these conventions, developers can write code that is more easily understood and maintained by others, and can help to reduce bugs and errors in their code.




Trevor Chiwo
so what do all those functions do?

Sure, here's a brief explanation of each function:

isupper: This function takes a character as input and returns true (non-zero) if the character is an uppercase letter, and false (zero) otherwise.
toupper: This function takes a character as input and returns the uppercase equivalent of the character, if it is a lowercase letter. If the input character is already uppercase or not a letter at all, the function returns the input character unchanged.
isalpha: This function takes a character as input and returns true (non-zero) if the character is an alphabetic letter (either uppercase or lowercase), and false (zero) otherwise.
isdigit: This function takes a character as input and returns true (non-zero) if the character is a digit (0-9), and false (zero) otherwise.
isalnum: This function takes a character as input and returns true (non-zero) if the character is either a letter or a digit, and false (zero) otherwise.
strlen: This function takes a null-terminated string as input and returns the number of characters in the string, not including the null terminator.
strcat: This function takes two null-terminated strings as input and concatenates (joins) them together, with the second string being appended to the end of the first. The resulting string is also null-terminated.
puts: This function takes a null-terminated string as input and prints it to the standard output (typically the console). The string is followed by a newline character.
memset: This function takes a block of memory, a value, and the number of bytes to set to that value, and sets each byte to the given value. It's often used to initialize arrays or structs to a particular value.
memcpy: This function takes two blocks of memory and the number of bytes to copy, and copies the specified number of bytes from the source block to the destination block.
I hope this helps! Let me know if you have any more questions.





This script is a Bash script that compiles and creates a static library from the source code files with a .c extension in the current directory.

Here's a breakdown of the commands in the script:

#!/bin/bash specifies that the script should be interpreted using the Bash shell.
gcc -Wall -pedantic -Werror -Wextra -c *.c compiles all the C source code files (*.c) in the current directory into object files with the same name but with a .o extension. The -Wall, -pedantic, -Werror, and -Wextra options are flags that enable additional compiler warnings and errors to help catch potential issues with the code.
ar -rc liball.a *.o creates a static library named liball.a from all the object files (*.o) in the current directory. The -r option tells the ar command to replace any existing files in the archive, and -c specifies that a new archive should be created if it doesn't exist.
ranlib liball.a adds an index to the static library file to speed up linking with the library.
Overall, this script automates the process of compiling and creating a static library from C source code files, making it easier to distribute and link the code in other programs.




Trevor Chiwo
how do i use it if i have save it as create_static_lib.sh

Assuming you have saved the script as create_static_lib.sh and you want to use it to compile the necessary object files and create the static library, you can follow these steps:

Open your terminal and navigate to the directory where you have saved the script and the source code files.

Make the script executable using the following command:

bash
Copy code
chmod +x create_static_lib.sh
Run the script using the following command:

bash
Copy code
./create_static_lib.sh
The script will compile all the source code files ending with .c and create object files with the same name but ending with .o. It will then use ar command to create a static library called liball.a by combining all the object files. Finally, it will use ranlib command to generate an index for the static library.

Once the script completes, you should see the liball.a file in the same directory along with the source code files.

You can now use this liball.a file to link with your main program and use the functions defined in the source code files.




Trevor Chiwo
_putchar.c: In function ‘_putchar’:
_putchar.c:12:13: error: implicit declaration of function ‘write’ [-Werror=implicit-function-declaration]
   12 |     return (write(1, &c, 1));
      |             ^~~~~
cc1: all warnings being treated as errors

This error occurs because the write() function is not declared in the file where _putchar() function is defined. To fix this error, you need to include the header file unistd.h which contains the declaration for the write() function.

To do this, add the following line at the top of the _putchar.c file:

c
Copy code
#include <unistd.h>
This will include the necessary header file and resolve the error related to the write() function.
