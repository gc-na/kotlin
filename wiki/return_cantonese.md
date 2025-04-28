<!--
Meta Description: # Kotlin 中的 "return" 關鍵字使用指南 ## 概述 在 Kotlin 中，`return` 關鍵字用來從函數或 lambda 表達式中返回一個值。這是函數編程中的一個基本概念，能夠讓開發者控制函數的執行流程並返回計算結果。 ## 文檔 `return` 的主要用途是終止函數的執行並...
Meta Keywords: return, kotlin, int, lambda, fun
-->

# Kotlin 中的 "return" 關鍵字使用指南

## 概述
在 Kotlin 中，`return` 關鍵字用來從函數或 lambda 表達式中返回一個值。這是函數編程中的一個基本概念，能夠讓開發者控制函數的執行流程並返回計算結果。

## 文檔
`return` 的主要用途是終止函數的執行並返回指定的值。Kotlin 支援多種函數類型，包括普通函數、擴展函數及 lambda 表達式。在使用 `return` 時，需確保所返回的值符合函數的返回類型。

### 語法
```kotlin
fun functionName(parameters): ReturnType {
    // 函數邏輯
    return value
}
```

### 使用方式
- 在函數中使用 `return` 返回計算結果。
- 在 lambda 表達式中使用 `return` 來從外部函數返回值。

## 範例
以下是一些基本使用範例：

### 簡單函數
```kotlin
fun add(a: Int, b: Int): Int {
    return a + b
}

fun main() {
    val result = add(5, 3)
    println(result) // 輸出：8
}
```

### 使用 lambda 表達式
```kotlin
val multiply: (Int, Int) -> Int = { a, b ->
    return@multiply a * b
}

fun main() {
    val result = multiply(4, 2)
    println(result) // 輸出：8
}
```

### 在條件語句中使用
```kotlin
fun checkNumber(num: Int): String {
    return if (num > 0) {
        "正數"
    } else if (num < 0) {
        "負數"
    } else {
        "零"
    }
}

fun main() {
    println(checkNumber(10)) // 輸出：正數
}
```

## 解釋
使用 `return` 時，開發者需注意以下幾點：
- 確保返回的值符合函數的預期返回類型，否則會導致編譯錯誤。
- 在 lambda 表達式中，使用標籤（例如 `return@multiply`）來指定要返回的上下文，這有助於防止意外的返回行為。
- 在某些情況下，過度使用 `return` 可能會使程式碼的可讀性降低，應謹慎使用。

## 一句總結
`return` 關鍵字在 Kotlin 中用於從函數或 lambda 表達式中返回值，控制函數的執行流程及結果。