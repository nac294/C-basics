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
Scanf works with almost all types of variables in C. The syntax of scanf() changes slightly when used with things other than a char array. Notice the use of ```&``` in the example below. this is necessary for reading data into variables. Using ```&``` before a variable indicates that you are accessing the memory address of the variable, not the variable's value. The absense of the ampersand when reading into a C string is because of how array names work. Do not worry about this...
```C
#include <stdio.h>

int main() {

  char cStr[50];
  int intArr[5];

  int test;
  scanf("%d", &test); // Using &test is necessary here to read into the single variable
 
  scanf("%d", &intArr[0]); // & is nessary when reading into a single array element
  
  scanf("%s", cStr); // & is unnecessary when reading into c strings
  
  
  printf("%d %d %s\n", test, intArr[0], cStr); // Print the test variable, the first element of the integer array, and the string
  
  return 0;
}
```
***
Using scanf() in the manner works with almost all C variables.
### Write a program that reads values into an int array with three elements, and gets a string from the user. Afterward, the program should output the message followed by the three values.  

<details>
<summary>Solution (Click me!)</summary>
  
```C 
#include <stdio.h>
#include <string.h>

int main() {

  int arr[3];
  char charBuf[512];
  
  scanf("%d %d %d", &arr[0], &arr[1], &arr[2]);
  scanf("%512s", charBuf); // The use of 512 before the s prevents reading too many characters from the keyboard
  
  strcat(charBuf, "\0");
  
  printf("%s\n", charBuf);
  printf("%d %d %d\n", arr[0], arr[1], arr[2]);
  
  return 0;
}
```
</details>  
  
This program only reads a single word from the user because though. If you want to read an entire line, you can use a special function called ```getline()```. This is actually easier, because getline() automatically appends the null terminator unlike scanf(), meaning we can omit the strcat.

  
  
  
