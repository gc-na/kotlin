<!--
Meta Description: # Understanding the 'override' Keyword in Kotlin: A Comprehensive Guide ## Synopsis The `override` keyword in Kotlin is used to indicate that a member...
Meta Keywords: override, open, keyword, you, class
-->

# Understanding the 'override' Keyword in Kotlin: A Comprehensive Guide

## Synopsis
The `override` keyword in Kotlin is used to indicate that a member function or property in a subclass is intended to override a member function or property in its superclass. This feature is essential for implementing polymorphism in object-oriented programming.

## Documentation
In Kotlin, when you define a class that inherits from another class, you may want to modify or extend the behavior of a function or property defined in the superclass. To achieve this, you must use the `override` keyword. This keyword ensures that the subclass's member is an overridden version of the superclass's member.

### Purpose
The primary purpose of the `override` keyword is to enable polymorphism, allowing a subclass to provide a specific implementation of a method that is already defined in its superclass. This is critical in designing flexible and reusable code.

### Usage
To override a function or property in Kotlin, follow these steps:

1. **Define the function or property in the superclass** with the `open` modifier. This indicates that the member is open for overriding.
2. **In the subclass, use the `override` keyword** before the function or property to indicate that you are providing a new implementation.

### Details
- The `override` keyword is mandatory when you override a member. If you forget to use it, the compiler will raise an error.
- You can override only `open`, `abstract`, or `override` members from a superclass. Members marked as `final` cannot be overridden.
- The overridden method in the subclass can also be marked as `final`, preventing further overriding in any subclasses of that subclass.

## Examples

### Example 1: Basic Function Override
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
    val dog = Dog()
    dog.sound()  // Output: Bark
}
```

### Example 2: Overriding Properties
```kotlin
open class Vehicle {
    open val wheels: Int = 4
}

class Motorcycle : Vehicle() {
    override val wheels: Int = 2
}

fun main() {
    val motorcycle = Motorcycle()
    println(motorcycle.wheels)  // Output: 2
}
```

### Example 3: Final Override
```kotlin
open class Shape {
    open fun draw() {
        println("Drawing shape")
    }
}

class Circle : Shape() {
    final override fun draw() {
        println("Drawing circle")
    }
}

// The following subclass would result in a compilation error
// class Ellipse : Circle() {
//     override fun draw() { // Error: Cannot override 'draw': it is final in 'Circle'
//         println("Drawing ellipse")
//     }
// }

fun main() {
    val circle = Circle()
    circle.draw()  // Output: Drawing circle
}
```

## Explanation
While using the `override` keyword is straightforward, there are some common pitfalls to be aware of:

- **Forgetting to use `open`:** If you attempt to override a method in a superclass that is not marked with `open`, you'll encounter a compilation error.
- **Incorrect Method Signatures:** The overridden method's signature in the subclass must match exactly with the superclass’s method, including parameter types and return type.
- **Overriding Properties:** When overriding properties, ensure you understand the difference between backing fields and getter/setter methods.

Additionally, note that using the `final` keyword on an overridden method prevents any further subclasses from overriding that method again, which can be useful for defining fixed behavior in a class hierarchy.

## One Line Summary
The `override` keyword in Kotlin is essential for implementing polymorphism by allowing subclasses to provide specific implementations of methods and properties defined in their superclasses.