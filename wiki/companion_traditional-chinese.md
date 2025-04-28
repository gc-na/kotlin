<!--
Meta Description: # Kotlin Companion 伴隨物件：深入了解 Kotlin 的伴隨物件特性 ## 概述 Kotlin 的伴隨物件（companion object）是一種特殊的物件，可以作為類別的靜態成員存在。透過伴隨物件，開發者能夠在類別內部定義靜態方法和屬性，使其可以方便地被訪問，而不需要建立類別的...
Meta Keywords: kotlin, fun, user, companion, object
-->

# Kotlin Companion 伴隨物件：深入了解 Kotlin 的伴隨物件特性

## 概述
Kotlin 的伴隨物件（companion object）是一種特殊的物件，可以作為類別的靜態成員存在。透過伴隨物件，開發者能夠在類別內部定義靜態方法和屬性，使其可以方便地被訪問，而不需要建立類別的實例。

## 文檔
伴隨物件是 Kotlin 中一種特殊的物件，與類別關聯並且在類別被加載時就會被初始化。伴隨物件的主要用途包括：

- **靜態成員**：提供類似 Java 中靜態方法和屬性的功能。
- **工廠方法**：可以在伴隨物件內部定義工廠方法，用於創建類別的實例。
- **名稱空間**：避免全域函數的名稱衝突，因為伴隨物件的成員可以通過類別名稱來訪問。

### 使用方式
伴隨物件的定義方式如下：

```kotlin
class MyClass {
    companion object {
        // 靜態屬性
        const val STATIC_PROPERTY = "這是靜態屬性"

        // 靜態方法
        fun staticMethod() {
            println("這是靜態方法")
        }
    }
}
```

要訪問伴隨物件中的成員，可以使用類別名稱：

```kotlin
fun main() {
    println(MyClass.STATIC_PROPERTY) // 輸出：這是靜態屬性
    MyClass.staticMethod() // 輸出：這是靜態方法
}
```

## 範例
以下是幾個使用伴隨物件的基本範例：

1. **伴隨物件的基本使用**：
    ```kotlin
    class Calculator {
        companion object {
            fun add(a: Int, b: Int): Int {
                return a + b
            }
        }
    }

    fun main() {
        val result = Calculator.add(5, 3)
        println(result) // 輸出：8
    }
    ```

2. **伴隨物件與工廠方法**：
    ```kotlin
    class User private constructor(val name: String) {
        companion object {
            fun create(name: String): User {
                return User(name)
            }
        }
    }

    fun main() {
        val user = User.create("Alice")
        println(user.name) // 輸出：Alice
    }
    ```

## 解釋
在使用伴隨物件時，有幾個常見的注意事項：

- **伴隨物件無法繼承**：伴隨物件不能被繼承，這意味著如果你有一個伴隨物件，則它無法作為父類的伴隨物件。
- **多個伴隨物件**：一個類別只能有一個伴隨物件，這一點與 Java 的靜態成員有所不同。
- **可見性修飾符**：伴隨物件內的成員可以使用不同的可見性修飾符（如 `public`、`private`）來控制訪問權限。

## 一句話總結
Kotlin 的伴隨物件提供了一種靜態成員的實現方式，使得在類別內部定義靜態方法和屬性變得簡單而有效。