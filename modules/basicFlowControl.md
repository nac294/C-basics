# Ifs, binary logic, and conditions.  

This is where the lesson goes from broad and introductory to specific. We have not examined any practical C code thus far, this module changes that with the introduction of basic flow control. The most basic
flow control in C comes in the form of if statements. The concept behind if statements is relatively straighforward: if this codition is true execute this block of code, otherwise execute this other block of code.
Let's see a simple example.  


Given a variable, we want to check if it is greater than 0, if so we print "The number is greater than 0", if not, we want to print "The number is less than or equal to 0". We can easily write this code using an if/else statement.

```C
void checkNumber(const int num) {

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

Notice if statements have a pair of {} just like functions do. You will write your code for your if/else statements in between the ```{}```. You will also notice that the if statement has a pair of () just like functions. The (), in this case, do not specify a set of arguments being passed to the if block, it specifies the logiv=cal condition that is to be evaluated. You can essentially pass any logical statement to an if. For example, in C there are many different examples of logic, and there are sets of symbols for each.

```C
!= // Is not equal to
== // Is equal to, note using one = is different than two. One equal sign is an assignment of a value to something. Two equal signs are a test for equavilance
< // Is less than
> // Is greater than
<= // Is less than OR equal to
>= // Is greater than OR equal to
```  

We can also combine these into a large chain of logical conditions. It would not be practical for us to implement a seperate if statement for each conditions. Lets see an example where this would not be practical. Example: We have light with two switches connected. We want each switch to be reactive. Let's implement this, assuming the switch inputs are synchronous. Here SW1 and SW2 represent the switches, 
1 = switch on, 0 = switch off.

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


This code is a mess, we can surely clean this up and make it more efficient. Logic in computers derrives heavily from Boolean algebra, this becomes more obvious the more you write practical code. This also means computers represent conditions that are false as 0 and conditions that are true as literally anything else (usually 1). With this in mine let's look at this problem from a mathematical perspective. We can see that the lightswitch problem entails a sinple [XOR](https://www.vedantu.com/iit-jee/basic-logic-gates) operation.  
![](https://github.com/nac294/C-basics/blob/main/images/lightXOR.png)  
We can simplify this code by using the set of provided logical operators provided in C.

```C
&& // Logical AND, as in, this and that
|| // Logical OR, as in, this or that
! // Logical NOT, as in, if this is true, make it false, if it is false, make it true
```
 
