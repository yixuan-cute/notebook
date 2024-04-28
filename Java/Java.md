# 1 Getting Started with Java

## 1.1 Downloading and Setting up a Java Development Kit

1. Click <a href="https://www.oracle.com/java/technologies/downloads/" target="_blank">here</a> to download Oracle JDK.

2. Unpack the downloaded file and put it somewhere.

```bash
tar -zxvf jdk1.8.0_371
sudo mv jdk1.8.0_371/ /opt/
```

3. Set environment variables.

Execute `sudo vim /etc/zsh/zprofile`, and then add the following lines:

```bash
export JAVA_HOME=/opt/jdk1.8.0_371/
export PATH=$PATH:$JAVA_HOME/bin
```

## 1.2 Running the Hello World Program

1. Create the first Java class.

```java
public class MyFirstClass {
    
}
```

&emsp;&emsp;The name of this Java class is MyFirstClass. We need to save this text in a file named MyFirstClass.java.

> Note:  
> &emsp;&emsp;A Java class must be saved in a file that has the same name as the class with the extension `.java`. This is mandatory and is in fact very convenient.  
> &emsp;&emsp;We can give this class any name as long as it does not start with a number. There is a convention though: **the name of a Java class starts with a capital letter**. (If it consists of more than one word, capitalize the first letter of each word.) This is not mandatory but all Java developers follow this convention.

2. Add code to our class.

```java
public class MyFirstClass {
    public static void main(String... args) {
        System.out.println("Hello, World!");
    }
}
```

3. Compile the first class.

&emsp;&emsp;Change to the directory where we saved our first class MyFirstClass.java. We can check that we are in the right directory by typing `dir`. And then execute the following command:

```bash
javac MyFirstClass.java
```

&emsp;&emsp;Checking the content of the directory again should show a new file in it: MyFirstClass.class, which is called a byte code file.

4. Run the byte code.

```bash
java MyFirstClass
```

## 1.3 Expressions, Statements and Blocks

### 1.3.1 Expressions

&emsp;&emsp;An expression is a construct made up of variables, operators, and method invocations, which are constructed according to the syntax of the language, that evaluates to a single value.

```java
int cadence = 0;

anArray[0] = 100;
System.out.println("Element 1 at index 0: " + anArray[0]);

int result = 1 + 2; // result is now 3

if (value1 == value2)
    System.out.println("value1 == value2");
```

&emsp;&emsp;The data type of the value returned by an expression depends on the elements used in the expression.

&emsp;&emsp;The expression `cadence = 0` returns an `int` because the assignment operator returns a value of the same data type as its left-hand operand; in this case, cadence is an `int`.

## 1.4 Objects, Classes, Interfaces, Packages, and Inheritance

# 2 Creating Variables and Naming Them

## 2.1 Variables

&emsp;&emsp;Whatever and whenever we build a project or we build an application, what we are doing is we are doing the processing on data (This data can be coming from user or something else and we will do some work with it).

&emsp;&emsp;When we want to **temporarily store and process this data**, we need to use variables.

> Note:  
> &emsp;&emsp;In the Java programming language, the terms "field" and "variable" are both used.

The Java programming language defines the following kinds of variables:

* Instance Variables (Non-Static Fields)
* Class Variables (Static Fields)
* Local Variables
* Parameters

> Having said that, there are the following general guidelines when discussing fields and variables:  
> &emsp;&emsp;If we are talking about "fields in general" (excluding local variables and parameters), we may simply say "fields". If the discussion applies to "all of the above", we may simply say "variables".

## 2.2 Naming Variables

The rules and conventions for naming our variables can be summarized as follows:

1. A variable's name can be any legal identifier — an unlimited-length sequence of Unicode letters and digits, beginning with a letter, the dollar sign `$`, or the underscore character `_`.

