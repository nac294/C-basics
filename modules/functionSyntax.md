# Functions in C (extended)
***

A stated in the [first module](https://github.com/nac294/C-basics/blob/main/modules/firstProgram.md), functions are a critically important part of programming
in C. A function in C is essentially the same concept as a function in mathematics. A function, ```f(x)``` given a valid set of inputs ```S```
, and a valid set of outputs ```Y```,
```mma
f(x): x -> y, x ⊂ S, y ∈ Y
```
In English, a C function takes input that is a proper subset of all valid inputs, it then maps that input onto a valid output. For example, let's look
at a simple example from algebra. A function ```f(x) = x + 3```, the only parameter of this function is x, and any input to this function will result in
the input + 3. For a few alternative examples, If 2 is passed in, the result will be 5. If 27 is passed in, the result will be 30.

***  
### Now, let's write this same function (```f(x) = x + 3```) in C...

  <details>
  <summary>Solution (Click me!)</summary>
  
  ```C
  #include <stdio.h>
  
  int f(int x) { // A function that adds three to the input and returns that value
  
    return x + 3;
  }
  ```
</details>  

Note: C is a [strongly-typed language](https://www.techtarget.com/whatis/definition/strongly-typed), so you have to manually specify the type of data 
that each variable stores, and the type of data each function returns. For example, in the example above, 
the data type the function returns is specified as int (integer), the input variable x is the same. As specified in the function 
declaration this function returns and integer and it has a single parameter an integer variable named x.
***

Let's upgrade the last function. 
 ```C
  #include <stdio.h>
  
  int f(int x) {
    
    return x + 3;
  }
  
  
  int main() {
  
    printf("%d\n", f(3));
    
    return 0;
  }
  ```
This is now a complete progam, We are now "calling" the f() function in main. 
In the printf() function you can print a variable by using a ```%``` followed by an initial specifying the type of data. Here ```%d``` indicates printf()
should print a decimal value. _Note: the first argument to printf() should be a string literal. The other arguments are the variables to be printed._
By passing the f() function to printf we can print the value it returns.
in this case f(3) returns 6, and printf prints it to the screen.  

Because C is a [procedural-oriented](https://eng.libretexts.org/Courses/Delta_College/CS11_-_Informations_Systems/02%3A_Information_Systems_for_Strategic_Advantage/2.04%3A_Information_Systems_Development/2.4D%3A_Programming_Languages/1.03%3A_Procedural/Object_Oriented) programming language, functions are very important for splitting up problems. Without using functions, you will have large blocks of code in main(), this is not incorrect, but it it almost universally considered bad practice. So far, we have covered some basic example of functions; however, functions in C are useful for more than just arethmatic computations.  

## Next -> [Variables](https://github.com/nac294/C-basics/blob/main/modules/variables.md)
## Previous -> [First program](https://github.com/nac294/C-basics/blob/main/modules/firstProgram.md)
