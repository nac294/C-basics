# Variables
Now lets talk about variables in more detail. Variables int C are user-defined names that are associated with a specific memory address. You can store whatevery you want
in that variable as long as it is the correct type. Variables can be used in algebraic computations, 
they can be incremented and decremented, and the value they store can be printed to the screen.  

Common C datatypes include 
```C
int // Integer
float // Floating point number
double // Double precision floating point number
char // Single character
void // No datatype
```
***
Functions use these same datatypes to specify what kind of data they return, if any. Remember the function syntax in C!  
```returnVal functionName(parameters/arguments) { code; }```
```C
int func(int var) {} // Accepts an int, returns an int
float func(float var) {} // Accepts a float, returns a float
double func(double var) {} // Accepts a double, returns a double
char func(char var) {} // Accepts a char, returns a char
void func() {} // Accepts nothing, returns nothing 
void func(void) {} // is also acceptable
```

## More complex functions
Write a program that prints a floating point number in main, passes it into a function that squares it, and then prints the result.

<details>
<summary>Solution (Click me!)</summary>
  
```C
#include <stdio.h>
  
float square(float num) { // Function to compute square
    
  return num * num;
}
  
  
int main() {
  
  float pi = 3.14159265;
    
  printf("Num before: %f\n", pi);
    
  pi = square(pi); // Only necessary if you want to store the squared value
  printf("Num after: %f\n", pi);  // Alternatively printf("Num after: %f\n", square(pi)); also works if you do not want to store the new value of pi
    
  return 0;
}
  ```
</details>

## More storage  
Now, you may be wondering, how can we store multiple elements? Do we really have to write a seperate variable for each data element? Thankfully, the answer is no...  
C has a standardized data structure called an array for storing multiple elements of the same type.  
  
A C array is created like this:
```C
int main() {
  
  int x; // Normal integer variable
  
  int arr[5]; // An array of 5 integers.
  
  return 0;
}
```  
Arrays in C are extremely useful, they act as multiple seperate variables but they share a single name. This is made possible by indexing. As seen below, array elements are accessed with pecific index numbers.
```C
int main() {
  
  int arr[5];
  
  // NOTE: computers start counting at 0, not 1
  // So the five elements of this 5-element array are indexed as { 0, 1, 2, 3, 4 } 
  arr[0] = 6; // Set the first element in the array to 6
  arr[4] = 762 // Set the last element in the array to 762
  
  printf("%d %d\n", arr[0]);
  
  return 0;
}
```
```Output: 6 762```  
  
C arrays has many practical applications, one of them is character strings. C does not have a standardized way to store strings, so you must store them in a sufficiently long character array.
```C
#include <stdio.h>
  
int main() {
  
  char cstring[512]; // Make a 512-element character array/C string.
  
  char cstring2[] = "You do not have to specify a number of elements if you want to immediately assign the array a value!";
  
  // The approach above also works for arrays of every datatype, although it looks slightly different.
  
  return 0;
}
```
  
With this in mind, you now understand C's most standard data container, and you are ready to move on to basic I/O.
  
  
 
## Previous -> [More functions](https://github.com/nac294/C-basics/blob/main/modules/functionSyntax.md)