> Note:  
> &emsp;&emsp;The convention, however, is to always begin our variable names with a letter, not `$` or `_`. Subsequent characters may be letters, digits, dollar signs, or underscore characters. Additionally, the dollar sign character, by convention, is never used at all.  
> &emsp;&emsp;A similar convention exists for the underscore character; while it's technically legal to begin our variable's name with `_`, this practice is discouraged.  
> &emsp;&emsp;White space is not permitted.

2. When choosing a name for our variables, use full words instead of cryptic abbreviations. Doing so will make our code easier to read and understand.

> Note: The name we choose **must not be a keyword or reserved word**.

3. If the name we choose consists of only one word, spell that word in all lowercase letters. If it consists of more than one word, capitalize the first letter of each subsequent word.

> Note:  
> &emsp;&emsp;The names gearRatio and currentGear are prime examples of this convention.  
> &emsp;&emsp;If our variable stores a constant value, such as `static final int NUM_GEARS = 6`, the convention changes slightly, capitalizing every letter and separating subsequent words with the underscore character. (By convention, **the underscore character is never used elsewhere**.)

# 3 Creating Primitive Type Variables

## 3.1 Primitive Types

&emsp;&emsp;The Java programming language is statically-typed, which means that all variables must first be declared before they can be used. This involves stating the variable's type and name, as we have already seen:

```java
int gear = 1;
```

&emsp;&emsp;A variable's data type determines the values it may contain, plus the operations that may be performed on it.

&emsp;&emsp;In addition to `int`, the Java programming language supports seven other primitive data types. **A primitive type is predefined by the language and is named by a reserved keyword**.  The eight primitive data types supported by the Java programming language are:

1. `byte`: An 8-bit signed two's complement integer. ($-128$ ~ $127$)
2. `short`: A 16-bit signed two's complement integer. ($-32768$ ~ $32767$)
3. `int`: A 32-bit signed two's complement integer. ($-2^{31}$ ~ $2^{31}-1$)
4. `long`: A 64-bit two's complement integer. ($-2^{63}$ ~ $2^{63}-1$)
5. `float`: A single-precision 32-bit IEEE 754 floating point.
6. `double`: A double-precision 64-bit IEEE 754 floating point.
7. `boolean`: The boolean data type has only two possible values: `true` and `false`.
8. `char`: A single 16-bit Unicode character. It has a minimum value of `\u0000 (or 0)` and a maximum value of `\uffff (or 65,535 inclusive)`.

&emsp;&emsp;In addition to the eight primitive data types listed above, **the Java programming language also provides special support for character strings via the `java.lang.String` class**. Enclosing our character string within double quotes will automatically create a new String object; for example:

```java
String s = "this is a string";
```

## 3.2 Initializing a Variable(field) with a Default Value

&emsp;&emsp;It is not always necessary to assign a value when a field is declared. Fields that are declared but not initialized will be set to a reasonable default by the compiler.

> Note:  
> &emsp;&emsp;Generally speaking, this default will be zero or null, depending on the data type. Relying on such default values, however, is generally considered bad programming style.

&emsp;&emsp;The following table summarizes the default values for the above data types:

|       Data Type       | Default Value (for fields) |
|:---------------------:|:--------------------------:|
|          byte         |              0             |
|         short         |              0             |
|          int          |              0             |
|          long         |             0L             |
|         float         |            0.0f            |
|         double        |            0.0d            |
|          char         |           \u0000           |
| String(or any object) |            null            |
|        boolean        |            false           |

> Note:  
> &emsp;&emsp;Local variables are slightly different; **the compiler never assigns a default value to an uninitialized local variable**.  
> &emsp;&emsp;We must assign a value to an uninitalized local variable before we use it. Accessing an uninitialized local variable will result in a compile-time error.

## 3.3 Creating Values with Literals

&emsp;&emsp;Primitive types are special data types built into the language; they are not objects created from a class.

&emsp;&emsp;A literal is the source code representation of a fixed value; literals are represented directly in our code without requiring computation.

&emsp;&emsp;As shown below, it is possible to assign a literal to a variable of a primitive type:

