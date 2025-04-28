<!--
Meta Description: # Kotlin 中的介面（Interface）概述 ## 概要 Kotlin 中的介面（Interface）是一種用來定義類別行為的協議，讓實現該介面的類別必須遵循特定的方法。介面在 Kotlin 中是多態性和抽象的核心，促進了程式碼的重用和可擴展性。 ## 文件說明 介面是 Kotlin 中一種...
Meta Keywords: kotlin, interface, val, speed, fun
-->

# Kotlin 中的介面（Interface）概述

## 概要
Kotlin 中的介面（Interface）是一種用來定義類別行為的協議，讓實現該介面的類別必須遵循特定的方法。介面在 Kotlin 中是多態性和抽象的核心，促進了程式碼的重用和可擴展性。

## 文件說明
介面是 Kotlin 中一種特殊的類型，可以包含方法的聲明和屬性的定義。與 Java 不同的是，Kotlin 的介面可以包含實作的方法，這使得介面更加靈活和功能強大。

### 目的
介面的主要目的是定義一組方法和屬性，讓不同的類別可以實現這些方法和屬性，從而達到多型性和鬆耦合的設計。

### 使用
在 Kotlin 中，介面使用 `interface` 關鍵字來定義，並可以被類別實現。實現介面的類別需要提供介面中所有方法的具體實作。

### 詳細資訊
- 介面可以擁有屬性，但這些屬性必須是抽象的，不能初始化。
- 介面可以包含方法的具體實作，這稱為「預設方法」。
- 一個類別可以實現多個介面，這使得 Kotlin 支援多重繼承的特性。

## 例子
以下是 Kotlin 中定義和使用介面的基本範例：

```kotlin
// 定義介面
interface Drivable {
    val speed: Int
    fun drive(): String
}

// 實現介面
class Car : Drivable {
    override val speed: Int = 100

    override fun drive(): String {
        return "Driving at $speed km/h"
    }
}

fun main() {
    val myCar = Car()
    println(myCar.drive()) // 輸出: Driving at 100 km/h
}
```

## 解釋
在使用介面時，開發者需注意以下幾點：

1. **方法的實作**：如果類別實現了介面，則必須提供所有抽象方法的具體實作，否則類別會被視為抽象類別。
2. **屬性初始值**：介面中的屬性不可以直接初始化，必須由實現介面的類別提供具體的值。
3. **多重介面實作**：如果一個類別實現多個介面，需特別注意方法的名稱衝突，可能需要使用 `super` 關鍵字來指定具體的介面方法。

## 總結
Kotlin 的介面是設計靈活且功能強大的工具，能有效促進程式碼的重用和可維護性。