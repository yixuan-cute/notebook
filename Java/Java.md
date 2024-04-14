# 1 Getting Started with Java

## 1.1 Downloading and setting up JDK for Linux/x64

1. Click <a href="https://www.oracle.com/java/technologies/downloads/" target="_blank">oracle jdk</a> to download Oracle JDK.

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

&emsp;&emsp;A Java class must be saved in a file that has the same name as the class with the extension `.java`. This is mandatory and is in fact very convenient.

&emsp;&emsp;We can give this class any name as long as it does not start with a number. There is a convention though: **the name of a Java class starts with a capital letter**. This is not mandatory but all Java developers follow this convention.

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

> Note: In the Java programming language, the terms "field" and "variable" are both used.

The Java programming language defines the following kinds of variables:

* Instance Variables (Non-Static Fields)
* Class Variables (Static Fields)
* Local Variables
* Parameters

&emsp;&emsp;Having said that, there are the following general guidelines when discussing fields and variables: If we are talking about "fields in general" (excluding local variables and parameters), we may simply say "fields". If the discussion applies to "all of the above", we may simply say "variables".

## 2.2 Naming variables

The rules and conventions for naming our variables can be summarized as follows:

1. A variable's name can be any legal identifier — an unlimited-length sequence of Unicode letters and digits, beginning with a letter, the dollar sign `$`, or the underscore character `_`.
    * The convention, however, is to always begin our variable names with a letter, not `$` or `_`. Subsequent characters may be letters, digits, dollar signs, or underscore characters. Additionally, the dollar sign character, by convention, is never used at all.
    * A similar convention exists for the underscore character; while it's technically legal to begin our variable's name with `_`, this practice is discouraged.
    * White space is not permitted.
2. When choosing a name for our variables, use full words instead of cryptic abbreviations. Doing so will make our code easier to read and understand.
    * The name we choose must not be a keyword or reserved word.
3. If the name we choose consists of only one word, spell that word in all lowercase letters. If it consists of more than one word, capitalize the first letter of each subsequent word.
    * The names gearRatio and currentGear are prime examples of this convention.
    * If our variable stores a constant value, such as `static final int NUM_GEARS = 6`, the convention changes slightly, capitalizing every letter and separating subsequent words with the underscore character. By convention, **the underscore character is never used elsewhere**.

# 3 Creating Primitive Type Variables

## 3.1 Primitive types

&emsp;&emsp;The Java programming language is statically-typed, which means that all variables must first be declared before they can be used. This involves stating the variable's type and name, as we have already seen:

```java
int gear = 1;
```

&emsp;&emsp;A variable's data type determines the values it may contain, plus the operations that may be performed on it.

&emsp;&emsp;In addition to `int`, the Java programming language supports seven other primitive data types. **A primitive type is predefined by the language and is named by a reserved keyword**.

The eight primitive data types supported by the Java programming language are:

1. `byte`: An 8-bit signed two's complement integer. ($-128$ ~ $127$)
2. `short`: A 16-bit signed two's complement integer. ($-32768$ ~ $32767$)
3. `int`: A 32-bit signed two's complement integer. ($-2^{31}$ ~ $2^{31}-1$)
4. `long`: A 64-bit two's complement integer. ($-2^{63}$ ~ $2^{63}-1$)
5. `float`: A single-precision 32-bit IEEE 754 floating point.
6. `double`: A double-precision 64-bit IEEE 754 floating point.
7. `boolean`: The boolean data type has only two possible values: `true` and `false`.
8. `char`: A single 16-bit Unicode character. It has a minimum value of `\u0000 (or 0)` and a maximum value of `\uffff (or 65,535 inclusive)`.

## 3.2 Initializing a variable with a default value

## 3.3 Creating values with literals

## 3.4 Literals

## 3.5 Using `var` type indentifier

# 4 Creating Arrays

# 5 Using Operators

# 6 Control Flow Statements



我们家一个亲戚推荐的，叫什么



