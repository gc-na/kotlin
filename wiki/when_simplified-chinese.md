<!--
Meta Description: # Kotlin 中的 when 语句详解 ## 概述 `when` 是 Kotlin 中的一种控制流结构，类似于其他编程语言中的 `switch` 语句。它允许根据给定表达式的值执行不同的代码块，是一种非常灵活和强大的条件判断工具。 ## 文档 ### 目的 `when` 语句用于根据条件选择执行...
Meta Keywords: when, kotlin, println, else, 代码块
-->

# Kotlin 中的 when 语句详解

## 概述
`when` 是 Kotlin 中的一种控制流结构，类似于其他编程语言中的 `switch` 语句。它允许根据给定表达式的值执行不同的代码块，是一种非常灵活和强大的条件判断工具。

## 文档
### 目的
`when` 语句用于根据条件选择执行的代码块。它可以匹配多个条件，并可以根据不同的数据类型进行匹配。

### 用法
`when` 语句的基本语法如下：

```kotlin
when (expression) {
    value1 -> { // 代码块 1 }
    value2 -> { // 代码块 2 }
    in valueRange -> { // 代码块 3 }
    is Type -> { // 代码块 4 }
    else -> { // 默认代码块 }
}
```

- **expression**: 这是需要判断的表达式。
- **value1, value2**: 这些是要与表达式匹配的值。
- **valueRange**: 可以用来匹配一个值是否在某个范围内。
- **is Type**: 用于类型检查。
- **else**: 可选的默认代码块，当没有其他条件匹配时执行。

### 细节
- `when` 语句是一个表达式，因此可以返回值。
- 可以不提供表达式，直接使用条件来判断。
- 支持使用布尔表达式作为条件。

## 示例
### 基本用法
```kotlin
val x = 3
val result = when (x) {
    1 -> "一"
    2 -> "二"
    3 -> "三"
    else -> "未知"
}
println(result) // 输出: 三
```

### 使用范围
```kotlin
val y = 5
val result = when (y) {
    in 1..10 -> "在范围内"
    else -> "超出范围"
}
println(result) // 输出: 在范围内
```

### 类型检查
```kotlin
fun printLength(obj: Any) {
    when (obj) {
        is String -> println("字符串长度: ${obj.length}")
        is Int -> println("整数: $obj")
        else -> println("未知类型")
    }
}
printLength("Hello") // 输出: 字符串长度: 5
```

### 不带表达式的 when
```kotlin
val z = 10
when {
    z < 0 -> println("负数")
    z == 0 -> println("零")
    else -> println("正数")
}
// 输出: 正数
```

## 说明
在使用 `when` 语句时，有几个常见的注意事项：
- 确保表达式的值与条件相匹配，否则将会执行 `else` 代码块。
- 使用范围匹配时，确保范围是正确的（例如 `1..10` 表示从 1 到 10 的所有值）。
- 当使用类型检查时，`is` 关键字可以帮助我们确认对象的类型。

## 一句话总结
Kotlin 中的 `when` 语句是一种强大的条件判断工具，允许根据表达式的值或类型选择执行的代码块。