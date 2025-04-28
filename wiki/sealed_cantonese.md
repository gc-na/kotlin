<!--
Meta Description: # Kotlin 的 Sealed 類型：強類型的封閉類別 ## 簡介 Kotlin 的 Sealed 類型提供了一種安全的方式來定義有限的類別階層，它允許開發者在編譯時期控制類別的繼承。這對於需要對一組相關類型進行模式匹配的情況特別有用。 ## 文檔 Sealed 類型是 Kotlin 中的一種特...
Meta Keywords: sealed, shape, kotlin, class, data
-->

# Kotlin 的 Sealed 類型：強類型的封閉類別

## 簡介
Kotlin 的 Sealed 類型提供了一種安全的方式來定義有限的類別階層，它允許開發者在編譯時期控制類別的繼承。這對於需要對一組相關類型進行模式匹配的情況特別有用。

## 文檔
Sealed 類型是 Kotlin 中的一種特殊類型，可以用來定義一組有限的子類。這些子類必須在同一個文件中聲明，這樣編譯器就能夠檢查所有可能的子類。Sealed 類型常用於需要穩定和可預測的類別結構的情況，例如處理狀態、事件或命令。

### 目的
- 提供穩定的類別結構：Sealed 類型使得類別的繼承關係更加清晰，易於管理。
- 提升安全性：編譯器將檢查是否處理所有可能的子類，避免了意外的錯誤。

### 使用方法
要定義一個 Sealed 類型，只需將類別聲明為 `sealed`，然後可以在同一個文件中定義其子類。例如：

```kotlin
sealed class Result {
    data class Success(val data: String) : Result()
    data class Error(val exception: Exception) : Result()
}
```

在這個例子中，`Result` 是一個 Sealed 類型，它有兩個子類 `Success` 和 `Error`。

## 範例
以下是使用 Sealed 類型的基本範例：

```kotlin
sealed class Shape {
    data class Circle(val radius: Double) : Shape()
    data class Rectangle(val width: Double, val height: Double) : Shape()
}

fun describeShape(shape: Shape): String {
    return when (shape) {
        is Shape.Circle -> "這是一個圓形，半徑為 ${shape.radius}"
        is Shape.Rectangle -> "這是一個矩形，寬度為 ${shape.width}，高度為 ${shape.height}"
    }
}
```

在這個例子中，`Shape` 是一個 Sealed 類型，`describeShape` 函數使用 `when` 表達式來安全地處理所有可能的 `Shape` 子類。

## 解釋
在使用 Sealed 類型時，開發者需要注意以下幾點：

- **子類必須在同一文件中定義**：Sealed 類型的子類必須在同一個文件中聲明，這樣才能保持其封閉性。
- **無法直接實例化 Sealed 類型**：Sealed 類型本身不能被實例化，只能通過其子類創建實例。
- **與 `when` 表達式結合使用**：Sealed 類型與 `when` 表達式非常搭配，能夠保證所有子類都被處理，編譯器會報告未處理的情況。

## 總結
Kotlin 的 Sealed 類型提供了一種強類型的方式來定義封閉的類別階層，增強了安全性和可預測性，是處理有限類型的一個強大工具。