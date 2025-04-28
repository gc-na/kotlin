<!--
Meta Description: # Kotlin 中的 "when" 表達式：用法與示例 ## 摘要 Kotlin 的 "when" 表達式是一種控制流結構，類似於其他編程語言中的 switch 語句。它允許根據不同的條件選擇執行不同的代碼塊，適用於處理多個條件的情境。 ## 文件說明 "when" 表達式的主要目的是為了簡化多條...
Meta Keywords: when, println, kotlin, else, 表達式
-->

# Kotlin 中的 "when" 表達式：用法與示例

## 摘要
Kotlin 的 "when" 表達式是一種控制流結構，類似於其他編程語言中的 switch 語句。它允許根據不同的條件選擇執行不同的代碼塊，適用於處理多個條件的情境。

## 文件說明
"when" 表達式的主要目的是為了簡化多條件的分支判斷。相比傳統的 if-else 結構，"when" 提供了更清晰和簡潔的語法，能夠有效地處理多個條件分支。

### 用法
在 Kotlin 中，"when" 表達式的基本語法如下：

```kotlin
when (表達式) {
    條件1 -> 執行的代碼1
    條件2 -> 執行的代碼2
    else -> 執行的代碼3
}
```

- **表達式**：要進行匹配的值。
- **條件**：可以是具體的值、範圍或類型檢查。
- **else**：可選項，當沒有其他條件匹配時執行的代碼。

### 詳細說明
"when" 表達式可以用來替代多重的 if-else 結構，並且能夠處理更多樣的情況，例如：

- 匹配具體值。
- 使用範圍進行匹配。
- 根據類型進行條件判斷。

## 示例
以下是一些使用 "when" 的基本示例：

### 範例 1：簡單值匹配
```kotlin
val x = 2
when (x) {
    1 -> println("x 是 1")
    2 -> println("x 是 2")
    3 -> println("x 是 3")
    else -> println("x 是其他值")
}
```

### 範例 2：範圍匹配
```kotlin
val y = 15
when (y) {
    in 1..10 -> println("y 在 1 到 10 之間")
    in 11..20 -> println("y 在 11 到 20 之間")
    else -> println("y 超出範圍")
}
```

### 範例 3：類型檢查
```kotlin
fun checkType(value: Any) {
    when (value) {
        is String -> println("這是一個字符串")
        is Int -> println("這是一個整數")
        else -> println("未知類型")
    }
}
```

## 解釋
使用 "when" 表達式時，需注意以下幾點：

- **落入 else 區塊**：如果所有條件都不符合，則會執行 else 區塊，這是處理預設情況的好方法。
- **同時匹配多個條件**：可以使用逗號分隔多個條件，例如：
  
  ```kotlin
  when (x) {
      1, 2 -> println("x 是 1 或 2")
      else -> println("x 是其他值")
  }
  ```

- **不需要 break**：在 Kotlin 中，"when" 表達式不需要像 C 語言中的 switch 一樣使用 break 語句來終止執行。

## 總結
Kotlin 的 "when" 表達式是一個強大且靈活的控制流工具，提供了多條件判斷的簡明解決方案。