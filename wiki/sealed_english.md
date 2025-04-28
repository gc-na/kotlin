<!--
Meta Description: # Understanding Sealed Classes in Kotlin: A Comprehensive Guide ## Synopsis Sealed classes in Kotlin provide a way to define restricted class hierarch...
Meta Keywords: sealed, class, uistate, classes, when
-->

# Understanding Sealed Classes in Kotlin: A Comprehensive Guide

## Synopsis
Sealed classes in Kotlin provide a way to define restricted class hierarchies, allowing for type safety and exhaustive `when` expressions. They are particularly useful for representing a fixed set of related types.

## Documentation
Sealed classes in Kotlin are declared using the `sealed` keyword. They are abstract by nature, meaning they cannot be instantiated directly. Instead, they serve as a superclass for other classes that inherit from them. This feature is essential for creating a controlled hierarchy of classes, which improves code readability and maintainability.

### Purpose
The primary purpose of sealed classes is to define a closed set of types that are related. This is particularly useful in scenarios where you want to express a limited number of options, such as in state management, event handling, or representing different UI states.

### Usage
To declare a sealed class, use the `sealed class` keyword followed by the class name. The subclasses must be defined within the same file, ensuring that all possible subclasses are known at compile-time.

```kotlin
sealed class Result {
    data class Success(val data: String) : Result()
    data class Error(val error: Exception) : Result()
    object Loading : Result()
}
```

### Details
- **Inheritors**: All subclasses of a sealed class must be declared in the same file. This restriction allows the Kotlin compiler to know all possible subclasses, enabling exhaustive checks in `when` expressions.
- **Exhaustiveness**: When using sealed classes, the `when` expression can cover all possible cases, eliminating the need for an `else` branch.
- **Type Safety**: Sealed classes enhance type safety, making it easier to handle different states or outcomes without the risk of unhandled cases.

## Examples
Here are some basic usage examples of sealed classes:

### Example 1: Representing Network Results
```kotlin
sealed class NetworkResult {
    data class Success(val data: String) : NetworkResult()
    data class Failure(val error: Throwable) : NetworkResult()
    object Loading : NetworkResult()
}

fun handleResult(result: NetworkResult) {
    when (result) {
        is NetworkResult.Success -> println("Data received: ${result.data}")
        is NetworkResult.Failure -> println("Error occurred: ${result.error.message}")
        NetworkResult.Loading -> println("Loading...")
    }
}
```

### Example 2: UI States
```kotlin
sealed class UiState {
    object Loading : UiState()
    data class Content(val items: List<String>) : UiState()
    data class Error(val message: String) : UiState()
}

fun render(uiState: UiState) {
    when (uiState) {
        is UiState.Loading -> showLoadingIndicator()
        is UiState.Content -> displayItems(uiState.items)
        is UiState.Error -> showError(uiState.message)
    }
}
```

## Explanation
Common pitfalls when using sealed classes include:
- **Defining subclasses outside the sealed class file**: All subclasses must be in the same file as the sealed class. Attempting to define them in separate files will result in a compilation error.
- **Ignoring exhaustiveness**: When using `when` expressions, forgetting to handle all cases can lead to runtime exceptions if an unhandled case arises. However, if all subclasses are covered, the compiler will enforce this at compile time.

## One Line Summary
Sealed classes in Kotlin allow for a controlled class hierarchy that enhances type safety and enables exhaustive `when` expression handling.