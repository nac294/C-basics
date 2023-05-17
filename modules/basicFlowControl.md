# Ifs, binary logic, and conditions.  

This is where the lesson goes from broad and introductory to specific. We have not examined any practical C code thus far, this module changes that with the introduction of basic flow control. The most basic
flow control in C comes in the form of if statements. The concept behind if statements is relatively straighforward: if this codition is true execute this block of code, otherwise execute this other block of code. Let's see a simple example.  


Given a variable, we want to check if it is greater than 0, if so we print "The number is greater than 0", if not, we want to print "The number is less than or equal to 0". We can easily write this code using an if/else statement.

```C
void checkNumber(const int num) { // Const is a special word that indicates variables cannot be changed.
// If a variable is passed to a function as a const, its value cannot be changed in the function

  // check if the number is greater than 0
  if(num > 0) { // If so, do this
    
    printf("The number if greater than 0\n");
    
  } else {  // If not, do this
 
    printf("The number is less than or equal to 0\n");
  
  }
}


int main() {

  checkNumber(5);
  checkNumber(0);
  
  return 0;
}
```  

```
Output:  
The number is greater than 0  
The number is less than or equal to 0
```

Notice if statements have a pair of {} just like functions do. You will write your code for your if/else statements in between the ```{}```. You will also notice that the if statement has a pair of () just like functions. The (), in this case, do not specify a set of arguments being passed to the if block, it specifies the logical condition that is to be evaluated. You can essentially pass any logical statement to an if. For example, in C there are many different examples of logic, and there are sets of symbols for each. These symbols are called operators. Whether you know it or not, you use operators every day. An operator is just a symbol that performs an operation on a value or set of values. For example, the + symbol is an operator. You take the value on the left side and add it to the value on the right side which gives the sum. Given below are the set of comparison operators in C.

```C
!= // Is not equal to
== // Is equal to, note using one = is different than two. One equal sign is an assignment of a value to something. Two equal signs are a test for equavilance
< // Is less than
> // Is greater than
<= // Is less than OR equal to
>= // Is greater than OR equal to
```  

We can also combine these operators into a large chain of logical conditions. It would not be practical for us to implement a seperate if statement for each condition. Lets see an example where this would not be practical. Example: We have a light with two switches connected. We want each switch to be reactive. Let's implement this, assuming the switch inputs are synchronous. Here SW1 and SW2 represent the switches, 1 = switch on, 0 = switch off. When both switches are the same the light should be off, otherwise it should be on.

```C
#include <stdio.h>


void turnLightOn() {
  printf("Light on\n");
}


void turnLightOff() {
  printf("Light off\n");
}


int main() {

  int SW1 = 0; // Default to off
  int SW2 = 0; // Default to off
  
  
  // Get the values of the switches
  
  
  if(SW1 == 1) {
  
    if(SW2 == 0) {
      turnLightOn();
    } else {
      turnLightOff();
    }
    
  } else {
    
    if(SW2 == 1) {
      turnLightOn();
    } else {
      turnLightOff();
    }
    
  }

  return 0;
}
```  


