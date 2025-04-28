<!--
Meta Description: # Kotlin 中的 Sealed 類型：深入探討及使用指南 ## 概述 Sealed 類型是 Kotlin 中的一種特殊類型，允許開發者定義一組受限的子類別，這可以提高類別的安全性和可讀性。透過 Sealed 類型，開發者可以在編譯時確保所有可能的類型都已被處理，這對於使用 when 表達式時特...
Meta Keywords: sealed, shape, data, class, result
-->

# Kotlin 中的 Sealed 類型：深入探討及使用指南

## 概述
Sealed 類型是 Kotlin 中的一種特殊類型，允許開發者定義一組受限的子類別，這可以提高類別的安全性和可讀性。透過 Sealed 類型，開發者可以在編譯時確保所有可能的類型都已被處理，這對於使用 when 表達式時特別有用。

## 文件說明
Sealed 類型的主要目的是限制類別的繼承，使得所有的子類別都必須在同一個文件中定義。這樣可以確保開發者知道所有可能的類型，並在需要時進行處理。Sealed 類型不能被外部類別繼承，這樣可以強化類型的封閉性。

### 用法
要定義一個 Sealed 類型，可以使用 `sealed class` 關鍵字。這個類型可以包含多個子類別，這些子類別可以是數據類（data classes）或普通類別。

```kotlin
sealed class Result

data class Success(val data: String) : Result()
data class Error(val exception: Exception) : Result()
```

在使用時，開發者可以利用 when 表達式進行模式匹配，因為編譯器知道所有可能的子類型。

```kotlin
fun handleResult(result: Result) {
    when (result) {
        is Success -> println("成功: ${result.data}")
        is Error -> println("錯誤: ${result.exception.message}")
    }
}
```

## 範例
以下是幾個使用 Sealed 類型的基本範例：

### 範例 1：簡單的 Sealed 類型
```kotlin
sealed class Shape {
    data class Circle(val radius: Double) : Shape()
    data class Rectangle(val width: Double, val height: Double) : Shape()
}

fun area(shape: Shape): Double {
    return when (shape) {
        is Shape.Circle -> Math.PI * shape.radius * shape.radius
        is Shape.Rectangle -> shape.width * shape.height
    }
}
```

### 範例 2：帶有多個子類的 Sealed 類型
```kotlin
sealed class NetworkResponse {
    object Loading : NetworkResponse()
    data class Success(val data: String) : NetworkResponse()
    data class Failure(val error: String) : NetworkResponse()
}

fun handleResponse(response: NetworkResponse) {
    when (response) {
        is NetworkResponse.Loading -> println("載入中...")
        is NetworkResponse.Success -> println("成功: ${response.data}")
        is NetworkResponse.Failure -> println("失敗: ${response.error}")
    }
}
```

## 解釋
使用 Sealed 類型的時候，有幾個常見的陷阱和注意事項：

1. **封閉性**：Sealed 類型只能在同一個文件中定義所有子類別。這意味著如果你需要擴展功能，必須在原有文件中添加新的子類別。
2. **when 表達式要求**：當使用 when 表達式處理 Sealed 類型時，如果沒有處理所有的子類別，編譯器會發出警告。這是 Sealed 類型的一個優勢，確保所有情況都被考慮到。
3. **無法實例化**：Sealed 類型本身不能被實例化；只能創建其子類的實例。

## 簡短總結
Kotlin 的 Sealed 類型允許開發者定義一組受限的子類別，提供了更高的類型安全性和編譯時檢查。