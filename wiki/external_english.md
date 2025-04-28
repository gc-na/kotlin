<!--
Meta Description: # Understanding the "external" Keyword in Kotlin: A Comprehensive Guide ## Synopsis The `external` keyword in Kotlin is used to declare functions or p...
Meta Keywords: kotlin, native, external, function, code
-->

# Understanding the "external" Keyword in Kotlin: A Comprehensive Guide

## Synopsis
The `external` keyword in Kotlin is used to declare functions or properties that are implemented in native code, enabling interoperability with C/C++ libraries and facilitating the use of native platform features in Kotlin applications.

## Documentation
In Kotlin, the `external` modifier is employed to indicate that a function or a property is defined externally, typically in a native library. This is particularly useful when working with Kotlin/Native, which allows Kotlin code to run on platforms like iOS, where you might want to leverage existing C or C++ libraries.

### Purpose
The primary purpose of the `external` keyword is to enable Kotlin code to call functions that are implemented outside of the Kotlin environment, allowing developers to harness the power of existing native libraries or system calls without rewriting them in Kotlin.

### Usage
To declare an external function or property, simply prefix the function or property declaration with the `external` keyword. The function must be defined in a separate native library that the Kotlin application can access.

```kotlin
external fun nativeFunction(param: Int): String
```

### Details
- `external` functions cannot have a body in Kotlin; they must be implemented in the native library.
- The Kotlin compiler needs access to the native library for linking at compile time.
- When using `external`, ensure that the native function’s signature matches the Kotlin declaration, including the parameter types and return type.

## Examples

### Example 1: Declaring an External Function
```kotlin
external fun greet(name: String): String
```
In this example, the `greet` function is declared as external and is expected to return a greeting message in the form of a `String`, which is implemented in the native code.

### Example 2: Using External Functions
```kotlin
fun main() {
    val message = greet("World")
    println(message) // Output depends on the native implementation
}
```
When `greet` is called, it will invoke the corresponding native function and print the returned value.

### Example 3: External Properties
```kotlin
external var nativeValue: Int
```
This example declares an external property `nativeValue` which can be accessed and modified in the Kotlin code, but its implementation resides in the native library.

## Explanation
### Common Pitfalls
- **Missing Native Implementation**: If the required native function or property is not implemented or linked correctly, you will encounter runtime errors.
- **Signature Mismatches**: Ensure that the Kotlin declaration matches the native implementation in terms of parameter types and return types to avoid unexpected behavior.
- **Platform Compatibility**: The use of `external` is primarily applicable in Kotlin/Native projects. Using it in Kotlin/JVM or Kotlin/JS will not have the desired effect, as they don't support native code execution.

### Gotchas
- The `external` keyword does not guarantee type safety with respect to native code; the developer must ensure that the types used in Kotlin match those in the native library.
- Debugging external functions can be more challenging, as errors may arise from the native side that are not directly visible in Kotlin.

## One Line Summary
The `external` keyword in Kotlin allows for the declaration of functions and properties that are implemented in native code, enabling seamless integration with C/C++ libraries.