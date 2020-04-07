# Do Things: A Clojure Crash Course

## Syntax

### Forms

All Clojure code conforms to a uniform structure. There are two kinds of structures in Clojure

1. Literal representations of data structures (numbers, strings, maps, vectors)
2. Operations

All operations take the form

```clojure
(operator operand1 operand2 ... operandn)
```

Some examples

```clojure
(+ 1 2 3)
6
(str "hello" "world")
hello world
```

### Control Flow

The three basic control flow operators in Clojure are `if`, `do` and `when`.

#### if

The general structure of the `if` statement is as follows


```clojure
(if boolean-form
    then-form
    optional-else-form)
```

Some examples

```clojure
(if true
    "Hello"
    "World")
Hello

(if false
    "Hello"
    "World")
World
```
In the first example, it evaluated to true and therefore returned the first value (i.e the value in the true section of the definition). In the second, it evaluated to false and therefore returned the value defined in the `optional-else` portion of the definition. If you omit the `else` then it returns `nil`.

```clojure
(if false
    "Hello")
nil
```

#### do

The `do` operator evaluates expressions and returns the value of the last.

```clojure
(do
    (println "Hello World")
    (+ 2 3))
Hello World
5

(do
    (println "Hello World")
    (+ 2 3)
    (+ 1 1))
Hello World
2
```

From the example, it is clear that only the last value is returned. It executes every statement in the chain however and that is why `Hello World` is always printed (it's position is irrelevant)

#### when

The `when` operator is similar to a combination of `if` and `do`. It executes every command in the chain if some condition evaluates to true. However, it does not have an `else` statement and will return `nil` if the condition is false by default.

```clojure
(when true
    (println "Hello World")
    (+ 2 3))
Hello World
5

(when false
    (println "Hello World")
    (+ 2 3))
nil
```
