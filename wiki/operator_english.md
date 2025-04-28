<!--
Meta Description: # Understanding Operators in Kotlin: A Comprehensive Guide ## Synopsis Operators in Kotlin are special symbols or keywords that perform operations on ...
Meta Keywords: operators, kotlin, val, these, println
-->

# Understanding Operators in Kotlin: A Comprehensive Guide

## Synopsis
Operators in Kotlin are special symbols or keywords that perform operations on variables and values. They facilitate arithmetic, logical, and relational operations, making the programming experience more intuitive and efficient.

## Documentation
In Kotlin, operators are categorized based on their functionality. They can be broadly divided into the following types:

1. **Arithmetic Operators**: These operators perform basic mathematical operations.
   - `+` (Addition)
   - `-` (Subtraction)
   - `*` (Multiplication)
   - `/` (Division)
   - `%` (Modulus)

2. **Relational Operators**: These operators compare two values and return a Boolean result.
   - `==` (Equal to)
   - `!=` (Not equal to)
   - `>` (Greater than)
   - `<` (Less than)
   - `>=` (Greater than or equal to)
   - `<=` (Less than or equal to)

3. **Logical Operators**: These operators are used to combine Boolean expressions.
   - `&&` (Logical AND)
   - `||` (Logical OR)
   - `!` (Logical NOT)

4. **Assignment Operators**: These operators assign values to variables.
   - `=` (Assign)
   - `+=`, `-=`, `*=`, `/=`, `%=` (Compound assignments)

5. **Unary Operators**: These operators operate on a single operand.
   - `++` (Increment)
   - `--` (Decrement)

6. **Infix Operators**: These are special functions that can be called without using the dot or parentheses.
   - Defined using the `infix` keyword.

Operators can also be overloaded in Kotlin, allowing developers to define custom behavior for existing operators when they are applied to user-defined types.

## Examples
### Arithmetic Operators
```kotlin
val a = 10
val b = 5
val sum = a + b // 15
val difference = a - b // 5
val product = a * b // 50
val quotient = a / b // 2
val remainder = a % b // 0
```

### Relational Operators
```kotlin
val x = 10
val y = 20
println(x == y) // false
println(x != y) // true
println(x > y) // false
println(x < y) // true
```

### Logical Operators
```kotlin
val isTrue = true
val isFalse = false
println(isTrue && isFalse) // false
println(isTrue || isFalse) // true
println(!isTrue) // false
```

### Infix Operator Example
```kotlin
infix fun Int.isGreaterThan(value: Int): Boolean {
    return this > value
}

val result = 10 isGreaterThan 5 // true
```

## Explanation
When using operators in Kotlin, it's important to be aware of operator precedence and associativity, as these can affect the outcome of complex expressions. Also, remember that Kotlin does not support operator overloading for all operators; for instance, you cannot overload the `.` operator.

A common pitfall for new Kotlin developers is the misunderstanding of the distinction between `==` and `===`. The former checks for value equality, while the latter checks for reference equality.

## One Line Summary
Operators in Kotlin are symbols that perform operations on variables and values, enhancing code readability and functionality.