```java
boolean result = true;
char capitalC = 'C';
byte b = 100;
short s = 10000; int i = 100000;
```

### 3.3.1 Integer Literals

&emsp;&emsp;**An integer literal is of type `long` if it ends with the letter L or l; otherwise it is of type `int`.**

> Note:  
> &emsp;&emsp;It is recommended that we use the uppercase letter L because the lowercase letter l is hard to distinguish from the digit 1.

&emsp;&emsp;Values of the integral types `byte`, `short`, `int`, and `long` can be created from `int` literals. Values of type `long` that exceed the range of `int` can be created from `long` literals.

```java
byte byteVar = 100;
short shortVar = 100;

int intVar = 100;

long longVar1 = 100;

long longVar2 = 10000000000; //Error: The literal 10000000000 of type int is out of range
long longVar3 = 10000000000L; //Pass
```

Integer literals can be expressed by these number systems:

* **Decimal**: Base 10, whose digits consists of the numbers 0 through 9
    * this is the number system we use every day
* **Hexadecimal**: Base 16, whose digits consist of the numbers 0 through 9 and the letters A through F
* **Binary**: Base 2, whose digits consists of the numbers 0 and 1
    * we can create binary literals in Java SE 7 and later

The prefix 0x indicates hexadecimal and 0b indicates binary:

```java
// The number 26, in decimal
int decimalValue = 26;

//  The number 26, in hexadecimal
int hexadecimalValue = 0x1a;

// The number 26, in binary
int binaryValue = 0b11010;
```

### 3.3.2 Floating-Point Literals

&emsp;&emsp;**A floating-point literal is of type `float` if it ends with the letter F or f (32-bit float literal); otherwise its type is `double` and it can optionally end with the letter D or d (64-bit double literal; this is the default and by convention is omitted).**

&emsp;&emsp;The floating point types can also be expressed using E or e (for scientific notation):

```java
double d1 = 123.4;

// same value as d1, but in scientific notation
double d2 = 1.234e2;
```

> Note:  
> &emsp;&emsp;The literal of double connot be converted to float automaticly. A **-f** postfix is needed. But a int literal can be assigned to a short (or byte) variable as long as the literal is not out of the range of short (or byte). No postfix is needed.

### 3.3.3 Character and String Literals

### 3.3.4 Using Underscore Characters in Numeric Literals

## 3.4 Using `var` type indentifier

# 4 Creating Arrays

&emsp;&emsp;The following program, ArrayDemo, creates an array of integers, puts some values in the array, and prints each value to standard output.

```java
class ArrayDemo {
    public static void main(String[] args) {
        // declares an array of integers
        int[] anArray;

        // allocates memory for 10 integers
        anArray = new int[10];

        // initialize first element
        anArray[0] = 100;
        // initialize second element
        anArray[1] = 200;
        // and so forth
        anArray[2] = 300;
        anArray[3] = 400;
        anArray[4] = 500;
        anArray[5] = 600;
        anArray[6] = 700;
        anArray[7] = 800;
        anArray[8] = 900;
        anArray[9] = 1000;

        System.out.println("Element at index 0: " + anArray[0]);
        System.out.println("Element at index 1: " + anArray[1]);
        System.out.println("Element at index 2: " + anArray[2]);
        System.out.println("Element at index 3: " + anArray[3]);
        System.out.println("Element at index 4: " + anArray[4]);
        System.out.println("Element at index 5: " + anArray[5]);
        System.out.println("Element at index 6: " + anArray[6]);
        System.out.println("Element at index 7: " + anArray[7]);
        System.out.println("Element at index 8: " + anArray[8]);
        System.out.println("Element at index 9: " + anArray[9]);
    }
}
```

## 4.1 Declaring a Variable to Refer to an Array

&emsp;&emsp;The preceding program declares an array (named anArray) with the following line of code:

```java
// declares an array of integers
int[] anArray;
```

&emsp;&emsp;Similarly, we can declare arrays of other types:

