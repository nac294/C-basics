# Variables
Now lets talk about the variables in C. Variables are user-defined names that are associated with a specific memory address. You can store whatevery you want
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

## More complex functions
Write a function that prints a floating point number in main, passes it into a function that squares it, and then prints the result.

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
