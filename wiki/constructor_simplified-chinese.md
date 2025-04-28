<!--
Meta Description: # Kotlin 构造函数详解 ## 摘要 构造函数是 Kotlin 中用于初始化对象的特殊函数。它允许开发者在创建类的实例时传递参数，以设定对象的初始状态。 ## 文档 在 Kotlin 中，构造函数分为主构造函数和次构造函数。主构造函数是类头的一部分，而次构造函数是类内部定义的额外构造函数。 #...
Meta Keywords: kotlin, string, name, age, brand
-->

# Kotlin 构造函数详解

## 摘要
构造函数是 Kotlin 中用于初始化对象的特殊函数。它允许开发者在创建类的实例时传递参数，以设定对象的初始状态。

## 文档
在 Kotlin 中，构造函数分为主构造函数和次构造函数。主构造函数是类头的一部分，而次构造函数是类内部定义的额外构造函数。

### 主构造函数
主构造函数在类声明时定义，通常用于初始化属性。其语法如下：

```kotlin
class 类名(参数列表) {
    // 属性和方法
}
```

例如：

```kotlin
class Person(val name: String, var age: Int) {
    // 其他方法和属性
}
```

在这个例子中，`name` 是只读属性，`age` 是可变属性。主构造函数会在创建 `Person` 类的实例时被调用。

### 次构造函数
次构造函数是类内部定义的构造函数，可以有多个，语法如下：

```kotlin
class 类名 {
    constructor(参数列表) {
        // 初始化代码
    }
}
```

例如：

```kotlin
class Person {
    var name: String
    var age: Int

    constructor(name: String, age: Int) {
        this.name = name
        this.age = age
    }
}
```

在这个例子中，`Person` 类有一个次构造函数用于初始化 `name` 和 `age` 属性。

## 示例
以下是使用构造函数的基本示例：

```kotlin
// 使用主构造函数
class Car(val brand: String, var year: Int)

fun main() {
    val car = Car("Toyota", 2021)
    println("品牌: ${car.brand}, 年份: ${car.year}")
}

// 使用次构造函数
class Bike {
    var brand: String
    var type: String

    constructor(brand: String, type: String) {
        this.brand = brand
        this.type = type
    }
}

fun main() {
    val bike = Bike("Giant", "Mountain")
    println("品牌: ${bike.brand}, 类型: ${bike.type}")
}
```

## 说明
使用构造函数时，开发者需要注意以下几点：

1. **默认参数**：在主构造函数中，可以为参数提供默认值，这样在创建对象时可以省略某些参数。
2. **初始化顺序**：在主构造函数中定义的属性会在类的主体之前初始化，而次构造函数则在其调用时初始化。
3. **调用其他构造函数**：在次构造函数中，可以通过 `this(...)` 调用主构造函数或其他次构造函数。

常见的错误包括未初始化属性的使用和构造函数参数的类型不匹配。

## 一句话总结
构造函数是 Kotlin 中用于初始化类实例的特殊函数，分为主构造函数和次构造函数。