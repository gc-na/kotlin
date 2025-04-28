<!--
Meta Description: # Kotlin 中的 "break" 語句：用法與示例 ## 簡介 在 Kotlin 中，`break` 語句用於立即終止循環結構的執行，常見於 `for`、`while` 和 `do...while` 循環。這個語句可以幫助開發者在滿足特定條件時提前退出循環。 ## 文檔 `break` 語句的...
Meta Keywords: break, kotlin, while, number, println
-->

# Kotlin 中的 "break" 語句：用法與示例

## 簡介
在 Kotlin 中，`break` 語句用於立即終止循環結構的執行，常見於 `for`、`while` 和 `do...while` 循環。這個語句可以幫助開發者在滿足特定條件時提前退出循環。

## 文檔
`break` 語句的主要目的是提供一種控制循環流程的方法，允許開發者根據條件中斷循環的執行。這在需要根據特定邏輯（如找到特定元素或達到某個條件）停止循環時非常有用。

### 用法
在 Kotlin 中，`break` 語句通常用於循環結構內部。當 `break` 被執行時，控制流將跳出最近的循環結構，並繼續執行循環之後的代碼。

#### 基本語法：
```kotlin
for (item in collection) {
    if (condition) {
        break
    }
    // 其他代碼
}
```

## 示例
以下是幾個使用 `break` 語句的基本示例：

### 示例 1：使用 `break` 中斷 `for` 循環
```kotlin
val numbers = listOf(1, 2, 3, 4, 5)

for (number in numbers) {
    if (number == 3) {
        break
    }
    println(number) // 輸出 1, 2
}
```

### 示例 2：使用 `break` 中斷 `while` 循環
```kotlin
var i = 0

while (i < 5) {
    if (i == 3) {
        break
    }
    println(i) // 輸出 0, 1, 2
    i++
}
```

### 示例 3：在巢狀循環中使用 `break`
```kotlin
for (i in 1..3) {
    for (j in 1..3) {
        if (j == 2) {
            break
        }
        println("i: $i, j: $j") // 輸出 i: 1, j: 1; i: 2, j: 1; i: 3, j: 1
    }
}
```

## 解釋
在使用 `break` 時，開發者需要注意以下幾點：

1. **控制流**：`break` 只會終止最近的循環。如果有多層嵌套循環，`break` 只能退出最內層的循環。
2. **不可用於函數**：`break` 只能在循環內部使用，不能在函數或其他非循環結構中使用。
3. **可讀性**：過度使用 `break` 可能會影響代碼可讀性，尤其是在複雜邏輯中，應合理安排代碼結構。

## 單行摘要
`break` 語句在 Kotlin 中用於立即終止循環的執行，根據特定條件控制循環流程。