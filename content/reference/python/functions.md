---
title: 'Functions'
date: 2023-11-16T18:34:26-08:00
draft: true

description: 'Basic reference on python functions'
author: 'Matthew Reese'
---

## Introduction

Functions in Python are similar in both concept and syntax to most other high-level programming languages. They provide a clean way to abstract code into various subroutines, or to implement some other paradigm out of the vast number supported.

## Rudiments

### Denotative Statements

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
def printNTimes(message, n):
    for _ in range(n):
        print(message)

printNTimes('snakes', 3)
# > snakes
# > snakes
# > snakes
```

```python
def printSquare(n=10):
    print(f'{n} squared = {n * n}')

printSquare()
# > 10 squared = 100
printSquare(4)
# > 4 squared = 16
```

`printNTimes(message, n)` rather intuitively, prints a **message**, **n** number of times.

`printSquare(n)` makes use of *default arguments*, allowing the caller to not specify those arguments, allowing the default value of 10 to be passed in.

> IMPORTANT: Default parameters must be specified **after** all normal parameters, or else the code will exit with an error!

### Return Values

Not only can functions receive data, they can also send some back whence to the caller. Using the **return** statement, functions may pass back data in the form of *any type*. Here is an illustration of this behavior:

```python
def weird(n):
    if n > 1:
        return 'yay'
    elif n < 0:
        return 1.212
    else:
        return weird
```

In most circumstances, a function that has paths branching to multiple possible return types is a very bad idea.

TODO: More stuff

___

## *\*args* and *\*\*kwargs*

## Recursive Functions

## Syntactic Definitions

## Conventions
