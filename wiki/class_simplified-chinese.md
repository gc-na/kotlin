<!--
Meta Description: # Kotlin中的类: 详解与用法 ## 概述 Kotlin中的类是面向对象编程的基本构造块，允许开发者创建自定义数据类型，封装属性和方法，以便实现更高效的代码组织和复用。 ## 文档 在Kotlin中，类通过`class`关键字定义。类是对象的蓝图，包含属性（变量）和方法（函数）。Kotlin的...
Meta Keywords: class, fun, kotlin, name, age
-->

# Kotlin中的类: 详解与用法

## 概述
Kotlin中的类是面向对象编程的基本构造块，允许开发者创建自定义数据类型，封装属性和方法，以便实现更高效的代码组织和复用。

## 文档
在Kotlin中，类通过`class`关键字定义。类是对象的蓝图，包含属性（变量）和方法（函数）。Kotlin的类支持继承、接口实现和构造函数，使得创建复杂的数据结构变得简单。

### 基本语法
```kotlin
class ClassName {
    // 属性
    var propertyName: Type = initialValue

    // 方法
    fun methodName(parameters): ReturnType {
        // 方法体
    }
}
```

### 构造函数
Kotlin支持主构造函数和次构造函数。主构造函数在类头中定义，而次构造函数用`constructor`关键字定义。

#### 主构造函数示例
```kotlin
class Person(val name: String, var age: Int) {
    fun introduce() {
        println("我叫 $name, 今年 $age 岁。")
    }
}
```

#### 次构造函数示例
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

## 示例
### 创建对象
```kotlin
fun main() {
    val person = Person("小明", 25)
    person.introduce()  // 输出: 我叫 小明, 今年 25 岁。
}
```

### 继承
Kotlin支持单继承，使用`open`关键字使类可被继承。
```kotlin
open class Animal {
    open fun sound() {
        println("动物发出声音")
    }
}

class Dog : Animal() {
    override fun sound() {
        println("汪汪")
    }
}
```

### 使用接口
类可以实现接口以提供多种功能。
```kotlin
interface Vehicle {
    fun drive()
}

class Car : Vehicle {
    override fun drive() {
        println("汽车在行驶")
    }
}
```

## 说明
- **常见陷阱**：在Kotlin中，未使用`open`关键字的类不能被继承。确保在设计可扩展类时使用`open`。
- **数据类**：Kotlin提供了`data class`，用于简化模型类的定义，自动生成`toString()`、`equals()`、和`hashCode()`等方法。
- **可见性修饰符**：Kotlin支持`public`、`private`、`protected`和`internal`等可见性修饰符，帮助控制类和其成员的访问权限。

## 一句话总结
Kotlin中的类是构建自定义数据类型的基础，支持属性、方法、继承和接口，实现了灵活的面向对象编程。