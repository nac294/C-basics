# Basic I/O  

Now that we have covered the basic concepts, it is time to begin the delve into the functionality provided in C. Considering the definition of an [algorithm](https://www.cs.purdue.edu/homes/spa/courses/cs182/algorithms-rego.pdf)
input and output (I/O) are both important parts of every program. C provides a set functions specifically dedicated to I/O. You should already have a remote idea about how ```printf()``` works, this function is a big
part of I/O in C. However, we need to be able to get input from the keyboard as well. This is where ```scanf()``` comes in.  

## A program to get the user's input
```C
#include <stdio.h>  // Standard I/O is in the name

int main() {
  
  char charBuf[1024];  // Make a "character buffer" for the user's input
  
  scanf("%s", charBuf); // Use scanf() to get the user's input
  
  printf("%s\n", charBuf); // Print the user's input
  
  return 0;
}
```  

There is an isue with this code. Strings in C need to be terminated by a special character "\0" this is the null terminator. This character is what tells the computer to stop reading. If the null terminator
is absent in a string, the computer will try to read more characters than were input, and it causes random, unintelligible (garbage) output. Therefore we have to append \0 to our strings.
Again, C provides a function for this. ```strcat()```. To use this function we need to include a new library, ```string.h```.  

```C
#include <stdio.h>  
#include <string.h>

int main() {
  
  char charBuf[1024];  // Make a "character buffer" for the user's input
  
  scanf("%s", charBuf); // Use scanf() to get the user's input
  strcat(charBuf, "\0"); // Concatenate the strings to append the null terminator.
  
  printf("%s\n", charBuf); // Print the user's input
  
  return 0;
}
```
