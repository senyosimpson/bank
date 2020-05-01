# Functions

## Defining functions

Functions are defined using `defn`.

```clojure
(defn add
    "Adds to numbers"
    [a b]
    (+ a b))

(add 2 3)
; => 5
```

The first line defines the name of the function. The second line is the docstring that describes the functionality of the function - it is optional. The function arguments are specified in line 3, `[a b]`. The last line defines the function implementation.

Clojure functions can take in zero or more arguments. The arguments can be of any type.

```clojure
(defn printname
    []
    (println "Daisy"))

(printname)
; => Daisy
```

Functions can also be overloaded. The function will be executed depending on what function signature is matched.

```clojure
(defn printname
    ([]
        (println "Daisy"))
    ([name]
        (println name))
    ([name surname]
        (println (str name " " surname)))
)

(printname)
; => Daisy

(printname "Leo")
; => Leo

(printname "Leo" "Daisy")
; => Leo Daisy
```

Overloading provides a way to set default arguments

```clojure
(defn printname
    ([name]
        (printname name "Snow"))
    ([name surname]
        (println (str name " " surname)))
)

(printname "Leo")
; => Leo Snow
```

In the case you only pass one argument in, the function will call itself with the second argument set as a default.

Clojure also allows for a variable number of arguments to passed into a function. This is done with the `rest` parameter which is denoted by an ampersand. The variables become a *list* within the function.

```clojure
(defn concatstrings
    [& string]
    (clojure.string/join " " string))

(concatstrings "It's" "a" "good" "day")
; => It's a good day
```

## Destructuring

Destructuring is a more sophisticated way of defining parameters. It allows for binding names to values within a collection. It associates the variable at a position with the corresponding value at that position within the collection.

```clojure
(defn add
    [[a b]]
    (+ a b))

(add [1 2])
; => 3
```

In the destructuring, `a` mapped to 1 and `b` mapped to 2. This can also be used with a variable number of arguments

```clojure
(defn add
    [[a b & more_terms]]
    (+ (+ a b) (nth more_terms 0)))

(add [1 2 3 4])
; => 6
```

Maps can also be deconstructed. There are two ways that are equivalent

```clojure
(defn printname
    [{name :name surname :surname}]
    (println (str name " " surname)))

(printname {:name "Leo" :surname "Daisy"})
; => Leo Daisy

(defn printname
    [{:keys [name surname]}]
    (println (str name " " surname)))

(printname {:name "Leo" :surname "Daisy"})
; => Leo Daisy
```

## Anonymous Functions

Anonymous functions are functions without names. The common form of anonymous functions is as follows

```clojure
(fn [param list]
    function body
)
```

```clojure
(fn [name]
    (str "Hey " name)
)
```

You can use the above function in such a manner

```clojure
(map (fn [name] (str "Hey " name))
["Daisy", "Leo"])

; => ("Hey Daisy", "Hey Leo")
```

The alternate method of declaring anonymous functions is more concise

```clojure
#(function % other val)
```
where `%` serves as the placeholder for the arguments

A simple example

```clojure
(#(* % 3) 8)
; => 24
```