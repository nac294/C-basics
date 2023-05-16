# Ifs, binary logic, and conditions.  

This is where the lesson goes from broad and introductory and specific. We have not examined any practical C code thus far, this module changes that with the introduction of basic flow control. The most basic
flow control in C comes in the form of if statements. The concept behind if statements is relatively straighforward; if this codition is true execute this block of code, otherwise, execute this other block of code.
Let's see a simple example.  


Given a variable, we want to check if it is greater than 0, if so we print "The number is greater than 0", if not, we want to print "The number is less than or equal to 0". We can easily write this code using an
if/else statement.

```C
void checkNumber(const int num) {

  // check if the number is greater than 0
  if(num > 0) { // If so, do this
    
    printf("The number if greater than 0\n");
    
  } else {  // If not do this
 
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

Notice if statements have a pair of {} just like functions do. You will write your code for your if/else statements in between the ```{}```. 
 
