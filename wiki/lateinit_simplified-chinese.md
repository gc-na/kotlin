<!--
Meta Description: # Kotlin 中的 lateinit 关键字详解 ## 概述 `lateinit` 是 Kotlin 中一个用于延迟初始化属性的关键字，主要用于可变属性（`var`）。它允许我们在声明时不立即赋值，而是在稍后的某个时间点进行初始化。 ## 文档 ### 目的 `lateinit` 关键字的主要目...
Meta Keywords: lateinit, kotlin, name, example, var
-->

# Kotlin 中的 lateinit 关键字详解

## 概述
`lateinit` 是 Kotlin 中一个用于延迟初始化属性的关键字，主要用于可变属性（`var`）。它允许我们在声明时不立即赋值，而是在稍后的某个时间点进行初始化。

## 文档
### 目的
`lateinit` 关键字的主要目的是解决 Kotlin 对非空类型的严格要求。在 Kotlin 中，非空类型必须在声明时立即初始化，而 `lateinit` 使得我们能够在某些情况下推迟初始化，避免了使用可空类型（`?`）带来的复杂性。

### 用法
`lateinit` 只能用于可变属性（`var`），并且必须是非空类型。使用时，只需在属性声明前加上 `lateinit` 关键字。例如：

```kotlin
lateinit var myVariable: String
```

在使用前，必须确保在访问该属性时已经初始化，否则会抛出 `UninitializedPropertyAccessException` 异常。

### 详细信息
- `lateinit` 不适用于基本数据类型（如 `Int`, `Double` 等），只能用于引用类型。
- 在访问 `lateinit` 属性前，可以通过 `::propertyName.isInitialized` 语法检查属性是否已初始化。
- 通常用于依赖注入、测试或在 Android 开发中，避免在构造函数中初始化 UI 组件。

## 示例
```kotlin
class Example {
    lateinit var name: String

    fun setName(value: String) {
        name = value
    }

    fun printName() {
        if (::name.isInitialized) {
            println("Name: $name")
        } else {
            println("Name not initialized")
        }
    }
}

fun main() {
    val example = Example()
    example.printName() // 输出: Name not initialized
    example.setName("Kotlin")
    example.printName() // 输出: Name: Kotlin
}
```

## 解释
### 常见陷阱和注意事项
- **未初始化访问**：如果尝试在未初始化的状态下访问 `lateinit` 属性，将会抛出 `UninitializedPropertyAccessException`。
- **不可用于基本数据类型**：确保使用 `lateinit` 时属性类型为引用类型，基本数据类型无法使用。
- **作用域**：`lateinit` 属性的作用域仅限于声明它的类，无法在外部或子类中访问。

## 一句话总结
`lateinit` 是 Kotlin 中用于延迟初始化非空可变属性的关键字，允许在稍后的时间点进行赋值。