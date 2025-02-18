---
icon: repeat
---

# Python Course - Control Flow & Loops

## Comparison operators

<table><thead><tr><th width="217">Operator</th><th>Meaning</th></tr></thead><tbody><tr><td><code>==</code></td><td>Equal</td></tr><tr><td><code>!=</code></td><td>Not equal</td></tr><tr><td><code>&#x3C;</code></td><td>Less</td></tr><tr><td><code>></code></td><td>More</td></tr><tr><td><code>&#x3C;=</code></td><td>Less or equal</td></tr><tr><td><code>>=</code></td><td>More or equal</td></tr></tbody></table>

{% hint style="warning" %}
Do not confuse the `=` symbol which is used to assign a variable and the `==` operator which is used to compare values.
{% endhint %}

## Boolean operators

There are three boolean operators : `and`, `or` and `not`.

Here are some examples adding [comparison operators](pyco-a2.md#comparison-operators) and [mathematical operators](pyco-a1.md#mathematical-operators) :

```python
(4 < 5) and (5 < 6)                              # True
(1 == 2) or (2 + 3 == 2)                         # False
2 + 2 == 4 and not 2 + 2 == 5 and 2 * 2 == 2 + 2 # True
(5 > 4 or 3 < 4) and 5 > 5                       # False
```

{% hint style="info" %}
The keyword `or` doesn't mean _"or"_ but _"and/or"_.
{% endhint %}

## Keywords `if`, `else` and `elif`

The `if` keyword checks if the provided expression is true (condition met). If yes, the indented code is executed. If not, the indented statements after `else` are executed. Finally, `elif` can be placed in between to act as an _"else if"_. There can be several.

<pre class="language-python"><code class="lang-python"># The user is asked to create a name.
username = input("Create your username.")

<strong># We check if it is incorrect. In this case, we give him the reason.
</strong><strong>if username == "admin" or username == "administrator" :
</strong>    print("This username is not allowed.")
    print("This is an impersonation of the owner of the software.")
elif username == "me" :
    print("You have no right to call yourself that.")
    print("This could be confusing.")
elif username = "" :
    print("Please enter text : your name cannot be empty.")

# Otherwise, a welcome message is displayed.
else :
    print("Welcome,", username, "!")
</code></pre>

{% hint style="info" %}
Understand that the 1st `elif` statement will only execute if the `if` statement evaluates to false, the 2nd elif will only evaluate its expression to true if the two previous ones evaluated theirs to false. Obviously, the indented code after `else` will only execute if all the expressions in the `if` and `elif` statements are false.
{% endhint %}

## Ternary operator

The ternary operator is a way to compact an _"if else"_ into a single line. It returns a value that can be displayed or assigned to a variable for example. It has a slightly different construction that we will see with the help of this code snippet.

```python
age = input("Enter your age : ")

if age < 18 :
    print("kid")
else :
    print("adult")

# is equivalent to

print("enfant" if age < 18 else "adulte")
```

It does not natively support `elif` even though it can be used by chaining several ternary operators.

```python
age = input("Enter your age : ")

if age < 13 :
    categorie = "kid"
elif age < 18 :
    categorie = "teen"
else :
    categorie = "adult"

# is equivalent to

categorie = "kid" if age < 13 else "teen" if age < 18 else "adult"
```

## Keywords `match` and `case`

The _"switch-case"_ flow control is used to take an action based on the value of a variable quickly and efficiently.&#x20;

Let's take the HTTP protocol status codes as an example.

```python
match response_code : # This code snippet displays the meaning of the status code
    case 200 :        # contained in the response_code variable.
        print("OK")
    case 201 :
         print("Created with Success")
    case 300 :
        print("Multiple Choice Redirect")
    case 307 :
        print("Temporary Redirection")
    case 404 :
        print("Page Not Found")
    case 500 :
        print("Internal Server Error")
    case 502 :
        print("Bad Gateway")
```

{% hint style="warning" %}
Keep in mind that as soon as a condition is met, we skip all the indented code following `match`.
{% endhint %}

This snippet can be modified using two features :&#x20;

* The `or` which allows to execute the same code for several cases. It can also be written as `|`.
* The `_` case is a default case if none of the others match.

```python
match response_code:
    case 200 | 201 :
        print("OK")
    case 300 | 307 :
        print("Redirection")
    case 404 :
        print("Bad Request")
    case 500 | 502 :
        print("Internal Server Error")
    case _ :
        print("Invalid Code")
```

{% hint style="info" %}
It is a good practice and sometimes even essential to place the default case (`case _`) last.
{% endhint %}

## `while` loop

A `while` loop is used to execute code in a loop as long as the condition is met.

```python
counter = 0
while spam < 5 :
    print("Hello")
    counter += 1 # We increment the variable
# This code will display "Hello" 5 times
```

You can also make endless loops.

```python
notes = ""
while True :
    new_note = input("Type a new note : ") # input() allows the system to
                                           # not execute code to its full
                                           # capacity by pausing.
    notes += new_note + " ; "
    print(notes)
```

{% hint style="danger" %}
Using endless loops can be problematic. In code like the one below, _"Hello"_ will be printed as many times as possible, which will drain all the resources of the computer and may even cause it to crash.

```python
while True :
    print("Hello")
# This code is dangerous and may crash.
```

This is why such loops should only be used with wait functions inside them like `input()` or `time.sleep()` (which we will see later).
{% endhint %}

## `for` loop

A `for` loop allows you to process or use each element of a compound object. The only one we have learned so far is `str`. Note that each character is an element in its own right.

Here is a program that removes all spaces in a text. It will therefore have to process the characters one by one.

```python
text = "Hello, I am a Python developer." # We define the
result = ""                              # input values

for c in text :     # Puts the character in the variable "c" at each iteration
    if c != " " :   # Check that this character is not a space
        result += c # In this case, we add it to the result

print(result) # At the end of the loop, the result is displayed

# Will give "Hello,IamaPythondeveloper."
```

## Keywords `break` and `continue`

### `break`

Imagine an endless loop (or not) from which you would like to exit. The `break` statement allows you to immediately exit the loop without even completing the cycle.

```python
while True :
    entry = input("Type exit to exit the loop : ")
    if  entry == "exit" :
        break
print("Congratulations, you get out of the loop !") # this line will not be
                                                    # executed until break
                                                    # is called
```

### `continue`

The `continue` keyword immediately returns to the beginning of a new loop cycle. As an example, we will take this authentication system.

```python
while True :
    name = input("Who are you ? ")
    if name != "Bob" :
        continue # Here, no need to display the password prompt
    password = input("Password : ")
    if password == "1234" : # We exit the loop to display the access granted
        break               # message if the password is correct
print("Access granted.")
```

{% hint style="info" %}
Note that the `break` and `continue` keywords can be used on both `for` and `while` loops.
{% endhint %}
