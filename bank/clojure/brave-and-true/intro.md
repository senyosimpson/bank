# Introduction to Clojure

## Lein

## REPL

## Building a project

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
; => 6
(str "hello" "world")
; => hello world
```