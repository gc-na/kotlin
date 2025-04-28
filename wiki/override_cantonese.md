<!--
Meta Description: # Kotlin 的 "override" 關鍵字詳解 ## 摘要 在 Kotlin 中，"override" 關鍵字用於重寫（覆蓋）基類中的方法或屬性，讓子類可以自定義其行為。 ## 文檔 ### 目的 "override" 關鍵字的主要目的是允許子類別提供基類方法的具體實現，從而實現多態性和靈活...
Meta Keywords: override, open, kotlin, class, fun
-->

# Kotlin 的 "override" 關鍵字詳解

## 摘要
在 Kotlin 中，"override" 關鍵字用於重寫（覆蓋）基類中的方法或屬性，讓子類可以自定義其行為。

## 文檔
### 目的
"override" 關鍵字的主要目的是允許子類別提供基類方法的具體實現，從而實現多態性和靈活的代碼結構。

### 使用方式
在 Kotlin 中，當你想要重寫基類中的方法或屬性時，必須在基類中使用 `open` 關鍵字標記該方法或屬性，這樣子類才能使用 `override` 進行重寫。

#### 語法示例：
```kotlin
open class Animal {
    open fun sound() {
        println("Animal sound")
    }
}

class Dog : Animal() {
    override fun sound() {
        println("Bark")
    }
}
```

在上述例子中，`Animal` 類中的 `sound` 方法被標記為 `open`，而 `Dog` 類則使用 `override` 關鍵字重寫了該方法。

## 例子
以下是幾個簡單的使用範例：

### 範例 1：重寫方法
```kotlin
open class Vehicle {
    open fun start() {
        println("Vehicle starting")
    }
}

class Car : Vehicle() {
    override fun start() {
        println("Car starting")
    }
}

fun main() {
    val myCar = Car()
    myCar.start()  // 輸出: Car starting
}
```

### 範例 2：重寫屬性
```kotlin
open class Person {
    open val name: String = "Unknown"
}

class Student : Person() {
    override val name: String = "John Doe"
}

fun main() {
    val student = Student()
    println(student.name)  // 輸出: John Doe
}
```

## 解釋
在使用 `override` 時，有幾個常見的陷阱和注意事項：

1. **基類必須開放**：若基類方法或屬性未標記為 `open`，則無法在子類中使用 `override` 進行重寫。
2. **重寫的簽名必須匹配**：重寫的方法或屬性必須與基類中的定義完全一致（包括名稱、參數類型、返回類型等）。
3. **無法重寫常量**：對於使用 `val` 定義的常量屬性，如果基類中的屬性是 `val`，則無法在子類中用 `override` 進行重寫。

## 一句總結
Kotlin 中的 "override" 關鍵字允許子類別自定義基類行為，實現靈活的多態性。