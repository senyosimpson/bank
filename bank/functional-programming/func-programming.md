# Functional Programming

Functional programming is a programming paradigm. Functional programming core construct is the function. Programs are built from composing multiple pure functions together. Given this structure, functional programming does not maintain or mutate state. This is in stark contrast to object-oriented programming where code is built around objects that have state and that can be mutated.

## Core Tenets

The core tenets of functional programming are

* Pure functions
* No side effects
* Immutability
* Function composition
* First-class functions
* Referential transparency

### Pure Functions

Pure functions are functions that return the same output for a given input. An example of a pure function is

```python
def square_area(x):
    return x * x
```

This function will *always* give the same output if the same input is given no matter how many times it is invoked. The other important aspect of a pure function is that is has no side effects (i.e it does not mutate state).

### No Side Effects

Side effects occur when a function mutates state out of its context. Side effects make it harder to reason about code since it is not always easy to understand the flow of data. Example of side effects are reading or writing files, updating databases, creating database connections, so on and so forth. Naturally, functional programs cannot completely rid themselves of side effects, however, they are often separated from the data and are integrated in a principled manner. An example of a function with side effects

```python

def add_numbers(a, b):
    num = a + b
    update_database(num)    
    return num
```
This example, while ridiculous, adequately highlights a side effect. When adding the numbers, a database is updated with a value of that number. This is a side effect and the outcome of the function every time it is executed is actually different considering it is adding data to a database. The reason that this can be difficult to reason about is that the function gives no indication such an effect would occur.


### Immutability

Functional programming relies heavily on immutability. This means once declared, structures cannot be modified. For example in the object-oriented paradigm, you can do

```python
x = 1
x = x + 1
```
This is not possible in functional programming. In functional programming we can create a *new* variable but we can't update an already instantiated variable. This, again, brings the benefit of making it easier to reason about code and understand the flow of data through a program. 