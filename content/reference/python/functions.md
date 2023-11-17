---
title: 'Python Functions'
date: 2023-11-16T18:34:26-08:00
draft: true

description: 'Basic reference on python functions'
author: 'Matthew Reese'
---

## Introduction

Functions in Python are similar in both concept and syntax to most other high-level programming languages. They provide a clean way to abstract code into various subroutines, or to implement some other paradigm out of the vast number supported.

## Rudiments

### Syntax Basics

A function in python is defined using the **def** keyword. Following this is the function name, then a pair of parenthesis `()`, containing any parameters. At the end of the line is a colon `:`

```python
def hello():
    print("Hello World!")
```

1. {{< highlight python "hl_inline=true" >}}def hello():{{< /highlight >}} defines the header of the function **hello** with no parameters.
2. {{< highlight python "hl_inline=true" >}}print("Hello World!"){{< /highlight >}} is the only statement in the body of the function.

Calling a function is done by placing parenthesis and any parameters after the name of the function. For example:

```python
hello()
# > Hello World!
```

Calls the function **hello**

### Parameters

If functions were limited solely to the data created within their own scope, they wouldn't be a very useful construct. *Parameters* allow the caller of a function to pass in data to be read or transformed.

Below are two examples

```python
def print_n_times(message, n):
    for _ in range(n):
        print(message)

print_n_times('snakes', 3)
# > snakes
# > snakes
# > snakes
```

```python
def print_square(n=10):
    print(f'{n} squared = {n * n}')

print_square()
# > 10 squared = 100
print_square(4)
# > 4 squared = 16
```

`print_n_times(message, n)` rather intuitively, prints a **message**, **n** number of times.

`print_square(n)` makes use of *default arguments*, allowing the caller to not specify those arguments, allowing the default value of 10 to be passed in.

> IMPORTANT: Default parameters must be specified **after** all normal parameters, or else the code will exit with an error!

### Return Values

Not only can functions receive data they can also send some back to the caller. Using the **return** statement, functions may pass back data in the form of *any type*. Here is an illustration of this behavior:

```python
def weird(n):
    if n > 1:
        return 'yay'
    elif n < 0:
        return 1.212
    else:
        return weird
```

In most circumstances, a function that has paths branching to multiple possible return types is a very bad idea. Imagine that you need to call a function like this; parsing the return value will be very difficult and prone to error.

With the freedom that python permits, it is remarkably easier to return *multiple values* from a function than in a language like C++. There are several to do this using **lists**, **dicts** or even user-defined types, but the simplest is to return a **tuple** holding the return values. Below is an implementation of that idea, for a function calculating the number of days, hours, and minutes in a given number of seconds.

```python
def get_time_period(seconds):
    days = seconds // 86400
    hours = seconds % 86400 // 3600
    minutes = seconds % 3600 // 60

    return (seconds % 60, minutes, hours, days)

get_time_period(180_122) # 2 days, 2 hours, 2 minutes, and 2 seconds
# > (2, 2, 2, 2)
```

Looking at this, the usefulness of returning multiple values at once is clear, but these values still need to be accessible somehow. One approach might be to set the output of the function to a single variable like `t = get_time_period(180_122)`. Then, when individual values are needed, they can be accessed using subscript notation as follows: `secs = t[0]`, `mins = t[1]`, $\cdots$ This solution however, is innately inelegant when python's support for *variable unpacking* is considered. Here is a much cleaner way of obtaining the returned values, all at once:

```python
secs, mins, hours, days = get_time_period(180_122)
```

Each variable is assigned to its respective element from the returned tuple. Note that the order in which they are assigned is **very relevant**; if the function instead returned values in the order of `(days, hours, minutes, seconds)` the order of variables on the LHS of the assignment operator would need to be adjusted accordingly.

___

## *\*args* and *\*\*kwargs*

