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
; => 6
(str "hello" "world")
; => hello world
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
; => Hello

(if false
    "Hello"
    "World")
; => World
```
In the first example, it evaluated to true and therefore returned the first value (i.e the value in the true section of the definition). In the second, it evaluated to false and therefore returned the value defined in the `optional-else` portion of the definition. If you omit the `else` then it returns `nil`.

```clojure
(if false
    "Hello")
; => nil
```

#### do

The `do` operator evaluates expressions and returns the value of the last.

```clojure
(do
    (println "Hello World")
    (+ 2 3))
Hello World
; => 5

(do
    (println "Hello World")
    (+ 2 3)
    (+ 1 1))
Hello World
; => 2
```

From the example, it is clear that only the last value is returned. It executes every statement in the chain however and that is why `Hello World` is always printed (it's position is irrelevant)

#### when

The `when` operator is similar to a combination of `if` and `do`. It executes every command in the chain if some condition evaluates to true. However, it does not have an `else` statement and will return `nil` if the condition is false by default.

```clojure
(when true
    (println "Hello World")
    (+ 2 3))
Hello World
; => 5

(when false
    (println "Hello World")
    (+ 2 3))
; => nil
```

### Boolean Operators

#### Nil

In Clojure, the none value is `nil`. You can check if a value is `nil` with the `nil?` function

```clojure
(nil? 1)
; => false

(nil? nil)
; => true
```

#### Or

The `or` operator returns either the first truthy value or if none of them evaluate to true, the last value.

```clojure
(or false nil)
; => nil

(or (= 1 1))
; => true

(or (= 1 2) 6)
; => 6

(or (= 2 2) (= 4 5))
; => true
```

#### And

The `and` operator returns the first falsey value or if no values evaluate to false, the last truthy value.

```clojure
(and (= 1 1) (= 2 2) 10)
; => 10

(and (= 1 2) (= 1 1))
; => false

(and nil (= 1 1))
; => nil
```

### Naming values with def

-- Research the difference between binding & assignment (has to do something with context)

You can *bind* names to a value 

```clojure
(def name "Daisy")
name
; => Daisy
```

## Data Structures

All data structures in Clojure are immutable. The common data structures are present - numbers, strings, lists, maps (known as dictionaries in Python), sets and vectors.

#### Numbers

Clojure supports integers, floats and ratios. An example of each

```clojure
1
1.4
1/5
```

#### Strings

Strings are defined within double quotes in Clojure

```clojure
"Hello World"
```

#### Maps (Dictionaries)

Maps map keys to values. An example of a map

```clojure
{"name" "Daisy"}
```

To get the value mapped to a key, the `get` function is used

```clojure
(get {"name" "Daisy"}, "name")
; => Daisy
```
If it doesn't find the key it will return `nil` as the value. You can also set a default as follows

```clojure
(get {"name" "Daisy"}, "surname" "Wag")
; => Wag
```

Similar to other languages, maps can be nested

```clojure
{"name" {"first" "Daisy" "last" "Wag"}}
```

To access variables in a nested dictionary, the function `get-in` can be used

```clojure
(get-in {"name" {"first" "Daisy" "last" "Wag"}} ["name" "first"])
; => Daisy
```

#### Keywords

Keywords are primarily used as keys in maps. An example of a map with keywords

```clojure
{:name "Daisy"}
```

The same functions apply with keywords

```clojure
(get {:name "Daisy"} :name)
; => Daisy

(get-in {:name {:first "Daisy" :last "Wag"}} [:name :first])
; => Daisy
```

Keywords can be used as functions to look up the value in a data structure such as a map.

```clojure
(:name {:name "Daisy"})
; => Daisy
```
Default values can also be provided

```clojure
(:surname {:name "Daisy"} "Wag")
; => Wag
```

#### Vectors
