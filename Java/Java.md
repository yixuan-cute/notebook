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

> Note: The name we choose must not be a keyword or reserved word.

3. If the name we choose consists of only one word, spell that word in all lowercase letters. If it consists of more than one word, capitalize the first letter of each subsequent word.

> Note:  
> &emsp;&emsp;The names gearRatio and currentGear are prime examples of this convention.  
> &emsp;&emsp;If our variable stores a constant value, such as `static final int NUM_GEARS = 6`, the convention changes slightly, capitalizing every letter and separating subsequent words with the underscore character. By convention, **the underscore character is never used elsewhere**.

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

&emsp;&emsp;Primitive types are special data types built into the language; they are not objects created from a class. A literal is the source code representation of a fixed value; literals are represented directly in our code without requiring computation.

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

&emsp;&emsp;**A floating-point literal is of type `float` if it ends with the letter F or f(32-bit float literal); otherwise its type is `double` and it can optionally end with the letter D or d (64-bit double literal; this is the default and by convention is omitted).**

&emsp;&emsp;The floating point types can also be expressed using E or e (for scientific notation):

```java
double d1 = 123.4;

// same value as d1, but in scientific notation
double d2 = 1.234e2;
```

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
> &emsp;&emsp;However, convention discourages this form; the brackets identify the array type and should appear with the type designation.

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



# 6 Control Flow Statements

