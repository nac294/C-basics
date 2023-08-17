# Flow control using loops

Now, we discuss the subject of flow control using loops. Loops are very similar to if statements. Let's look at a quick example... Write a program that increments a variable, the variable should be initialized to
0, and it should be incremented until it reaches 30. Notice, if you tried to do this without a loop, you would have to write thirty consecutive increment statements!  

Let's use a loop instead (that will be muchy cleaner, and easier.)  
```C
#include <stdio.h>

int main() {

  int num = 0;  // Variable initialized to 0

  while(num < 30) {  // Loops from 0 to 30, and prints the value of the variable each time.
    num = num + 1;
    printf("The number is now: %d\n", num);
  }

  return 0;
}
```
The ```while()``` statement in the code above repeatedly executes the same two lines of code while the condition ```num < 30``` is true. These loops are syntatically the same as ```if()``` statements. While
the condition is true, execute the code between the ```{}```.  

## Other types of loops

While loops are not the only type of loop. There are also do/while loops, and for loops. Each type of loop has its own specific uses.
