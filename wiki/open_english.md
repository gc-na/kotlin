<!--
Meta Description: # Understanding "open" in Kotlin: A Comprehensive Guide ## Synopsis The `open` keyword in Kotlin is used to allow classes and methods to be inheritabl...
Meta Keywords: open, class, kotlin, classes, fun
-->

# Understanding "open" in Kotlin: A Comprehensive Guide

## Synopsis
The `open` keyword in Kotlin is used to allow classes and methods to be inheritable, enabling polymorphism and overriding capabilities in object-oriented programming.

## Documentation
In Kotlin, all classes are final by default, meaning they cannot be subclassed unless explicitly marked as `open`. This design choice promotes safer and more predictable code. The `open` modifier serves several purposes:

- **Classes**: When a class is declared with the `open` keyword, it can be subclassed. For example, if you have a base class that you want other classes to extend, you must mark it as `open`.

- **Methods**: Similarly, methods within classes must also be marked as `open` if they are intended to be overridden in subclasses. If a method is not marked as `open`, any attempt to override it will result in a compilation error.

### Usage
To use the `open` keyword, simply prepend it to the class or method declaration. Here’s the syntax:

```kotlin
open class BaseClass {
    open fun display() {
        println("Display from BaseClass")
    }
}

class DerivedClass : BaseClass() {
    override fun display() {
        println("Display from DerivedClass")
    }
}
```

In this example, `BaseClass` is marked as `open`, allowing `DerivedClass` to inherit from it. The method `display()` is also marked as `open`, which permits overriding in the `DerivedClass`.

## Examples
### Example 1: Open Class
```kotlin
open class Animal {
    open fun sound() {
        println("Some sound")
    }
}

class Dog : Animal() {
    override fun sound() {
        println("Bark")
    }
}

fun main() {
    val myDog = Dog()
    myDog.sound()  // Output: Bark
}
```

### Example 2: Open Method
```kotlin
open class Vehicle {
    open fun start() {
        println("Vehicle starting")
    }
}

class Car : Vehicle() {
    override fun start() {
        println("Car starting")
    }
}

fun main() {
    val myCar = Car()
    myCar.start()  // Output: Car starting
}
```

## Explanation
### Common Pitfalls
1. **Forgetting to Use `open`**: A common mistake is to forget the `open` modifier, leading to unexpected compilation errors when overriding methods or classes.
   
2. **Immutability of Data Classes**: Data classes in Kotlin are final by default. To allow inheritance, you need to declare a data class as `open`, although this is generally not recommended.

3. **Overriding Non-open Methods**: If you try to override a method that is not marked as `open`, Kotlin will raise a compilation error, which can be confusing for developers transitioning from languages that allow default overriding.

### Additional Notes
- Constructors cannot be marked as `open`. Only class declarations and member functions can be.
- Marking a class or method as `open` can impact performance slightly due to dynamic dispatch, but this is usually negligible compared to the benefits of flexibility in design. 

## One Line Summary
The `open` keyword in Kotlin allows classes and methods to be inheritable and overridable, facilitating polymorphism in object-oriented programming.