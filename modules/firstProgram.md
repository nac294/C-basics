# Basic Concepts in C Programming
***
The first point of interest in C programming is that every program starts with the same basic syntax.
***

Hello world is the first program most programmers every write. An example implementaton of hello world in C is shown below.

```C
#include <stdio.h>

int main() {

  printf("Hello world\n");
  
  return 0;
}
```
Before learning how to write code, you need to understand the components of a C program. Let's analyse hello world piece-by-piece.  

***
First ``` #include <stdio.h> ``` is a pre-processor directive. C code elements are organized in what are called libraries. The include statements are self-explanitory,
they are used to include the contents of a specific library. For example, the implementation of the ``` printf() ``` function is 
located in stdio.h, and we cannot use it without including the file's contents first.

***

The next statement is ``` int main() {} ```, this is a *function definition*. This statement has multiple parts. In this statement we are declaring the "main" function. 
A main function is required in every C program because every C program begins and ends in main().  

``` returnType functionName(input) { code } ```   

```int``` is the type of data the funciton returns, or "outputs." ```main``` is the name of the function. ```()``` is where any inputs to the function are defined. ```{}``` is where the actual code is written.

The main function in the hello world program is a function that takes no input and returns an integer. The code for printing the text is written between the ```{}``` after the function name.  


***

The explanation of ``` printf("Hello world!\n") ``` is simple. Printf is a function that prints data to the screen. In this case printf is printing the string literal
"Hello world!", followed by ```\n``` (a new line).  

**_Please note: all statements in the body of C functions end with a ```;```, this is just baisc C syntax._**

***

Lastly, the ``` return 0; ``` statement is self-explanitory. This is what causes the main function to return 0 to the operating system's kernel. Main returns
an exit code and 0 is used to indicate successful termination.  

***

**All C programs have a set of included libraries, all C programs have a main function, and main is where all C programs begin and end. With this basic knowledge in mind, you are ready to start programming.** 

## Next -> [More functions](https://github.com/nac294/C-basics/blob/main/modules/functionSyntax.md)
