<!--
Meta Description: # Kotlin 中的 else 語句：用法、示例及注意事項 ## 簡介 在 Kotlin 中，`else` 語句是條件控制結構的一部分，通常與 `if` 語句一起使用。它用於處理當條件不符合時的情況，提供了一種清晰的方式來執行替代的代碼塊。 ## 文檔 `else` 語句的主要目的是在 `if` ...
Meta Keywords: else, kotlin, println, 時執行的代碼, score
-->

# Kotlin 中的 else 語句：用法、示例及注意事項

## 簡介
在 Kotlin 中，`else` 語句是條件控制結構的一部分，通常與 `if` 語句一起使用。它用於處理當條件不符合時的情況，提供了一種清晰的方式來執行替代的代碼塊。

## 文檔
`else` 語句的主要目的是在 `if` 條件不滿足時執行特定的代碼。這使得開發者能夠在不同的條件下選擇不同的行為，從而增加程式的靈活性和可讀性。

### 用法
`else` 語句通常是與 `if` 語句配合使用的，可以寫成以下格式：

```kotlin
if (condition) {
    // 當 condition 為 true 時執行的代碼
} else {
    // 當 condition 為 false 時執行的代碼
}
```

你還可以使用 `else if` 來處理多個條件：

```kotlin
if (condition1) {
    // 當 condition1 為 true 時執行的代碼
} else if (condition2) {
    // 當 condition2 為 true 時執行的代碼
} else {
    // 當以上條件都不滿足時執行的代碼
}
```

## 示例
以下是使用 `else` 的基本示例：

```kotlin
fun main() {
    val number = 10

    if (number > 0) {
        println("數字是正數")
    } else {
        println("數字不是正數")
    }
}
```

在這個示例中，當 `number` 大於 0 時，將打印 "數字是正數"；否則，將打印 "數字不是正數"。

另一個示例如下：

```kotlin
fun main() {
    val score = 85

    if (score >= 90) {
        println("等級：A")
    } else if (score >= 80) {
        println("等級：B")
    } else {
        println("等級：C")
    }
}
```

在這個例子中，根據 `score` 的值，將打印不同的等級。

## 解釋
使用 `else` 時需要注意幾個常見的陷阱：

1. **忽略 else 的必要性**：如果你的邏輯需要處理所有情況，務必確保有 `else` 來處理未預見的情況。
  
2. **嵌套的結構**：在使用嵌套的 `if-else` 結構時，代碼可讀性可能會下降，建議適當使用函數來簡化邏輯。

3. **Boolean 表達式**：確保 `if` 條件是有效的布林表達式，否則會導致編譯錯誤。

## 一句總結
在 Kotlin 中，`else` 語句用於處理 `if` 條件不符合時的情況，增強程式的邏輯和可讀性。