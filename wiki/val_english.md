<!--
Meta Description: # Understanding 'val' in Kotlin: Immutable Variable Declaration ## Synopsis In Kotlin, `val` is used to declare read-only (immutable) variables, ensur...
Meta Keywords: val, variable, kotlin, immutable, type
-->

# Understanding 'val' in Kotlin: Immutable Variable Declaration

## Synopsis
In Kotlin, `val` is used to declare read-only (immutable) variables, ensuring that once a value is assigned to a variable, it cannot be changed.

## Documentation
The `val` keyword is a fundamental aspect of Kotlin's type system that promotes immutability, making your code safer and easier to understand. By declaring a variable with `val`, you signal to both the compiler and other developers that the variable's value is fixed after its initial assignment.

### Purpose
- To create immutable variables, which cannot be reassigned once initialized.
- To promote safer coding practices by reducing the risk of unintended changes to variables.

### Usage
To declare a variable with `val`, simply use the following syntax:

```kotlin
val variableName: Type = initialValue
```

- `variableName`: This is the name of the variable you want to declare.
- `Type`: Specifies the type of the variable (optional if type inference is possible).
- `initialValue`: The initial value assigned to the variable at the time of declaration.

### Details
- If the type is omitted, Kotlin uses type inference to determine the type based on the assigned value.
- Attempting to reassign a `val` variable will result in a compile-time error.
- `val` can be used with any data type, including primitive types, objects, collections, and custom classes.

## Examples
Here are some basic usage examples of the `val` keyword in Kotlin:

### Declaring an Immutable Variable
```kotlin
val pi: Double = 3.14159
```

### Using Type Inference
```kotlin
val greeting = "Hello, World!"
```

### Immutable List
```kotlin
val numbers = listOf(1, 2, 3, 4, 5)
// numbers[0] = 10 // This will cause a compilation error
```

### Object Assignment
```kotlin
val person = Person("John", 30)
// person.age = 31 // This will cause a compilation error if age is a val
```

## Explanation
While `val` is powerful for creating immutable references, it’s important to note the following common pitfalls and gotchas:

- **Immutable Reference vs. Mutable Content**: Declaring a variable with `val` does not make the object it references immutable. For example, you can have a `val` list that is immutable in terms of reassignment, but the contents of the list can still be modified if the list itself is mutable.
  
  ```kotlin
  val mutableList = mutableListOf(1, 2, 3)
  mutableList.add(4) // This is allowed
  // mutableList = mutableListOf(5, 6) // This will cause a compilation error
  ```

- **Readability**: Using `val` enhances code readability by indicating variable intent. It’s recommended to use `val` by default unless you need to change the variable’s value.

- **Performance**: Since `val` variables are immutable, the compiler can optimize the code better, potentially leading to performance improvements.

## One Line Summary
In Kotlin, `val` is used to declare immutable variables that cannot be reassigned after their initial assignment.