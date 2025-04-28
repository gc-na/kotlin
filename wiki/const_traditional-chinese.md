<!--
Meta Description: # Kotlin 的 `const` 關鍵字：靜態常量的強大功能 ## 概述 在 Kotlin 中，`const` 關鍵字用於定義編譯時常量，這些常量的值在編譯時就已確定，並且不可變。這使得 `const` 成為優化性能和增加代碼可讀性的理想選擇。 ## 文檔 `const` 關鍵字僅用於 `val...
Meta Keywords: const, val, kotlin, base_url, timeout_seconds
-->

# Kotlin 的 `const` 關鍵字：靜態常量的強大功能

## 概述
在 Kotlin 中，`const` 關鍵字用於定義編譯時常量，這些常量的值在編譯時就已確定，並且不可變。這使得 `const` 成為優化性能和增加代碼可讀性的理想選擇。

## 文檔
`const` 關鍵字僅用於 `val` 修飾符，並且必須在頂層或伴隨對象中聲明。使用 `const` 聲明的常量必須是基本數據類型（如 `Int`、`Double`、`Boolean` 和 `String`），這意味著它們在編譯期間的值是確定的且不會改變。

### 用法
以下是 `const` 的基本用法：

```kotlin
const val MAX_COUNT = 100
const val PI = 3.14
const val APP_NAME = "MyKotlinApp"
```

在上述示例中，`MAX_COUNT`、`PI` 和 `APP_NAME` 都是編譯時常量，可以在整個應用程序中使用。

## 範例
以下是使用 `const` 的一些基本範例：

```kotlin
const val BASE_URL = "https://api.example.com/"
const val TIMEOUT_SECONDS = 30

fun fetchData() {
    println("Fetching data from $BASE_URL with a timeout of $TIMEOUT_SECONDS seconds.")
}
```

在這個例子中，我們定義了 `BASE_URL` 和 `TIMEOUT_SECONDS` 兩個常量，並在 `fetchData` 函數中使用它們。

## 解釋
使用 `const` 時，有幾個常見的陷阱和注意事項：

1. **僅限於頂層或伴隨對象**：`const` 只能在頂層聲明或伴隨對象中使用，無法在類內部的函數中使用。
  
2. **類型限制**：`const` 只支持基本數據類型和 `String`，這意味著不能用於其他類型（如集合或自定義對象）。

3. **不可變性**：使用 `const` 聲明的變量是不可變的，這意味著一旦賦值後不能再次更改。

4. **編譯時常量**：`const` 的值在編譯時就確定，這使得它對於性能優化特別有用，因為編譯器可以在編譯過程中進行優化。

## 一句總結
在 Kotlin 中，`const` 關鍵字用於定義編譯時常量，以提高代碼的性能和可讀性。