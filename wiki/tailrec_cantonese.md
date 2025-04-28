<!--
Meta Description: # Kotlin 尾遞歸 (tailrec) 用法詳解 ## 簡介 在 Kotlin 中，`tailrec` 是一個關鍵字，用於優化遞迴函數，以避免堆疊溢出問題。當一個遞迴函數使用尾遞歸時，編譯器會將其轉換為迴圈，從而提高性能和效率。 ## 文檔 `tailrec` 是 Kotlin 提供的一個特性...
Meta Keywords: tailrec, int, kotlin, fun, factorial
-->

# Kotlin 尾遞歸 (tailrec) 用法詳解

## 簡介
在 Kotlin 中，`tailrec` 是一個關鍵字，用於優化遞迴函數，以避免堆疊溢出問題。當一個遞迴函數使用尾遞歸時，編譯器會將其轉換為迴圈，從而提高性能和效率。

## 文檔
`tailrec` 是 Kotlin 提供的一個特性，主要用於提高函數的遞迴性能。當一個函數的最後一個操作是對自身的調用時，可以使用 `tailrec`。這樣，編譯器能夠將遞迴調用轉換為循環，減少堆疊深度，從而避免因為過多的遞迴層次而導致的堆疊溢出。

### 用法
在函數前加上 `tailrec` 來聲明這是一個尾遞歸函數。函數必須滿足以下條件：
1. 最後一個操作是對函數自身的調用。
2. 參數必須在調用時以相同的方式傳遞。

### 詳情
若函數未能滿足尾遞歸的條件，編譯器將報錯，提示該函數無法被標記為 `tailrec`。這一特性對於大多數遞迴算法（如斐波那契數列、階乘等）的性能優化特別有用。

## 範例
以下是使用 `tailrec` 的基本範例：

### 範例 1：計算階乘
```kotlin
tailrec fun factorial(n: Int, acc: Int = 1): Int {
    return if (n == 0) acc else factorial(n - 1, n * acc)
}

fun main() {
    println(factorial(5))  // 輸出：120
}
```

### 範例 2：計算斐波那契數列
```kotlin
tailrec fun fibonacci(n: Int, a: Int = 0, b: Int = 1): Int {
    return if (n == 0) a else fibonacci(n - 1, b, a + b)
}

fun main() {
    println(fibonacci(7))  // 輸出：13
}
```

## 解釋
使用 `tailrec` 時需注意以下幾點：
- 只有當遞迴調用是函數的最後一個操作時，才能使用 `tailrec`。
- 如果有其他操作（例如，計算或條件判斷）在遞迴調用之後，編譯器將無法進行優化。
- `tailrec` 不會在所有情況下都能提高性能，具體效果取決於函數的結構。

## 總結
`tailrec` 是 Kotlin 的一個強大特性，可用於優化尾遞歸函數，從而提高性能並避免堆疊溢出。