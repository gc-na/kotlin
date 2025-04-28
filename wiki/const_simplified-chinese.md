<!--
Meta Description: # Kotlin中的const关键字详解 ## 概述 `const` 是Kotlin中的一个关键字，用于声明编译时常量。它允许开发者定义不可变的常量，这些常量在编译时就被确定，从而提高代码的性能和可读性。 ## 文档 在Kotlin中，`const` 修饰符用于声明一个常量，该常量的值在编译时就被确...
Meta Keywords: const, val, kotlin, app_name, println
-->

# Kotlin中的const关键字详解

## 概述
`const` 是Kotlin中的一个关键字，用于声明编译时常量。它允许开发者定义不可变的常量，这些常量在编译时就被确定，从而提高代码的性能和可读性。

## 文档
在Kotlin中，`const` 修饰符用于声明一个常量，该常量的值在编译时就被确定。常量必须是`val`类型，并且只能用于基本数据类型（如`Int`, `Double`, `String`等）。使用`const`关键字的好处在于能够让常量在编译时进行优化，从而减少运行时的开销。

### 用法
- `const` 关键字只能用于顶层声明或对象声明中的属性。
- 只支持基本数据类型和字符串类型。
- 常量的值必须在声明时初始化，且不能被修改。

### 语法示例
```kotlin
const val MAX_USERS = 100
const val API_URL = "https://api.example.com"
```

## 示例
以下是使用`const`的基本示例：

```kotlin
const val PI = 3.14159
const val APP_NAME = "KotlinDemo"

fun main() {
    println("应用名称：$APP_NAME")
    println("圆周率：$PI")
}
```

## 解释
在使用`const`时，有一些常见的注意事项和陷阱：

1. **只能用于基本类型和字符串**：不能将`const`用于自定义对象或复杂数据结构。
2. **必须在顶层或对象中声明**：`const` 变量不能在类的内部声明。
3. **初始化要求**：`const`常量必须在声明时初始化，不能使用`lateinit`或懒加载。

### 陷阱
- **局部常量不可用**：局部变量不能使用`const`关键字，这可能会导致一些混淆。
- **不支持非基本类型**：尝试使用`const`与非基本数据类型（如List或Map）时，将会导致编译错误。

## 一句话总结
`const`关键字在Kotlin中用于声明编译时常量，以提高性能和代码可读性。