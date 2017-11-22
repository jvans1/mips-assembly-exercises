## Recursive Functions in Assembly

You've probably seen this function by now:

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int fib(int n) {
  if(n == 0) return 1;
  if(n == 1) return 1;

  return fib(n-1) + fib(n-2);
}


int main(int argc, char const *argv[]) {
  int r = fib(10);
  printf("%d", r); // 89
}
```

Recursive functions in assembly are particularly interesting because you are sure to overwrite register values in anytime you make the "recursive" call. They're also interesting in that at the assembly level, they hardly seem recursive -- they seem a lot more like loops...

Translate this c code into MIPS assembly.

## Stretch it

Use the prompt and print code to allow your users to input their desired n value!

When your solution is working, step through and at each step write down your prediction for what will change. Be detailed:

* will this change a register value or a memory location?
  * Which register or memory location?
  * What will the new value be?
* Will this impact the program counter?
  * What will the new address of the counter be?
* Introduce a common bug in recursion: forget to add the base case
  * When do we get a "stack overflow error?"
  * In the context of assembly... what IS a stack overflow error?