This code is a mess, we can clean this up and make it more efficient. Logic in computers derrives heavily from Boolean algebra, this becomes more obvious the more you write practical code. This also means computers represent logical conditions that are false as 0 and conditions that are true as literally anything else (usually 1). With this in mind let's look at this problem from a mathematical perspective. We can see that the lightswitch problem entails a simple [XOR](https://www.vedantu.com/iit-jee/basic-logic-gates) operation.  
![](https://github.com/nac294/C-basics/blob/main/images/lightXOR.png)  
We can simplify this code by using the set of provided logical operators provided in C.

```C
&& // Logical AND, as in, this and that
|| // Logical OR, as in, this or that
! // Logical NOT, as in, if this is true, make it false, if it is false, make it true (opposite)
```  

These operators are what allows us to evaluate multiple logic statements at the same time. Let's see a reconstructed example of the previous lightswitch example.

```C
#include <stdio.h>


void turnLightOn() {
  printf("Light on\n");
}


void turnLightOff() {
  printf("Light off\n");
}


int main() {

  int SW1 = 0; // Default to off
  int SW2 = 0; // Default to off
  
  
  // Get the value of the switches
  
  
  if(SW1 == 1 && SW2 == 1 || SW1 == 0 && SW2 == 0) {
    turnLightOff();
  } else {
    turnLightOn();
  }
  
  return 0;
}
```  

The condition used as the condition for the if() block is read in plain English as follows: IF SW1 is equal to 1 AND SW2 is equal to 1, OR SW1 is equal to 0 AND SW2 is equal to 0, turn the light off. If you go through this in your head, this is logically correct and it is simpler than the previous example. There are essentially infinite combinations of logical conditions that you can use to your advantage...  
The previous example is nice, but there is an even simpler way to solve this problem.

```C
#include <stdio.h>


void turnLightOn() {
  printf("Light on\n");
}


void turnLightOff() {
  printf("Light off\n");
}


int main() {

  int SW1 = 0; // Default to off
  int SW2 = 0; // Default to off
  
  
  // Get the value of the switches
  
  
  if(SW1 == SW2) {
    turnLightOff();
  } else {
    turnLightOn();
  }
  
  return 0;
}
```  

It is easy to see that the light should always be off if the switches are the same. This is as simple as this program gets; it does not require nested ifs nor does it require complex combinations of logical operators. This is a good example of the fact that there are multiple ways to solve a problem when programming. "When writing an algorithm, you should first think about the easiest, most obvious way to solve the problem; you can worry about optimization after the fact." [-Dr. Eric A. Hansen](https://web.cse.msstate.edu/~hansen/)  

## Bitwise operations
Let's take a step back from coding for a bit. Understanding how computers "think" is important for coding. Humans count in base 10. each digit goes from 0-9 before it resets back to 0, hence 10 values per digit. Whereas, computers count in base 2 (binary), understanding binary is important for understanding logical operations in C. Each digit in binary (bit) has two possible values, 1 and 0. Each new digit can be though of as the base to a specific power. If we have three base 10 digits, we have 1, 10 and 100, hence 10^0, 10^1, and 10^2. You can also consider this the maximum number of values the digits can represent. With three base 10 digits we can have 10^3 possible values, i.e. 0-999. Binary is no different an example of a 4-bit binary integer is show below.  
![](https://github.com/nac294/C-basics/blob/main/images/Binary.PNG)  
Give 4 bits, we have 4 base 2 digits, meaning we can represent 2^4 possible values, i.e. 0-15. If you are still confused [this site](https://www.advanced-ict.info/interactive/binary.html) explains the concept of binary perfectly, and it has an interactivae example of a binary counter!  


C provides a set of operators for bit operations:
```C
& // Bitwise AND
| // Bitwise OR
~ // Bitwise NOT (inverse)
^ // Bitwise XOR
<< // Shift bits left
>> // Shift bits right
```  

A detailed explanation of these bitwise operations can be found [here!](https://www.thegeekstuff.com/2012/10/bitwise-operators/) Since the lightswitch example involved an XOR, we can solve the lightswitch problem with a bitwise XOR operation as well!
```C
#include <stdio.h>


void turnLightOn() {
  printf("Light on\n");
}


void turnLightOff() {
  printf("Light off\n");
}


int main() {

  int SW1 = 0; // Default to off
  int SW2 = 0; // Default to off
  
  
  // Get the value of the switches
  
  
  if(SW1 ^ SW2) { // SW1 XOR SW2
    turnLightOn();
  } else {
    turnLightOff();
  }
  
  return 0;
}
```  

## Exercise  



### Next -> []()
### Previous -> [Basic I/O](https://github.com/nac294/C-basics/blob/main/modules/io.md)
