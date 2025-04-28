<!--
Meta Description: # Understanding "protected" in Kotlin: Access Modifiers Explained ## Synopsis In Kotlin, the `protected` access modifier is used to restrict the visib...
Meta Keywords: protected, class, access, parent, kotlin
-->

# Understanding "protected" in Kotlin: Access Modifiers Explained

## Synopsis
In Kotlin, the `protected` access modifier is used to restrict the visibility of class members, allowing access only within the same class and its subclasses. This feature promotes encapsulation and maintains the integrity of object-oriented design.

## Documentation
The `protected` keyword in Kotlin serves as an access modifier that provides a way to restrict access to class members (properties and methods). Unlike the `private` modifier, which limits access to the containing class only, `protected` allows subclasses to inherit and access these members.

### Purpose
The primary purpose of the `protected` modifier is to enable a controlled level of access to class properties and methods while ensuring that only derived classes can interact with them. This is particularly useful in scenarios involving inheritance, where you want to expose certain functionalities to subclasses without making them publicly accessible.

### Usage
The `protected` modifier can be applied to:
- Properties
- Methods
- Constructors

### Syntax
```kotlin
protected fun myProtectedFunction() {
    // function implementation
}

protected val myProtectedProperty: String = "Protected Property"
```

## Examples
### Example 1: Basic Usage of `protected` in a Class
```kotlin
open class Parent {
    protected val protectedProperty: String = "I am protected"
    
    protected fun protectedFunction() {
        println("This is a protected function")
    }
}

class Child : Parent() {
    fun accessProtected() {
        println(protectedProperty) // Accessible
        protectedFunction() // Accessible
    }
}

fun main() {
    val child = Child()
    child.accessProtected()
}
```

### Example 2: Attempting Access from Outside
```kotlin
class AnotherClass {
    fun accessParent() {
        val parent = Parent()
        // println(parent.protectedProperty) // Error: Cannot access 'protectedProperty': it is protected in 'Parent'
        // parent.protectedFunction() // Error: Cannot access 'protectedFunction': it is protected in 'Parent'
    }
}
```

## Explanation
While using the `protected` modifier is straightforward, there are common pitfalls:
1. **Limited Accessibility**: Members marked as `protected` cannot be accessed from outside their class hierarchy, which can lead to confusion if attempted.
2. **Inheritance Requirement**: The subclass must inherit from the class containing the `protected` member to access it, which may not always be the desired design.
3. **No Top-Level Declaration**: `protected` cannot be applied to top-level declarations, as it is intended for class members only.

### Gotchas
- If a class is not subclassed, `protected` members will be effectively inaccessible, making them redundant in such cases.
- Unlike `private`, `protected` does not restrict access to the containing class, leading to potential misuse in large inheritance hierarchies if not properly managed.

## One Line Summary
The `protected` access modifier in Kotlin allows class members to be accessible only within the class itself and its subclasses, promoting encapsulation in object-oriented design.