```java
byte[] anArrayOfBytes;
short[] anArrayOfShorts;
long[] anArrayOfLongs;
float[] anArrayOfFloats;
double[] anArrayOfDoubles;
boolean[] anArrayOfBooleans;
char[] anArrayOfChars;
String[] anArrayOfStrings;
```

&emsp;&emsp;We can also place the brackets after the array's name:

```java
float anArrayOfFloats[];
```

> Note:  
> &emsp;&emsp;However, convention discourages this form; the brackets **identify the array type and should appear with the type designation**.

## 4.2 Creating, Initializing, and Accessing an Array

&emsp;&emsp;One way to create an array is with the new operator:

```java
// create an array of integers
anArray = new int[10];
```

&emsp;&emsp;The next few lines assign values to each element of the array:

```java
anArray[0] = 100; // initialize first element
anArray[1] = 200; // initialize second element
anArray[2] = 300; // and so forth
```

&emsp;&emsp;Each array element is accessed by its numerical index:

```java
System.out.println("Element 1 at index 0: " + anArray[0]);
System.out.println("Element 2 at index 1: " + anArray[1]);
System.out.println("Element 3 at index 2: " + anArray[2]);
```

&emsp;&emsp;Alternatively, we can use the shortcut syntax to create and initialize an array:

```java
int[] anArray = {
    100, 200, 300,
    400, 500, 600,
    700, 800, 900, 1000
};
```

> Note:  
> &emsp;&emsp;Here the length of the array is determined by the number of values provided between braces and separated by commas.

&emsp;&emsp;We can also declare an array of arrays (also known as a **multidimensional array**) by using two or more sets of brackets, such as `String[][]` names. Each element, therefore, must be accessed by a corresponding number of index values.

&emsp;&emsp;In the Java programming language, a multidimensional array is an array whose components are themselves arrays. This is unlike arrays in C or Fortran. A consequence of this is that **the rows are allowed to vary in length**, as shown in the following `MultiDimArrayDemo` program:

```java
class MultiDimArrayDemo {
    public static void main(String[] args) {
        String[][] names = {
            {"Mr. ", "Mrs. ", "Ms. "},
            {"Smith", "Jones"}
        };
        // Mr. Smith
        System.out.println(names[0][0] + names[1][0]);
        // Ms. Jones
        System.out.println(names[0][2] + names[1][1]);
    }
}
```

&emsp;&emsp;Finally, we can use the built-in `length` property to determine the size of any array. The following code prints the array's size to standard output:

```java
System.out.println(anArray.length);
```

## 4.3 Copying Arrays

&emsp;&emsp;The `System` class has an static `arraycopy()` method that we can use to efficiently copy data from one array into another:

```java
public static void arraycopy(Object src, int srcPos, Object dest, int destPos, int length)
```

> Note:  
> &emsp;&emsp;The two Object arguments specify the array to copy from and the array to copy to. The three int arguments specify the starting position in the source array, the starting position in the destination array, and the number of array elements to copy.

## 4.4 Array Manipulations

&emsp;&emsp;For our convenience, Java SE provides several methods for performing array manipulations (common tasks, such as copying, sorting and searching arrays) in the `java.util.Arrays` class.

# 5 Using Operators

## 5.1 The Simple Assignment Operator

&emsp;&emsp;One of the most common operators that we'll encounter is the simple assignment operator `=`. It assigns the value on its right to the operand on its left:

```java
int cadence = 0;
int speed = 0;
int gear = 1;
```

> Note: This operator can also be used on objects to assign **object references**.

## 5.2 The Arithmetic Operators

&emsp;&emsp;The Java programming language provides operators that **perform addition, subtraction, multiplication, and division**.

> Note:  
> &emsp;&emsp;There is a good chance we will recognize them by their counterparts in basic mathematics. The only symbol that might look new to us is `%`, which divides one operand by another and returns the remainder as its result.

