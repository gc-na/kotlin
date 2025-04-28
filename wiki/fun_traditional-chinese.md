<!--
Meta Description: # Kotlin 中的 fun 關鍵字：函數定義與使用 ## 概述 `fun` 是 Kotlin 語言中用於定義函數的關鍵字。函數是 Kotlin 的基本構建塊，允許開發者將代碼邏輯封裝在可重用的單元中。 ## 文件說明 在 Kotlin 中，`fun` 關鍵字用來聲明函數。函數可以接收參數並返回值...
Meta Keywords: kotlin, fun, return, main, println
-->

# Kotlin 中的 fun 關鍵字：函數定義與使用

## 概述
`fun` 是 Kotlin 語言中用於定義函數的關鍵字。函數是 Kotlin 的基本構建塊，允許開發者將代碼邏輯封裝在可重用的單元中。

## 文件說明
在 Kotlin 中，`fun` 關鍵字用來聲明函數。函數可以接收參數並返回值，也可以不返回任何值。使用 `fun` 可以提高代碼的模組化和可讀性，使得複雜的邏輯被簡化為清晰的操作。

### 語法
```kotlin
fun functionName(parameter1: Type1, parameter2: Type2): ReturnType {
    // 函數體
    return value
}
```

### 參數與返回類型
- **functionName**：函數的名稱，遵循標識符命名規則。
- **parameter**：函數接收的參數，可以有多個，使用逗號分隔。
- **ReturnType**：函數返回的類型；若無返回值，則可以省略，或使用 `Unit`。

## 範例
### 定義和調用簡單函數
```kotlin
fun greet(name: String): String {
    return "Hello, $name!"
}

fun main() {
    println(greet("Kotlin"))  // 輸出: Hello, Kotlin!
}
```

### 無參數無返回值的函數
```kotlin
fun printGreeting() {
    println("Welcome to Kotlin!")
}

fun main() {
    printGreeting()  // 輸出: Welcome to Kotlin!
}
```

### 帶有多個參數的函數
```kotlin
fun add(x: Int, y: Int): Int {
    return x + y
}

fun main() {
    println(add(5, 10))  // 輸出: 15
}
```

## 解釋
在使用 `fun` 定義函數時，開發者需要注意以下幾點：
- 函數名稱必須唯一，不能與其他函數或變數衝突。
- 如果函數不返回任何值，則可以省略返回類型，默認為 `Unit`。
- Kotlin 支援默認參數和命名參數，可以使函數調用更加靈活。

常見的陷阱包括：
1. 忘記指定返回類型，雖然 Kotlin 可以推斷類型，但明確性有助於提高代碼可讀性。
2. 在使用可變參數時，需注意傳遞的參數類型。

## 一句話總結
`fun` 關鍵字在 Kotlin 中用於定義函數，是構建應用邏輯的基本組件。