If needed, functions can be written to take an arbitrary number of arguments using `*args`, or even an arbitrary number of keyword arguments using `**kwargs`. Beginning with `*args`, it functions to *pack* the arbitrary arguments passed to the function, into a data structure that can be used. Instead of unpacking the values from a returned tuple, as was done in the prior section, `*args` will place all arguments it receives into a tuple. The names `*args` and `**kwargs` may be anything, however, convention dictates that a variable list of arguments should be `*args` or `*argv`, while a variable list of keyword arguments is `**kwargs`.

One example of where you've likely used `*args` before is the built-in `print()` function. It accepts any number of arguments that passed in, printing each to stdout in order. Many other built-in functions make use of the argument list. An example implementation of `minimum` (similar to the builtin `min` function) is below.

```python
def minimum(*args):
    min_value = args[0]
    for arg in args:
        if arg < min_value:
            min_value = arg
    return min_value

minimum(1, 8, 6, -3, -2)
# > -3
```

`**kwargs` works in a similar fashion, except that instead of packing the values into a **tuple**, they are packed into a **dict**. Keyword arguments are also the only type of arguments parsed. Understand that plain old normal arguments, `*args`, keyword arguments and `**kwargs` can all be utilized in the same function. Due to the nature of how arguments are parsed, they **must** appear in that order. Below is an example demonstrating this idea. While this may be perfectly legal programmatically, using all of these in a function is certainly not advisable as the code will not be easy to read or understand.

```python
def print_all(a, b, *args, key_c, key_d, **kwargs):
    print(f'a = {a} | b = {b}')
    print('args =', args)
    print(f'key_c = {key_c} | key_d = {key_d}')
    print('kwargs =', kwargs)

print_all(2, 'bell', 8, 7, 6, key_d='c', key_c=3.1415, key_z=10, key_y=12)
# > a = 2 | b = bell
# > args = (8, 7, 6)
# > key_c = 3.1415 | key_d = c
# > kwargs = {'key_z': 10, 'key_y': 12}
```

## Recursive Functions

Python, like many other languages, allows for a function to be executed within its own block, or called *recursively*. This may seem strange at first, so it's best explained by an example.

```python
def summation_to_n(n):
    if n <= 0:
        return 0
    
    return n + summation_to_n(n - 1)

summation_to_n(6) # => 6 + 5 + 4 + 3 + 2 + 1 + 0
# > 21
```

This function computes the result of the equation $\sum_{i=0}^{n} {i}$ for a given natural number *n*. The conceptual aspects of this idea will not be covered on this page, but know that recursion has many applications in algorithmic design.

## Lambdas

Lambdas may sound like a complex, high-level mathematical term, but they are actually remarkably simple to understand in python. Simply put, lambdas are a concise way of writing *anonymous functions*. *Anonymous* in this context means that the function exists in the program but does not have a proper name to be referred to by. Consider the function `add(a,b)` which returns the sum of $a+b$, rewritten as a lambda function.

```python
def add(a, b):
    return a + b

lambda a, b : a + b
```

That's it. That's how simple the syntax of a lambda is: the keyword **lambda**, a list of arguments, then a single statement that handles all necessary computations and returns the result. Currently, the lambda in the program above is completely accessible. Using a variable, we can store a reference to the lambda function and then treat that variable as if it were the name of a function. See below:

```python
adder = lambda a, b : a + b

adder(1, 2) # -> 3
adder('a', 'c') # -> 'ac'
```

Now that you understand the syntax, what are lambda's useful for? They generally are passed as arguments to higher-order functions or returned from functions themselves. The applications of these two ideas are well beyond the scope of this page, but I will provide one example of the usefulness of the compact nature of lambdas when used in conjunction with higher-order functions.

```python
data = [1, 2, 3, 4]

map(lambda x : x * x, data)
# > [1, 4, 9, 16]
```

## Conventions

Refer to the [PEP 8](https://peps.python.org/pep-0008) style guide.