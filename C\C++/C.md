# 1 Getting Started with C

## 1.1 Print the Words: `hello, world`

1. Write the code in a file named **hello_world.c**.

```c
#include <stdio.h>
main() 
{
    printf("hello, world\n");
}
```

2. Compile it with the following command:

```bash
gcc hello_world.c
```

3. Run the executable file.

```bash
./a.out
```

## 1.2 Explanation of the Above Example

&emsp;&emsp;A C program, whatever its size, consists of **functions** and **variables**. A function contains statements that specify the computing operations to be done, and variables store values used during the computation.

&emsp;&emsp;Our example is a function named main. Normally we are at liberty to give functions whatever names we like, but "main" is special --- **our program begins executing at the beginning of main**. This means that every program must have a main somewhere. main will usually call other functions to help perform its job, some that we wrote, and others from libraries that are provided for us.

&emsp;&emsp;One method of communicating data between functions is for the calling function to provide a list of values, called arguments, to the function it calls. The parentheses after the function name surround the argument list. In this example, main is defined to be a function that expects no arguments, which is indicated by the empty list `()`.

&emsp;&emsp;The first line of the program: `#include <stdio.h>`, tells the compiler to include information about the standard input/output library; this line appears at the beginning of many C source files.

&emsp;&emsp;The statements of a function are enclosed in braces `{ }`. The function **main** contains only one statement: `printf("hello, world\n");`. A function is called by naming it, followed by a parenthesized list of arguments, so this calls the function **printf** with the argument `"hello, world\n"`.

&emsp;&emsp;

## 1.3 Variables



## 1.4 Symbolic Constants

## 1.5 Character Input and Output

## 1.6 External Variables and Scope

# 2 Types, Operators and Expressions

## 2.1 

# 3 Control Flow

# 4 Functions and Program Structure

# 5 Pointers and Arrays

# 6 Structures

# 7 Input and Output

# 8 The Unix System Interface
