# Data Structures

All data structures in Clojure are immutable. The common data structures are present - numbers, strings, lists, maps (known as dictionaries in Python), sets and vectors.

## Numbers

Clojure supports integers, floats and ratios. An example of each

```clojure
1
1.4
1/5
```

## Strings

Strings are defined within double quotes in Clojure

```clojure
"Hello World"
```

## Maps (Dictionaries)

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

## Keywords

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

## Vectors

Vectors are similar to arrays. You can mix types in lists as well.

```clojure
[3 2 1]
[3 "hello" {:name "Daisy"}]
```

To get an element at a certain index in a vector we use the `get` function

```clojure
(get [3 2 1] 0)
; => 3
```

To add elements to a vector, the `conj` function is used. This adds elements to the *end* of the vector

```clojure
(conj [1 2 3] 4)
; => [1 2 3 4]
```

## Lists

Lists store a collection of values similar to vectors. They are also able to mix types. To instantiate a list

```clojure
'(1 2 3 4)
```

To retrieve a value from the list, the `nth` function is used

```clojure
(nth '(1 2 3) 0)
; => 1
(nth '(1 2 3) 2)
; => 3
```

Elements can be added to a list using the `conj` function. However, different to vectors, they add elements to the *beginning* of a list.

```clojure
(conj '(1 2 3) 4)
; => (4 1 2 3)
```

## Sets

Sets are collections of unique values. There are two sets in Clojure, *hash sets* and *sorted sets*. They are also able to mix types. The book focuses on hash sets so this is all that is covered here.

```clojure
#{"Daisy" 20 4}
```

Since sets contain unique elements, it enforces this by default. If you try add a value that is already in the set, it will ignore it.

```clojure
#{1 1 "Daisy" "Daisy"}
; => #{1 "Daisy"}

(conj #{1 "Daisy"} "Daisy")
; => #{1 "Daisy"}
```

Sets can also be created from lists and vectors using the `set` function.

```clojure
(set [1 1 2 2])
; => #{1 2}
```

You can check if a value is in the set using the `contains?` function.

```clojure
(contains? #{"Daisy" 1} "Daisy")
; => true

(contains? #{"Daisy" 1} "Flower")
; => true
```

## Appendix

### Lists vs Vectors