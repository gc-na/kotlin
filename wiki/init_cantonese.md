<!--
Meta Description: # Kotlin 中的 init：初始化區塊的功能和用法 ## 簡介 在 Kotlin 編程語言中，`init` 是一個關鍵字，用於類的初始化區塊。它允許開發者在創建對象時執行代碼，以確保對象的正確初始化。 ## 文檔 `init` 區塊是 Kotlin 類中的一個特殊初始化區塊。當創建類的實例時，...
Meta Keywords: init, kotlin, val, age, car
-->

# Kotlin 中的 init：初始化區塊的功能和用法

## 簡介
在 Kotlin 編程語言中，`init` 是一個關鍵字，用於類的初始化區塊。它允許開發者在創建對象時執行代碼，以確保對象的正確初始化。

## 文檔
`init` 區塊是 Kotlin 類中的一個特殊初始化區塊。當創建類的實例時，`init` 區塊會在主構造函數被調用之後自動執行。這使得開發者能夠在對象創建時執行一些必要的初始化代碼，例如設置默認值或執行驗證。

### 用法
- **位置**: `init` 區塊必須位於類的主構造函數內部。
- **多個區塊**: 一個類可以有多個 `init` 區塊，這些區塊將按照它們在類中出現的順序執行。

### 詳情
`init` 區塊可以訪問主構造函數的參數，以及類中的其他屬性。這使得它非常靈活，能夠在對象創建時進行多種操作。

```kotlin
class Person(val name: String, var age: Int) {
    init {
        println("新建了一個人：$name，年齡：$age")
        if (age < 0) {
            throw IllegalArgumentException("年齡不能為負數！")
        }
    }
}
```

## 範例
以下是使用 `init` 區塊的基本示例：

```kotlin
class Car(val model: String, val year: Int) {
    init {
        println("新車型：$model，年份：$year")
    }
}

fun main() {
    val myCar = Car("Tesla", 2021)
}
```

這段代碼將在創建 `Car` 對象時輸出車型和年份。

## 解釋
### 常見陷阱
- **初始化順序**: 如果類中有多個 `init` 區塊，請注意它們的執行順序。這可能會影響初始化的邏輯。
- **不可變性**: 在 `init` 區塊中，請確保不嘗試更改主構造函數中的 `val` 參數，因為這會導致編譯錯誤。
- **異常處理**: 如果在 `init` 區塊中引發異常，則對象將無法成功創建。

## 一句總結
Kotlin 的 `init` 區塊提供了一種靈活的方式來在對象創建時進行初始化操作，確保對象處於有效狀態。