<!--
Meta Description: # Kotlin 中的 Override 關鍵字：覆寫方法與屬性 ## 摘要 在 Kotlin 中，`override` 關鍵字用於覆寫父類別中的方法或屬性，允許子類別提供其特定的實現。這是物件導向程式設計中的一個重要特性，使得多型性得以實現。 ## 文檔 ### 目的 `override` 關鍵字...
Meta Keywords: override, kotlin, open, class, fun
-->

# Kotlin 中的 Override 關鍵字：覆寫方法與屬性

## 摘要
在 Kotlin 中，`override` 關鍵字用於覆寫父類別中的方法或屬性，允許子類別提供其特定的實現。這是物件導向程式設計中的一個重要特性，使得多型性得以實現。

## 文檔
### 目的
`override` 關鍵字的主要目的是在子類別中定義與父類別相同名稱的方法或屬性，以便提供更具體的實現。這使得子類別能夠擴展或修改父類別的行為。

### 使用方法
在 Kotlin 中，若要覆寫父類別的方法或屬性，需遵循以下步驟：
1. 在父類別中聲明方法或屬性時，必須標記為 `open`，以允許子類別進行覆寫。
2. 在子類別中使用 `override` 關鍵字來覆寫父類別的方法或屬性。

### 詳細說明
- **方法覆寫**：當子類別需要改變父類別的方法行為時，必須使用 `override` 關鍵字。這不僅能提高可讀性，還能避免錯誤。
- **屬性覆寫**：同樣地，子類別可以覆寫父類別的屬性，使用 `override` 關鍵字來提供新的實現。
- **多型性**：利用覆寫，Kotlin 支持多型性，讓子類別對父類別的方法進行特定實現，從而提高代碼的靈活性與可重用性。

## 範例
以下是如何使用 `override` 關鍵字的基本示例：

### 方法覆寫示例
```kotlin
open class Animal {
    open fun sound() {
        println("動物發出聲音")
    }
}

class Dog : Animal() {
    override fun sound() {
        println("汪汪")
    }
}

fun main() {
    val dog = Dog()
    dog.sound()  // 輸出：汪汪
}
```

### 屬性覆寫示例
```kotlin
open class Vehicle {
    open val maxSpeed: Int = 120
}

class Car : Vehicle() {
    override val maxSpeed: Int = 150
}

fun main() {
    val car = Car()
    println(car.maxSpeed)  // 輸出：150
}
```

## 解釋
在使用 `override` 時，需注意以下幾點：
- **父類別方法必須標記為 `open`**：若父類別的方法未標記為 `open`，則無法覆寫。
- **方法簽名必須一致**：覆寫的方法必須與父類別的方法簽名完全一致，包括參數類型和返回類型。
- **不可覆寫的情況**：如果父類別的方法是 `final`，則子類別無法使用 `override` 進行覆寫，這是為了防止不必要的行為改變。

## 一句總結
在 Kotlin 中，`override` 關鍵字用於允許子類別覆寫父類別的方法和屬性，實現更加靈活的物件導向程式設計。