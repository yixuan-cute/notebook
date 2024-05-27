# 1 Types and Declarations

&emsp;&emsp;Every name (identifier) in a C++ program has a type associated with it.

&emsp;&emsp;This type determines what operations can be applied to the name (that is, to the entity referred to by the name) and how such operations are interpreted. For example:

```cpp
float x;        // x is a floating-point variable
int y = 7;      // y is an integer variable with the initial value 7
float f(int);   // f is a function taking an argument of type int and returning a floating-point number
```

&emsp;&emsp;These declarations would make the example meaningful. Because **y** is declared to be an **int**, it can be assigned to, used as an operand for **+**, etc.

> Notes:  
> &emsp;&emsp;On the other hand, **f** is declared to be a function that takes an **int** as its argument, so it can be called given the interger **2**.

## 1.1 Types

&emsp;&emsp;C++ has a set of fundamental types corresponding to the most common basic storage units of a computer and the most common ways of using them to hold data.

### 1.1.1 Booleans

&emsp;&emsp;A Boolean, **bool**, can have one of the two values **true** or **false**, is used to express the result of logical operations. For example:

```cpp
void f(int a, int b)
{
    bool b1 {a==b};
    //If a and b have the same value, b1 becomes true; otherwise, b1 becomes false.
    // ...
}
```

&emsp;&emsp;By definition, **true** has the value **1** when converted to an integer and **false** has the value **0**.

&emsp;&emsp;Conversely, integers can be implicitly converted to **bool** values: nonzero integers convert to **true** and **0** converts to **false**. For example:

```cpp
bool b1 = 7;    // 7!=0, so b becomes true
bool b2 {7};    // error: narrowing (§2.2.2, §10.5)
int i1 = true;  // i1 becomes 1
int i2 {true};  // i2 becomes 1

if(1)
{
    cout << "an integer is converted to a boolean value implicitly" << endl;
    //This line is executed.
}
```

&emsp;&emsp;In arithmetic and logical expressions, **bool**s are converted to **int**s; integer arithmetic and logical operations are performed on the converted values. If the result needs to be converted back to **bool**, a **0** is converted to **false** and a nonzero value is converted to **true**. For example:

```cpp
bool a = true;
bool b = true;
bool x = a+b;   // a+b is 2, so x becomes true
bool y = a||b;  // a||b is 1, so y becomes true ("||" means "or")
bool z = a−b;   // a-b is 0, so z becomes false
```

&emsp;&emsp;A pointer can be implicitly converted to a **bool**. A non-null pointer converts to **true**; pointers with the value **nullptr** convert to **false**. For example:

```cpp
void g(int∗ p)
{
    bool b = p;             // narrows to true or false
    bool b2 {p!=nullptr};   // explicit test against nullptr
    
    if(p)  //equivalent to p!=nullptr
    {
        // ...
    }
}
```

### 1.1.2 Character Types

&emsp;&emsp;C++ provides a variety of character types that reflect that – often bewildering – variety:

&emsp;&emsp;`char`: The default character type, used for program text. A char is used for the implementation’s character set and is usually 8 bits.

`signed char`: Like char, but guaranteed to be signed, that is, capable of holding both positive and negative values.
* `unsigned char`: Like char, but guaranteed to be unsigned.

* `wchar_t`: Provided to hold characters of a larger character set such as Unicode (see §7.3.2.2). The size of wchar_t is implementation-defined and large enough to hold the largest character set supported by the implementation’s locale (Chapter 39).
* `char16_t`: A type for holding 16-bit character sets, such as UTF-16.
* `char32_t`: A type for holding 32-bit character sets, such as UTF-32.


1. Signed and Unsigned Characters

2. Character Literals

## 1.2 Declarations

## 1.3 Objects and Values

## 1.4 Aliases

# 2 Pointers, Arrays, and References

# 3 Structures, Unions, and Enumerations

# 4 Statements

# 5 Expressions

# 6 Select Operations

# 7 Functions

# 8 Exception Handling

# 9 Namespaces

# 10 Source Files and Programs




