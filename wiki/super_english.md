<!--
Meta Description: # Understanding "super" in Kotlin: A Comprehensive Guide ## Synopsis In Kotlin, the `super` keyword is used to access members of a superclass from a s...
Meta Keywords: super, kotlin, class, display, method
-->

# Understanding "super" in Kotlin: A Comprehensive Guide

## Synopsis
In Kotlin, the `super` keyword is used to access members of a superclass from a subclass, facilitating polymorphism and enabling method overriding. This article delves into the purpose, usage, and nuances of the `super` keyword in Kotlin programming.

## Documentation
The `super` keyword is a fundamental component of Kotlin's object-oriented programming capabilities. It allows subclasses to reference properties and methods defined in their parent classes, supporting the principle of inheritance.

### Purpose
The primary purpose of `super` is to resolve ambiguities when a subclass overrides a method or property that is also defined in its superclass. By using `super`, developers can explicitly call the superclass's version of a method or access its properties.

### Usage
To use `super`, simply prefix the method or property you wish to access with the `super` keyword. This is particularly useful in overridden methods where you want to extend or customize the behavior of the superclass.

### Syntax
```kotlin
super.methodName(arguments)
super.propertyName
```

### Details
- **Inheriting Classes**: When a class inherits from a parent class, it can override or extend its functionality.
- **Multiple Inheritance**: Kotlin does not support multiple inheritance of classes but allows multiple interfaces. When dealing with multiple interfaces, `super` can help resolve conflicts.
- **Constructor Call**: The `super` keyword can also be used in a constructor to pass parameters to the superclass.

## Examples

### Basic Usage
```kotlin
open class Parent {
    open fun display() {
        println("Display from Parent")
    }
}

class Child : Parent() {
    override fun display() {
        super.display() // Calls Parent's display method
        println("Display from Child")
    }
}

fun main() {
    val child = Child()
    child.display()
}
```
**Output:**
```
Display from Parent
Display from Child
```

### Accessing Properties
```kotlin
open class Base {
    open val info: String = "Base Info"
}

class Derived : Base() {
    override val info: String = "Derived Info"

    fun showInfo() {
        println(super.info) // Accesses Base's info property
    }
}

fun main() {
    val derived = Derived()
    derived.showInfo() // Output: Base Info
}
```

### Using super in Constructors
```kotlin
open class Animal(val sound: String) {
    init {
        println("Animal sound: $sound")
    }
}

class Dog : Animal("Bark") {
    init {
        println("Dog class initialized")
    }
}

fun main() {
    val dog = Dog() // Output: Animal sound: Bark
                   //         Dog class initialized
}
```

## Explanation
While using `super`, developers should be mindful of the following common pitfalls:
- **Ambiguity**: In cases where a method is overridden from multiple interfaces, the compiler may raise an ambiguity error. Be explicit in your calls.
- **Constructor Resolution**: Ensure that the superclass constructor is called appropriately, especially when passing parameters to avoid runtime exceptions.
- **Scope**: The `super` keyword can only be used within the context of a subclass method or constructor.

## One Line Summary
The `super` keyword in Kotlin enables access to superclass members, facilitating method overriding and polymorphism in object-oriented programming.