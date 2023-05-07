# Basic Concepts in C Programming
***
The first point of interest in C programming is that every program starts with the same basic syntax.
***

"Hello world" is the first program most programmers every write. An example implementaton of hello world in C is shown below.

```C
#include <stdio.h>

int main() {

  printf("Hello world\n");
  
  return 0;
}
```
Before learning how to write code, you need to understand the components of a C program. Let's analyse hello world piece-by-piece.  

***
First let's look at ``` #include <stdio.h> ``` this is a pre-processor directive. In terms of functionality, include statements are simple, they are used to include the contents of a specific library. For example, the implementation of ``` printf() ``` is 
located in stdio.h, and we cannot use the function without including the contents of the stdio.h file first.

***

The next statement is ``` int main() {} ```, this is a *function definition*. In this statement we are declaring the "main" function. 
A main function is required in every C program because execution of every C program begins and ends in main().  

It is important to note that all C functions have the same basic syntax ``` returnType functionName(input) { code } ``` .  

In the example, ```int``` is the type of data the funciton returns, or "outputs." ```main``` is the name of the function. ```()``` is where any inputs to the function are defined. ```{}``` is where the actual code is written.

The main function in the hello world program is a function that takes no input and returns an integer. The code for printing the text is written between the ```{}``` after the function name.  


***

Regarding the body of the code, ``` printf("Hello world!\n") ```, printf is a function that prints data to the screen. In this case, printf is printing the string literal "Hello world!", followed by ```\n``` (a new line).  

**_Please note: all statements in the body of C functions end with a ```;```, this is just baisc C syntax._** Omitting the ```;``` at the end of a statement
will causes a syntax error, and you will not be able to run the code.

***

Lastly, the ``` return 0; ``` statement is self-explanitory. This is what causes the main function to return the integer number 0 to the operating system's kernel. Main always returns an exit code and 0 is used to indicate successful termination.  

***

**All C programs have a set of included libraries, and all C programs have a main function. Main is where all C programs begin and end. With this basic knowledge in mind, you are ready to start programming.** 

## Next -> [More functions](https://github.com/nac294/C-basics/blob/main/modules/functionSyntax.md)
