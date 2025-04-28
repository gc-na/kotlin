<!--
Meta Description: # Understanding "Reified" in Kotlin: A Comprehensive Guide ## Synopsis The `reified` keyword in Kotlin enhances generic programming by preserving type...
Meta Keywords: type, reified, inline, kotlin, functions
-->

# Understanding "Reified" in Kotlin: A Comprehensive Guide

## Synopsis
The `reified` keyword in Kotlin enhances generic programming by preserving type information at runtime, allowing developers to perform type checks and casts without the typical limitations of type erasure.

## Documentation
In Kotlin, generics are subject to type erasure, meaning that type parameters are not available at runtime. This can lead to limitations when you need to check types or create instances of a generic type. The `reified` type parameter provides a solution by allowing the type to be retained at runtime within inline functions.

### Purpose
The primary purpose of `reified` is to enable type-safe operations in inline functions, making it easier to work with generics while maintaining performance and type safety.

### Usage
To use `reified`, it must be declared within an `inline` function. This allows the function to access the type parameter at runtime. Here's the syntax:

```kotlin
inline fun <reified T> myFunction() {
    // Function implementation
}
```

You can then use `T` as a concrete type within the function body, allowing for type checks and instance creation.

### Details
- `reified` can only be used with inline functions, as the Kotlin compiler needs to generate specific bytecode to retain type information.
- It can be particularly useful in scenarios such as filtering lists, deserializing JSON objects, or implementing type-safe builders.

## Examples

### Basic Usage

1. **Using `reified` for Type Checking**:

```kotlin
inline fun <reified T> isInstance(value: Any): Boolean {
    return value is T
}

fun main() {
    println(isInstance<String>("Hello")) // Output: true
    println(isInstance<Int>("Hello"))    // Output: false
}
```

2. **Creating Instances**:

```kotlin
inline fun <reified T> createInstance(): T {
    return T::class.java.newInstance()
}

data class Person(val name: String)

fun main() {
    val person: Person = createInstance() // Requires a no-arg constructor
    println(person) // Output: Person(name=)
}
```

3. **Filtering Lists**:

```kotlin
inline fun <reified T> List<Any>.filterIsInstance(): List<T> {
    return this.filterIsInstance<T>()
}

fun main() {
    val mixedList: List<Any> = listOf(1, "two", 3.0, "four")
    val strings: List<String> = mixedList.filterIsInstance<String>()
    println(strings) // Output: ["two", "four"]
}
```

## Explanation
While `reified` is powerful, there are some common pitfalls:

- **Inline Function Requirement**: You cannot use `reified` with non-inline functions. Ensure that the function is marked as `inline` to utilize `reified`.
- **Type Limitations**: `reified` cannot be used with type parameters that are declared as `out` or `in`. It is purely for declaration and use within inline functions.
- **No reified in Class Members**: The `reified` keyword is exclusive to inline functions and cannot be used in class member functions or properties.

## One Line Summary
The `reified` keyword in Kotlin allows you to retain type information at runtime in inline functions, enabling type-safe operations with generics.