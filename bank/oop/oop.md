# Object-oriented Programming

Object-oriented is a programming paradigm based on objects which are data structures that include both data and functions that can be applied to those functions. The object-oriented paradigm is arguably the most popular programming paradigm, made so by its use in enterprise languages such as Java and C++. It also has the benefit of being a natural way of thinking. Take for instance a house. A house is an object that consists of many other objects such as a kitchen, bathroom, bedroom etc which also contain other objects such as a toilet, bed, table etc. These are all well defined in object-oriented programming and can have functions attached to them for processing the data they contain. For instance, a toilet might have a flush function which flushes the toilet and updates the number of flushes performed in a day. Object-oriented programming has four core tenets - encapsulation, abstraction, inheritance and polymorphism.

## Encapsulation

Encapsulation can be thought of a boundary around a set of data and the functions that operate on that data. This boundary manifests itself in the form of a class. Encapsulation hides implementation details and sets restrictions on how that class is interacted with - only public functions expose functionality of the class. A common example here is the use of setter methods. To set a value in a class, it has to be done through a setter method instead of directly. The benefits of encapsulation are increased program security and robustness to data corruption.

## Abstraction

Abstraction serves to reduce coding complexity by only showing the information that is essential and hides the implementation details from the user. An object provides an abstraction from the underlying complexity it encapsulates. For example, when logging into a website, the only required information is a username and password. How the data is sent to the server, authenticates the user and displays the loading page is abstracted from the user. In the same way, in development, when using objects, the implementation is abstracted away from the developer. All the relevant information is exposed through the object's functions.

## Inheritance

Inheritance is a mechanism which allows a class to extend another class while inheriting all the methods of that class. This provides a hierarchical relationship between classes. The benefit of inheritance is that it increases code reuse thereby reducing complexity and duplication of code. Additionally, it provides necessary flexibility in designing classes. At its simplest, inheritance is simple to understand. Imagine we have a base class `car`. This defines some common attributes relevant to every car (4 wheels, driving wheel, etc) and some common functionality (drive, brake, etc). We can think of a `Ferrari` as an extension of the `car` class. It has all the common traits of a car and some additional attributes (fanciness, convertible) and some additional functionlity (open roof, park itself). Thus instead of rewriting the `Ferrari` class from scratch, we can inherit all the functions and methods of `car` and add additional attributes and functions.

```java

class Car {
    protected int wheels = 4;

    public void drive() {
        System.out.println("Driving")
    }

    public void brake() {
        System.out.println("Braking")
    }
}

class Ferrari extends Car {
    private boolean fancy = True
    private boolean convertible = True

    public void openRoof() {
        System.out.println("Opening roof")
    }

    public void park() {
        System.out.println("Parking car")
    }
}
```

In the derived class, the methods `drive` and `brake` are still available for the `Ferrari class` to use even though they are not explicity defined.

```java
Ferrari ferrari = new Ferrari()
ferrari.drive()
// => Driving
```

## Polymorphism

Polymorphism is the ability of an object to take on many forms and be processed differently based on its data type. This is commonly realised through method overloading and overriding. In method overloading, an object can contain multiple versions of the same function. They are differentiated by their method signatures (the arguments that are passed into the function).

```java

class Overload {
    void demo (int a) {
       System.out.println ("a: " + a);
    }

    void demo (int a, int b) {
       System.out.println ("a and b: " + a + "," + b);
    }

    double demo(double a) {
       System.out.println("double a: " + a);
       return a*a;
    }
}
```
In the above example, the method `demo` is defined three times and each one has different input arguments. The corresponding method will be called depending on which input arguments are passed into the function.

The other common form of polymorphism, overriding, is when derived classes redefine the methods of their parent class.

```java

public class Animal {
   public void sound() {
      System.out.println("Animal is making a sound");   
   }
}

class Horse extends Animal {
    @Override
    public void sound() {
        System.out.println("Neigh");
    }
}
```
In this example, `Horse` overrides the `sound` function defined in its parent class, `Animal`. The corresponding function is called depending on which data type (`Animal` or `Horse`) invokes the function.


## References

1. [Object-oriented programming - webopedia](https://searchapparchitecture.techtarget.com/definition/object-oriented-programming-OOP)
2. [Object-oriented programming - wikipedia](https://en.wikipedia.org/wiki/Object-oriented_programming)
3. [OOP in Java](https://beginnersbook.com/2013/03/oops-in-java-encapsulation-inheritance-polymorphism-abstraction/)
4. [Polymorphism in Java](https://beginnersbook.com/2013/03/polymorphism-in-java/)