```java
class ArithmeticDemo {

    public static void main (String[] args) {

        int result = 1 + 2;
        // result is now 3
        System.out.println("1 + 2 = " + result);
        int original_result = result;

        result = result - 1;
        // result is now 2
        System.out.println(original_result + " - 1 = " + result);
        original_result = result;

        result = result * 2;
        // result is now 4
        System.out.println(original_result + " * 2 = " + result);
        original_result = result;

        result = result / 2;
        // result is now 2
        System.out.println(original_result + " / 2 = " + result);
        original_result = result;

        result = result + 8;
        // result is now 10
        System.out.println(original_result + " + 8 = " + result);
        original_result = result;

        result = result % 7;
        // result is now 3
        System.out.println(original_result + " % 7 = " + result);
    }
}
```

&emsp;&emsp;We can also combine the arithmetic operators with the simple assignment operator to create compound assignments. **For example, `x += 1;` and `x = x + 1;` both increment the value of x by 1.**

&emsp;&emsp;The `+` operator can also be used for **concatenating (joining) two strings together**, as shown in the following ConcatDemo program:

```java
class ConcatDemo {
    public static void main(String[] args){
        String firstString = "This is";
        String secondString = " a concatenated string.";
        String thirdString = firstString + secondString;
        System.out.println(thirdString);  //Output: This is a concatenated string.
    }
}
```

## 5.3 The Unary Operators

&emsp;&emsp;The unary operators require only one operand; they perform various operations such as incrementing (or decrementing) a value by one, negating an expression, or inverting the value of a boolean.

```java
class UnaryDemo {

    public static void main(String[] args) {

        int result = +1;
        // result is now 1
        System.out.println(result);

        result--;
        // result is now 0
        System.out.println(result);

        result++;
        // result is now 1
        System.out.println(result);

        result = -result;
        // result is now -1
        System.out.println(result);

        boolean success = false;
        // false
        System.out.println(success);
        // true
        System.out.println(!success);

    }

}
```

&emsp;&emsp;The increment/decrement operators can be applied before (prefix) or after (postfix) the operand. The code `result++;` and `++result;` will both end in result being incremented by one. The only difference is that **the prefix version (++result) evaluates to the incremented value, whereas the postfix version (result++) evaluates to the original value**.

```java
class PrePostDemo {

    public static void main(String[] args){

        int i = 3;
        i++;
        // prints 4
        System.out.println(i);
        ++i;               
        // prints 5
        System.out.println(i);

        // prints 6
        System.out.println(++i);
       
        // prints 6
        System.out.println(i++);

        // prints 7
        System.out.println(i);

    }
}
```

## 5.4 The Equality and Relational Operators

&emsp;&emsp;The equality and relational operators determine if one operand is greater than, less than, equal to, or not equal to another operand.

```java
class ComparisonDemo {

    public static void main(String[] args){
        int value1 = 1;
        int value2 = 2;
        if(value1 == value2)
            System.out.println("value1 == value2");
        if(value1 != value2)
            System.out.println("value1 != value2");
        if(value1 > value2)
            System.out.println("value1 > value2");
        if(value1 < value2)
            System.out.println("value1 < value2");
        if(value1 <= value2)
            System.out.println("value1 <= value2");
    }
}
```

> Note:  
> &emsp;&emsp;Keep in mind that we must use `==`, not `=`, when testing if two primitive values are equal.

## 5.5 The Conditional Operators

&emsp;&emsp;The `&&` and `||` operators perform Conditional-AND and Conditional-OR operations on two boolean expressions.

```java
class ConditionalDemo1 {

    public static void main(String[] args){
        int value1 = 1;
        int value2 = 2;
        if ((value1 == 1) && (value2 == 2))
            System.out.println("value1 is 1 AND value2 is 2");
        if ((value1 == 1) || (value2 == 1))
            System.out.println("value1 is 1 OR value2 is 1");
    }

}
```

