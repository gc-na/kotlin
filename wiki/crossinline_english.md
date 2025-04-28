<!--
Meta Description: # Understanding `crossinline` in Kotlin: A Comprehensive Guide ## Synopsis The `crossinline` modifier in Kotlin is used within inline functions to pre...
Meta Keywords: crossinline, lambda, return, inline, action
-->

# Understanding `crossinline` in Kotlin: A Comprehensive Guide

## Synopsis
The `crossinline` modifier in Kotlin is used within inline functions to prevent non-local returns from lambda expressions, ensuring that control flow remains predictable and manageable.

## Documentation
### Purpose
The `crossinline` keyword is a modifier that can be applied to lambda parameters in inline functions. Its primary purpose is to prevent the lambdas from using non-local returns, which can lead to unpredictable behavior in the code. When a lambda is marked as `crossinline`, it can only return to the caller of the inline function and cannot return to the caller of the lambda itself.

### Usage
To use `crossinline`, you declare it before the lambda parameter in an inline function. This indicates that the lambda cannot perform a return statement that would exit the function enclosing the lambda.

#### Syntax
```kotlin
inline fun exampleFunction(crossinline lambda: () -> Unit) {
    // Function body
}
```

### Details
- `crossinline` can only be used in inline functions.
- When a lambda is marked as `crossinline`, any attempt to use a non-local return (i.e., returning from the lambda to the caller of the function that passed it) will result in a compilation error.
- This modifier is particularly useful in scenarios where you want to ensure that the lambda cannot inadvertently alter control flow, such as in higher-order functions that may use the lambda in various contexts.

## Examples
### Basic Example
Here is a simple illustration of how `crossinline` is used:

```kotlin
inline fun performAction(crossinline action: () -> Unit) {
    println("Before action")
    action() // This will execute normally
    println("After action")
}

fun main() {
    performAction {
        println("Action performed")
        // To prevent non-local returns, you cannot use 'return' here
    }
}
```

### Example with Non-local Return Attempt
Attempting to use a non-local return within a `crossinline` lambda will lead to a compilation error:

```kotlin
inline fun performAction(crossinline action: () -> Unit) {
    println("Before action")
    action()
    println("After action")
}

fun main() {
    performAction {
        println("This action will return")
        return // Compilation error: 'return' is not allowed here
    }
}
```

## Explanation
### Common Pitfalls
1. **Non-local Returns**: The most common pitfall is attempting to use a return statement in a `crossinline` lambda. Unlike regular lambdas, where a return can exit the enclosing function, `crossinline` prevents this.
2. **Misunderstanding Function Flow**: Developers may expect that marking a lambda as `crossinline` will have no limitations on its usage. However, it strictly controls the flow, and understanding this is crucial for proper function design.

### Additional Notes
- Use `crossinline` when you need to ensure predictable control flow in your inline functions, especially when passing lambdas that could be called in different contexts.
- This modifier is often used in combination with other inline features, such as `noinline`, which allows you to specify that a particular lambda should not be inlined.

## One Line Summary
The `crossinline` modifier in Kotlin restricts lambda expressions in inline functions from using non-local returns, ensuring predictable control flow.