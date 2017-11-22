# Nesting Function Calls

The purpose of this exercise is to give students practice manipulating the call stack, return addresses, return registers, saved registers, and using a "calling convention" in assembly language.

Consider the following c code:

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int c(int n) {
  return n + 5;
}

int b(int n) {
  int x = c(n);
  return x * n;
}

int a(int n) {
  int x = b(n);
  int y = c(x);
  return x + y + n;
}

int main(int argc, char const *argv[]) {
  int r = a(atoi(argv[1]));
  printf("%s => %d\n", argv[1], r);
}
```

This C code, while a bit contrived, requires that functions call each other, save data from saved registers, save return addresses. In other words to generate assembly language for this C code, the compiler will have to follow a calling convention.

Translate this code into MIPS. Use a standard calling convention, remember to save the values of any $s registers (and ensure you use a $s register for anything that needs to be preserved)

## Stretch it:

Use the code you wrote in prompt-and-print to prompt the user for a string, transform it to an int, and print the resulting number.

What happens if you forget to store the saved values?

__Be a hacker__ Can you use what you know about calling conventions and the location of the test data maliciously to trick the tests into passing, even though your function returns values that don't pass the test case?

> There is more than one way to do this... how many different ways can you think of?
