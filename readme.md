# Epic Python Cheatsheet

## Variables

A variable has a value (that can change). Variables can be modified, in many different ways.

### Basic types

Basic types only have a single value. There is nothing more to them than the basic value they hold.
It is generally possible to convert between basic types if it makes sense, e.g. `str(5)` returns the value `5`.

A **boolean** is a true or false value. Convert to it using `bool(x)`.

```python
x = True

print(x) # prints "True"
print(x == False) #prints "False"
```

An **integer** is a whole number value, either positive or negative. Convert to it using `int(x)`.

```python
x = 5

print(x + 5) # prints "10"
print(x - 11) # prints "-6"
print(x * 6) # prints "30"
print(x / 2) # prints "2" ... note that dividing an integer makes another integer
print(float(x) / 2) #prints "2.5" (correct)
```

A **float** is a number with a fraction part. Convert to it using `float(x)`.

```python
x = 4.5
print(x + 5) # prints "9.5"
...
print(x / 2) # prints "2.25"
```

A **string** is a collection of characters, also known as text. Convert to it using `str(x)`. 

You can also think of it as a **readonly** (you can't change it) list, so you can iterate over it using a `for __ in __` structure, but you can't assign new values.

```python
greeting = "hello"
name = "Josh"

print(greeting + name  + "!") # prints "helloJosh!"
```

### Complex types

Complex types have more to them, as they have values within them that you can access.

A **list** is an ordered set. You can access a value in a list by using square brackets `[]` after the variable name.
Lists can be **iterated over** (gone through) using the `for __ in __` structure.

```python
a_list = ["apple", "banana", "pear"]
a_list[0] # has the value "apple"
a_list[1] # has the value "banana"
a_list[2] # has the value "pear"

for fruit_element in a_list:
    print(fruit_element)

# prints:
# "apple"
# "banana"
# "pear"
```

A **dict** is a map of keys to values. Think of it like an actual dictionary, where you can look up a definition (value) using the word (key).
You can access a value in a list by using square brackets `[]` after the variable name.

You can't use `for __ in __` for dicts, because it doesn't make sense, but you can check whether a value is a key or value using the `.keys()` and `.values()`
methods.

```python
banana_info = {"color": "yellow", "amount": 5, "is_fruit": True}
banana_info["color"] # has the value "yellow"
banana_info["amount"] # has the value 5
banana_info["is_fruit"] # has the value True

banana_info.keys() # returns a list of all keys in the dictionary
banana_info.values() # returns a list of all values in the dictionary
```

## Operators

Some operators make something happen.

| Symbol | Name           | Description                                                     | Syntax                     | Compatible types   |
| ------ | -------------- | --------------------------------------------------------------- | -------------------------- | ------------------ |
| `=`    | Assignment     | Assigns the variable on the LHS to the value on the RHS.        | `my_var = 5`               | all types          |

Some operators 'return', or evaluate to, a value.

| Symbol | Name           | Description                                                     | Syntax                     | Evaluates to   | Compatible types   |
| ------ | -------------- | --------------------------------------------------------------- | -------------------------- | -------------- | ------------------ |
| `==`   | Equality       | Returns whether the left value is equal to the right value.     | `my_var == 5`              | `boolean`      | all types          |
| `+`    | Addition       | Adds the left value and the right value.                        | `5 + 2` or `"hel" + "lo"`  |`float` or `int`| int, float, string |
| `-`    | Subtraction    | Subtracts the left value by the right value.                    | `17 - 12`                  |`float` or `int`| int, float         |
| `*`    | Multiplication | Multiplies the left value and the right value.                  | `6 * 10`                   |`float` or `int`| int, float         |

## Functions

Functions are blocks of code that can be 'called' (run) using parentheses `()` after the function name. Functions are actually just like any other kind of
variable, but they're defined differently.

```python
def say_beans():
    print("I say: beans")

say_beans() # prints "I say: beans"
```

Values can be 'passed in' through the parentheses into the function code.

```python
def say(phrase):
    print("I say: " + phrase)

say("hello") # prints "I say: hello"
say("kill me now") # prints "I say: kill me now"
```

Functions can also 'return' a value, which means that the function ends up as a value after it's called.

```python
def add_two_numbers(x,y):
    return x + y

a = 2
b = 5

add_two_numbers(a,b) # does nothing
c = add_two_numbers(a,b) # assigns the return value to the variable 'c'

print(c) # prints "7"
```

Variables can 'have' functions and variables inside them, which can be accessed with `.` after the variable name.

In VSCode you can often look at the functions available through pressing `CTRL-Space`.

```python
my_string = "hey there!"
my_string_uppercase = my_string.upper()

print(my_string) # prints "hey there!"
print(my_string_uppercase) # prints "HEY THERE!"
```

## Controlling the flow of the program

### Conditional ( `if` )

Programming conditionals take the following form.

1. if *condition*, do this
2. else if *condition*, do this
3. else, do this

```python
if x:
    # runs if x is True
elif y:
    # runs if x is False and y is True
elif z:
    # runs if x and y are False and z is True
else:
    # runs if x,y,z are all False
```

### Iteration ( `while`, `for` )

The `while` structure runs a block over and over again, while the condition is True.

```python
x = 0

while x < 5:
    print(x)
    x = x + 1

# prints:
# "0"
# "1"
# "2"
# "3"
# "4"
```

The `for` structure **iterates** (goes over) the elements of a list one at a time.

```python
xlist = [2,4,6,8,10,12]

for number in xlist:
    print(number)

# prints:
# "2"
# "4"
# "6"
# "8"
# "10"
# "12"
```

## Input and output

Use the `print(text)` function to output text. Note that it tries to automatically convert all other values to text.

```python
print("wow I'm output text")
print(56)

# prints:
# "wow I'm output text"
# "56"
```

Use the `input(prompt_text)` function to ask for input using the prompt. It returns the text input by the user (as a string).

```python
favorite_num_string = input("Type your favourite number: ")
print("Your favourite number is " + favorite_num_string)

# prints:
# "Type your favourite number: " (and waits for input, let's assume the number '56' is input)
# "Your favourite number is 56"
```
