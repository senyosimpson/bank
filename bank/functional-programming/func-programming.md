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
This example, while simple, adequately highlights a side effect. When adding the numbers, a database is updated with a value of that number. This is a side effect and the outcome of the function every time it is executed is actually different considering it is adding data to a database. The reason that this can be difficult to reason about is that the function gives no indication such an effect would occur.


### Immutability

Functional programming relies heavily on immutability. This means once declared, structures cannot be modified. For example in the object-oriented paradigm, you can do

```python
x = 1
x = x + 1
```
This is not possible in functional programming. In functional programming we can create a *new* variable but we can't update an already instantiated variable. This, again, brings the benefit of making it easier to reason about code and understand the flow of data through a program. 


### Function Composition

Function composition is the act of combining multiple (simple) functions to build more complex functions. Since functions are at the center of functional programming, as well as a focus on purity and mitigating side effects, it lends itself to the creating multiple small functions which are then combined into bigger functions. Looking at a trivial example - suppose we take the mean of a set of integers. We can consider this the result of two functions, one is to add all the elements and the other is to count how many elements there are. Using the two functions,  we can easily compute the mean. For the sake of verbosity, the functions are custom defined.

```python
def add(numbers):
    out = 0
    for n in numbers:
        out += n
    return out

def count(numbers):
    out = 0
    for _ in numbers:
        out += 1
    return out

def mean(numbers):
    return add(numbers) / count(numbers)
```

This is function composition at work. We have combined the functions `add` and `count` to create another function `mean`.


### First-class Functions

In simple terms, first-class functions are functions that are treated as variables. This means they can be passed into other functions as arguments, be returned from functions and be saved in variables. First-class functions allow developers to create higher-level with abstractions with functions alone and enables function composition. A simple example once again using the mean. Suppose we want to calculate the mean using one of three mean functions: harmonic mean, arithmetic mean or geometric mean. Using first-class functions we could do it in this way

```python
def arithmetic_mean(numbers):
    pass

def harmonic_mean(numbers):
    pass

def geometric_mean(numbers):
    pass

def mean(mean_fn, numbers):
    return mean_fn(numbers)

# using harmonic mean
mean(harmonic_mean, numbers)

# we can also assign the fn a variable and use
g_mean = geometric_mean
mean(g_mean, numbers) 
```
Here, the mean function is passed into `mean` which actually does the calculation. In the second example, the function `geometric_mean` is assigned to a variable `g_mean` and that is passed into the function. This highlights some attributes of first-class functions.

### Referential Transparency

Referential transparency is when a function can be replaced with the value it returns without changing the program's behaviour. This is dependent on the fact that functions are *pure*. Breaking function purity breaks referential transparency. The main advantages it brings are that it makes code easier to reason about, test, refactor and optimize. A simple example of a referentially transparent function is an addition function

```python
def add(a, b):
    return a + b
```
We can replace that function with its return value and the calling program will still function the same.

```python
a = add(2, 2)
b = add(a, a)
if b == 8:
    print('Sum function works')
else:
    print('Error in sum function')

# prints: sum functions works
```
It is clear that if we replace `a` with `4`, the program would work the same, printing `sum function works`. Now imagine we defined the `add` functions as 

```python
def add(a, b):
    print(f'Adding {a} and {b}')
    return a + b
```
In this case, the program would first print `Adding 2 and 2` and then `sum function works`. If we replaced `a` with `4`, we would not get the first message. This has altered the program and therefore it is not referentially transparent.

## References

1. [What are first-class functions](https://lispcast.com/what-are-first-class-functions/)
2. [Why functional programming](https://sookocheff.com/post/fp/why-functional-programming/)
3. [Core functional programming concepts](https://thecodeboss.dev/2016/12/core-functional-programming-concepts/)
4. [An introduction to the basic principles of functional programming](https://www.freecodecamp.org/news/an-introduction-to-the-basic-principles-of-functional-programming-a2c2a15c84/)
