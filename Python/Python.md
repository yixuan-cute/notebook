# 1 Python Baiscs

## 1.1 Variables

&emsp;&emsp;We can create a variable by assigning a value to a label using the equal sign or the assignment operator.

```python
name = "Xaiver"
age = 39
```

* A variable name can be composed of letters, numbers and even underscores but **it cannot start with a number**. And we can't use any other characters.
* A reserved keyword is something that is used to write python like `for`, `if`,`while`, `import` these are all  words that have very specific meanings within python, so **we cannot use them for a variable name**.
* If we are going to create a variable, we should be assigning it to a value or using a variable that already exists. A single newly created variable name in a line is not a Python code.

## 1.2 Expressions and Statements

&emsp;&emsp;An expression is any sort of code that returns a value.

```python
1+1
"Xaiver"
```

&emsp;&emsp;A program is formed by a series of statements and each statement is put on its own line like we have these two lines here, **but we can use a semicolon to have more than one statement on a single line**.

```python
# each statement is put on its own line
name = "Xaiver"
print(name)

# using a semicolon
name = "Xaiver"; print(name)
```

## 1.3 Comments

```python
# Everything after a hash mark is ignored.
# This is a inline comment.

"""
  This is a block comment.
"""
```

## 1.4 User Input

# 2 Operators

## 2.1 Arithmetic Operators

| Operator | Expression | Result ||
|:--------:|:----------:|:------:|:----:|
|    +     |   `1 + 1`  |    2   | plus |
|    -     |   `2 - 1`  |    1   | |
|    *     |   `2 * 2`  |    4   | times |
|    /     |   `5 / 2`  |   2.5  |   division    |
|    %     |   `4 % 3`  |    1   ||
|    **    |  `4 ** 2`  |   16   | set 4 to the power of 2|
|    //    |  `5 // 2`  |    2   | floor division|

&emsp;&emsp;We can use `round(5 / 2)` instead of `5 // 2`.

```python
5 // 2  # 2
round(5 / 2)  # 2
```

&emsp;&emsp;There is one other thing we can use plus `+` for, and that is to concatenate two different strings. 

```python
first = "Yixuan"
last = "Chen"

name = first + " " + last

print(name)
```

> Notice: Using plus sign, we can only concatenate str to str.

```python
name = "Yixuan Chen"
age = 19

print("name: " + name) # pass

print("age: " + age)  # error
print("age: " + str(age))  # pass
```

## 2.2 Assignment Operators

```python
num = 12  # assign 12 to num
```

&emsp;&emsp;We can combine the assignment operator to arithmetic operator.

```python
num += 10  # equivalent to num = num + 10
```

&emsp;&emsp;We can also do the same for the other arithmetic operators also.

```python
num -= 10  # equivalent to num = num - 10
num *= 10  # equivalent to num = num * 10
num /= 10  # equivalent to num = num / 10
```

## 2.3 Comparison Operators

```python
a = 1
b = 2
```

| Operator | Expression | Result |
|:--------:|:----------:|:------:|
|   ==     |  `a == b`  | False  |
|   !=     |  `a != b`  | Ture   |
|   >      |  `a > b`   | False  |
|   <      |  `a < b`   | True   |
|   >=     |  `a >= b`  | False  |
|   <=     |  `a <= b`  | Ture   |

## 2.4 Boolean Operators

## 2.5 Bitwise Operators

## 2.6 is & in Operators

# 3 Data Types

```python
name = "Xaiver"

# We can use a type() function to get a variable's data type.
print(type(name))  # str

# We can use a isinstance(variable_name, data_type) function to determine whether the variable is of the specified data type.
print(isinstance(name, str))  # True

# Functions above works same for other data types.
```

## 3.1 Strings

## 3.2 Number Data Types

## 3.3 Booleans

## 3.4 Enums

## 3.5 Lists

## 3.6 Tuples

## 3.7 Dictionaries

## 3.8 Sets

# 4 Control Statements

# 5 Functions


