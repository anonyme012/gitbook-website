---
icon: circle-play
---

# Python Course - Basics

## Mathematical operators

We'll start with some mathematics, the basis of computer science.

Here, in **descending order of priority**, are the arithmetic operators in Python :

<table><thead><tr><th width="129">Opérateur</th><th width="242">Opération</th><th>Exemple</th></tr></thead><tbody><tr><td><code>**</code></td><td>Exponent</td><td><code>3 ** 5 = 243</code></td></tr><tr><td><code>%</code></td><td>Modulo (remainder)</td><td><code>52 % 20 = 12</code></td></tr><tr><td><code>//</code></td><td>Integer division (euclidean)</td><td><code>52 // 20 = 2</code></td></tr><tr><td><code>/</code></td><td>Division</td><td><code>52 / 20 = 2.6</code></td></tr><tr><td><code>*</code></td><td>Multiplication</td><td><code>5 * 7.5 = 37.5</code></td></tr><tr><td><code>-</code></td><td>Subtraction</td><td><code>21 - 6 = 15</code></td></tr><tr><td><code>+</code></td><td>Addition</td><td><code>7 + 2 = 9</code></td></tr></tbody></table>

{% hint style="info" %}
Parentheses still take precedence as in mathematics and it must be kept in mind that the decimal separator of numbers in programming is the point (as in the English standards on which programming languages ​​are based).
{% endhint %}

```python
3.5 + 2 * 4   # 11.5

(3.5 + 2) * 4 # 22

6,2 + 8       # Will give (6, 10) because the interpreter will detect a tuple
              # (a type of object that we will discover later) which will give
              # an unexpected result.
```

## Data Types&#x20;

Computer science is about processing data of various types. Python developers have therefore provided different types of objects.

A chapter of this course is dedicated to that. You can find it here : [pyco-a3.md](pyco-a3.md "mention")

In the meantime, we will see the simplest and most used ones :

<table><thead><tr><th width="104">Nom</th><th width="396">Description</th><th>Exemple</th></tr></thead><tbody><tr><td><code>str</code></td><td>String (Unicode)</td><td><code>"Hello"</code> or <code>'Bye Bye !'</code></td></tr><tr><td><code>int</code></td><td>Signed integer (+ or -)</td><td><code>38</code></td></tr><tr><td><code>float</code></td><td>Signed decimal number</td><td><code>4.49529</code></td></tr><tr><td><code>bool</code></td><td>Boolean value (can only take 2 values : true or false)</td><td><code>True</code> or <code>False</code></td></tr></tbody></table>

## Variables

Now, let's move on to variables. They are used to store data in RAM for the duration of the program execution. This means that as soon as the program is closed, the data is deleted.

They can be used to store a number of an intermediate step in a process, a piece of data about the user, a constant, or anything else useful (or not).

Here are examples of variable declarations :

```python
name_of_the_variable = value

user_name = "Bob"

userAge = 21

darkMode = True
```

Variable names follow very specific standards :

* They can only contain letters, numbers and the underscore (`_`)
* They cannot start with a number
* They are case sensitive (difference between upper and lower case)
* Warning : accented characters (é, à, ù, ï, etc.) are not considered as letters

#### Writing conventions

There are also 2 main naming conventions : the "camel case" and the "snake case". Here are their differences :

```python
thisIsAVariableInCamelCase # Shorter but less readable
and_this_in_snake_case     # Longer but more readable
```

It's up to you to choose the one that suits you best.

#### Constants

Although Python does not have a built-in feature to define a constant (a variable that never changes), it is conventional to represent them with the all-caps "snake case" :

```python
PI = 3.14159265589793
ABSOLUTE_ZERO = -273.15
```

## The `print()` and `input()` functions

The user and the computer program need to be able to communicate with each other. These two functions will do that : `print()` displays text and `input()` allows the user to type text.

To learn more about what a function is, follow this link : [pyco-a4.md](pyco-a4.md "mention")

#### `print()`

This function can take multiple arguments of any type (not only `str`). The commas that separate the arguments insert spaces.

```python
print("Hello") # Hello
a = 12.36
b = False
print("Bye", a, b) # Bye 12.36 False
```

#### `input()`

This function takes user input and returns it as a string.

```python
user_age = input("How old are you ? ") # Will store the entry in the
                                       # variable "user_age"
```

#### Example

```python
name = input("Type your name : ") # This will display "Type your first name : "
                                  # (without the quotes) and allow the user to
                                  # type in text which will then be put into
                                  # the "name" variable.

print("Hello,", name, "!") # Will display the string passed as an argument.

# If I typed "anonyme012", then the program would write "Hello, anonyme012 !"
```

## Comments

Comments have no real use for a computer. They are used to explain how a complex piece of code works, explain the purpose of a variable, or indicate the author of the script.

This is a very good practice to adopt for your first programs. Think of another developer or even yourself wondering about the functioning of a problematic piece of code to be modified. Although it is slightly time-consuming when initially writing, it will save you hours of maintenance.

#### Line comment

```python
# Hello. This is a comment !
```

#### Multiline comment

```python
# And this
# one is
# multiline.
```

#### Comment with code

```python
user_age = 2025 - year_of_birth # This line calculates the user's age
```

## String Concatenation & Replication

We will see the simplest methods of string manipulation: concatenation and replication.&#x20;

To do this, we simply use the mathematical operators `+` and `*`. It also works with variables.

```python
greeting = "Hello"

sentence = greeting + "and all" # will give "Helloand all"

goodbye_text = "Bye ! " * 5 # will give "Bye ! Bye ! Bye ! Bye ! Bye ! "
```

{% hint style="info" %}
See here that it is indeed _"Helloand all"_ and not _"Hello and all"_ that is saved in the `sentence` variable. This is why when you concatenate strings with the `+`, you must add a space at the end or at the beginning of one of them.
{% endhint %}

## Assignment Operators

In addition to the `=` sign, there are various variable assignment operators.

#### Opérateurs d'assignation mathématiques

<table><thead><tr><th width="222">Opérateur</th><th>Équivalent</th></tr></thead><tbody><tr><td><code>var += 1</code></td><td><code>var = var + 1</code></td></tr><tr><td><code>var -= 1</code></td><td><code>var = var - 1</code></td></tr><tr><td><code>var *= 1</code></td><td><code>var = var * 1</code></td></tr><tr><td><code>var /= 1</code></td><td><code>var = var / 1</code></td></tr><tr><td><code>var //= 1</code></td><td><code>var = var // 1</code></td></tr><tr><td><code>var %= 1</code></td><td><code>var = var % 1</code></td></tr><tr><td><code>var **= 1</code></td><td><code>var = var ** 1</code></td></tr></tbody></table>

#### Opérateur de Walrus

This operator assigns a value while returning it.

```python
print(text := "Hi !") # displays "Hi !"

print(text) # still displays "Hi !" which shows that the variable 
            # has been assigned successfully

print(msg = "Voici mon message") # This will return either an error or a
                                 # boolean value if the variable already exists
```
