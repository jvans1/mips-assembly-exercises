# Creating a Simple Loop

With high level languages, it's easy to take even the simplest things for granted. In this exercise you will write assembly code that initializes an "array" of integers using an array. Consider the following c function:

```c
#include "stdio.h"

int main(int argc, char const *argv[]) {
  char a[10];
  for (int i=0; i<10; i++){
    int v = i + 48;
    a[i] = (char)v;
  }

  printf("%s", a); // prints 0123456789
}
```

# Important Considerations

* How can we represent an array in assembly language?
  * What is the "data type" of the value being stored at each array index?
    * As an int?
    * As a char?
  * Where shall we store each of the characters?
  * How long shall each character be?
  * How do we let printf know that it should be printing "0123456789" instead of "4849505152535455565758"

Once you have a working solution that prints 0123456789, how would you have to change your solution to print the integer values (rather than the ASCII characters) stored in our "array"?
  * Can we still make a single call to our printf equivalent?
  
