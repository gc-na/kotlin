<!--
Meta Description: # Kotlin 中的 lateinit：用法與注意事項 ## 概要 `lateinit` 是 Kotlin 語言中的一個特性，用於聲明延遲初始化的變數，讓開發者能夠在稍後的時間為變數賦值，而不需要在宣告時即進行初始化。 ## 文檔 ### 目的 `lateinit` 主要用於變數的延遲初始化，特別...
Meta Keywords: lateinit, kotlin, name, textview, var
-->

# Kotlin 中的 lateinit：用法與注意事項

## 概要
`lateinit` 是 Kotlin 語言中的一個特性，用於聲明延遲初始化的變數，讓開發者能夠在稍後的時間為變數賦值，而不需要在宣告時即進行初始化。

## 文檔
### 目的
`lateinit` 主要用於變數的延遲初始化，特別適合於需要依賴外部資源或在某些條件下初始化的情況。這在 Android 開發中特別常見，因為某些 UI 元素可能在 Activity 或 Fragment 的生命週期中才會被初始化。

### 使用方法
要使用 `lateinit`，只需在變數聲明時加上 `lateinit` 修飾符。此變數必須是可變的（即 `var`），並且不能是基本類型（如 `Int`、`Boolean` 等）。

#### 語法：
```kotlin
lateinit var variableName: Type
```

### 詳細說明
- **初始化要求**：在使用 `lateinit` 變數之前，必須確保它已被初始化。否則，訪問未初始化的變數會導致 `UninitializedPropertyAccessException` 錯誤。
- **基本類型不得使用**：`lateinit` 只能用於引用類型，基本類型（如 `Int`、`Double` 等）不能使用 `lateinit`。
- **可調用的屬性**：可以使用 `isInitialized()` 方法檢查 `lateinit` 變數是否已經初始化。

## 示例
以下是一些基本的 `lateinit` 使用示例：

### 示例 1：基本用法
```kotlin
class Example {
    lateinit var name: String

    fun initialize() {
        name = "Kotlin"
    }

    fun printName() {
        if (::name.isInitialized) {
            println(name)
        } else {
            println("Name is not initialized")
        }
    }
}
```

### 示例 2：在 Android 中使用
```kotlin
class MainActivity : AppCompatActivity() {
    private lateinit var textView: TextView

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        textView = findViewById(R.id.textView)
        textView.text = "Hello, Kotlin!"
    }
}
```

## 說明
- **常見陷阱**：未初始化的 `lateinit` 變數在使用前未進行檢查，會導致應用崩潰。總是應該檢查變數是否已初始化。
- **可見性問題**：`lateinit` 變數的可見性可能在不同的上下文中影響其使用，務必注意變數的範圍和生命周期。
- **替代方案**：對於基本類型，可以考慮使用 nullable 變數或提供預設值來避免使用 `lateinit`。

## 一句總結
`lateinit` 讓 Kotlin 開發者能夠在需要時延遲初始化變數，提供了靈活性，但必須小心處理未初始化的情況。