> Note:  
> &emsp;&emsp;These operators exhibit "short-circuiting" behavior, which means that the second operand is evaluated only if needed.

## 5.6 The Type Comparison Operator `instanceof`

## 5.7 Bitwise and Bit Shift Operators

# 6 Control Flow Statements

## 6.1 If-Then and If-Then-Else

&emsp;&emsp;The **if-then** statement is the most basic of all the control flow statements. It tells our program to execute a certain section of code only if a particular test evaluates to true.

```java
void applyBrakes() {
    // the "if" clause: bicycle must be moving
    if (isMoving){
        // the "then" clause: decrease current speed
        currentSpeed--;
    }
}
```

&emsp;&emsp;If this test evaluates to false (meaning that the bicycle is not in motion), control jumps to the end of the if-then statement.

> Note:  
> &emsp;&emsp;The opening and closing braces are optional, provided that the "then" clause contains only one statement.

&emsp;&emsp;The **if-then-else** statement provides a secondary path of execution when an "if" clause evaluates to false. 

```java
class IfElseDemo {
    public static void main(String[] args) {

        int testscore = 76;
        char grade;

        if (testscore >= 90) {
            grade = 'A';
        } else if (testscore >= 80) {
            grade = 'B';
        } else if (testscore >= 70) {
            grade = 'C';
        } else if (testscore >= 60) {
            grade = 'D';
        } else {
            grade = 'F';
        }
        System.out.println("Grade = " + grade);
    }
}
```

## 6.2 While and Do-while

&emsp;&emsp;The **while** statement continually executes a block of statements while a particular condition is true. Its syntax can be expressed as:

```java
while (expression) {
     statement(s)
}
```

> Note:  
> &emsp;&emsp;The while statement evaluates expression, which must return a boolean value. If the expression evaluates to true, the while statement executes the statement(s) in the while block. The while statement continues testing the expression and executing its block until the expression evaluates to false.

&emsp;&emsp;Using the while statement to print the values from 1 through 10 can be accomplished as in the following WhileDemo program:

```java
class WhileDemo {
    public static void main(String[] args){
        int count = 1;
        while (count < 11) {
            System.out.println("Count is: " + count);
            count++;
        }
    }
}
```

&emsp;&emsp;The Java programming language also provides a **do-while** statement, which can be expressed as follows:

```java
do {
     statement(s)
} while (expression);
```

&emsp;&emsp;The difference between do-while and while is that do-while **evaluates its expression at the bottom of the loop instead of the top**. Therefore, the statements within the do block are always executed at least once.

## 6.3 For

&emsp;&emsp;The **for** statement provides a compact way to iterate over a range of values. Programmers often refer to it as the "for loop" because of the way in which it repeatedly loops until a particular condition is satisfied. The general form of the for statement can be expressed as follows:

```java
for (initialization; termination; increment) {
    statement(s)
}
```

&emsp;&emsp;When using this version of the for statement, keep in mind that:

* The initialization expression initializes the loop; it is executed once, as the loop begins.
* When the termination expression evaluates to false, the loop terminates.
* The increment expression is invoked after each iteration through the loop; it is perfectly acceptable for this expression to increment or decrement a value.

&emsp;&emsp;The three expressions of the for loop are optional; an infinite loop can be created as follows:

```java
// infinite loop
for ( ; ; ) {

    // our code goes here
}
```

&emsp;&emsp;The for statement also has another form designed for iteration through Collections and arrays. This form is sometimes referred to as the **enhanced for statement**, and can be used to make our loops more compact and easy to read.

```java
class EnhancedForDemo {
    public static void main(String[] args){
         int[] numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
         for (int item : numbers) {
             System.out.println("Count is: " + item);
         }
    }
}
```

> Note:  
> &emsp;&emsp;We are recommended to use this form of the for statement instead of the general form whenever possible.

## 6.4 Break

## 6.5 Continue

## 6.6 Return

# 7 Classes and Objects

## 7.1 Creating Classes

### 7.1.1 Declaring Classes




