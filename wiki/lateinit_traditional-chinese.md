<!--
Meta Description: # Kotlin 的 lateinit 關鍵字使用指南 ## 摘要 在 Kotlin 中，`lateinit` 是一個用於延遲初始化變數的關鍵字，允許開發者在變數被聲明後稍後進行初始化，特別適用於非空類型的變數。 ## 文件說明 `lateinit` 關鍵字主要用於類的可變屬性，允許開發者在不立即初...
Meta Keywords: lateinit, user, name, kotlin, var
-->

# Kotlin 的 lateinit 關鍵字使用指南

## 摘要
在 Kotlin 中，`lateinit` 是一個用於延遲初始化變數的關鍵字，允許開發者在變數被聲明後稍後進行初始化，特別適用於非空類型的變數。

## 文件說明
`lateinit` 關鍵字主要用於類的可變屬性，允許開發者在不立即初始化變數的情況下聲明它。這對於依賴於外部因素（如依賴注入或 Android 的視圖）初始化的變數非常有用。使用 `lateinit` 的變數必須是可變的（即使用 `var` 聲明），並且不能是基本數據類型（如 `Int`、`Boolean` 等）。

### 用法
要使用 `lateinit`，只需在變數聲明前加上 `lateinit` 關鍵字。例如：

```kotlin
lateinit var myVar: String
```

這樣聲明的變數 `myVar` 可以在稍後的時間進行初始化。需要注意的是，在使用 `myVar` 前必須確保它已經被初始化，否則會引發 `UninitializedPropertyAccessException` 異常。

## 範例
以下是 `lateinit` 的基本用法示例：

```kotlin
class User {
    lateinit var name: String

    fun initializeName() {
        name = "Alice"
    }

    fun printName() {
        if (::name.isInitialized) {
            println(name)
        } else {
            println("Name is not initialized")
        }
    }
}

fun main() {
    val user = User()
    user.printName() // 輸出: Name is not initialized
    user.initializeName()
    user.printName() // 輸出: Alice
}
```

## 解釋
在使用 `lateinit` 時，有幾個常見的陷阱需要注意：

1. **必須是可變屬性**：`lateinit` 只能用於 `var`，不能用於 `val`，因為 `val` 需要在聲明時立即初始化。
2. **不能用於基本數據類型**：`lateinit` 不能用於如 `Int`、`Boolean` 等基本數據類型，僅適用於引用類型。
3. **初始化檢查**：在使用 `lateinit` 變數之前，應該使用 `::propertyName.isInitialized` 來檢查變數是否已經初始化，以避免異常。
4. **使用場景**：`lateinit` 通常在 Android 開發中非常有用，例如在 Activity 或 Fragment 中延遲初始化 UI 元件。

## 一句總結
`lateinit` 是 Kotlin 中用於延遲初始化非空可變屬性的關鍵字，能有效提高代碼的靈活性和可讀性。