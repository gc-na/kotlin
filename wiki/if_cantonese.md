<!--
Meta Description: # Kotlin 中的 "if" 語句：條件判斷的利器 ## 概述 在 Kotlin 中，`if` 語句是一個強大的條件判斷工具，用於控制程式的執行流程。它可以用來根據特定條件執行不同的代碼塊，並且可以作為表達式返回值。 ## 文件說明 `if` 語句的主要目的是根據布林條件判斷執行哪一段代碼。Ko...
Meta Keywords: kotlin, else, val, println, score
-->

# Kotlin 中的 "if" 語句：條件判斷的利器

## 概述
在 Kotlin 中，`if` 語句是一個強大的條件判斷工具，用於控制程式的執行流程。它可以用來根據特定條件執行不同的代碼塊，並且可以作為表達式返回值。

## 文件說明
`if` 語句的主要目的是根據布林條件判斷執行哪一段代碼。Kotlin 的 `if` 不僅限於語句，還可以作為表達式使用，這意味著它可以返回一個值。這使得 `if` 在函數或變量賦值中非常有用。

### 語法
基本的 `if` 語句語法如下：
```kotlin
if (condition) {
    // 當 condition 為 true 時執行的代碼
} else {
    // 當 condition 為 false 時執行的代碼
}
```

### 作為表達式
如果需要將 `if` 用作一個表達式，則可以這樣寫：
```kotlin
val max = if (a > b) a else b
```
這將返回 `a` 或 `b` 中的較大者。

## 範例
以下是一些基本的 `if` 語句的使用範例：

### 範例 1：基本用法
```kotlin
val number = 10
if (number > 0) {
    println("正數")
} else {
    println("非正數")
}
```

### 範例 2：作為表達式
```kotlin
val a = 5
val b = 10
val max = if (a > b) a else b
println("較大值是：$max")
```

### 範例 3：多重條件
```kotlin
val score = 85
val grade = if (score >= 90) {
    "A"
} else if (score >= 80) {
    "B"
} else if (score >= 70) {
    "C"
} else {
    "D"
}
println("你的成績是：$grade")
```

## 解釋
使用 `if` 時，需要留意以下幾點：

1. **條件必須是布林類型**：`if` 語句的條件必須返回 `true` 或 `false`，否則會出現編譯錯誤。
2. **不需要括號**：Kotlin 中的 `if` 語句不需要使用括號來包圍條件，但這在其他語言中可能是必需的。
3. **可以省略 else**：如果只需要在條件為 `true` 時執行代碼，而不需要在 `false` 時執行任何操作，可以省略 `else` 部分。

## 一句總結
Kotlin 的 `if` 語句是一個靈活且強大的條件判斷工具，能夠根據條件控制程式的執行流程。