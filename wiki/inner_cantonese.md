<!--
Meta Description: # Kotlin 中的 Inner 類別：深入了解內部類別的使用 ## 概要 Kotlin 的 `inner` 類別允許在外部類別中定義內部類別，並且可以直接訪問外部類別的成員。這種設計模式對於需要保持對外部類別狀態的引用時特別有用。 ## 文檔 `inner` 類別是 Kotlin 提供的一種功能...
Meta Keywords: inner, kotlin, outer, class, val
-->

# Kotlin 中的 Inner 類別：深入了解內部類別的使用

## 概要
Kotlin 的 `inner` 類別允許在外部類別中定義內部類別，並且可以直接訪問外部類別的成員。這種設計模式對於需要保持對外部類別狀態的引用時特別有用。

## 文檔
`inner` 類別是 Kotlin 提供的一種功能，能夠讓內部類別訪問其外部類別的屬性和方法。與 Java 的內部類別類似，Kotlin 的 `inner` 關鍵字標記內部類別，使其可以持有外部類別的引用。

### 用途
- **訪問外部類別成員**：內部類別能夠直接使用外部類別的屬性和方法，而不需要額外傳遞引用。
- **封裝**：`inner` 類別的使用可以幫助將邏輯封裝在一起，增強代碼的可讀性和維護性。

### 使用
要定義一個 `inner` 類別，只需在類別聲明前加上 `inner` 關鍵字。例如：

```kotlin
class OuterClass {
    private val outerProperty = "外部類別屬性"

    inner class InnerClass {
        fun innerFunction() {
            println("訪問外部類別屬性: $outerProperty")
        }
    }
}
```

## 範例
以下是使用 `inner` 類別的基本範例：

```kotlin
class Outer {
    val outerValue = "Hello from Outer"

    inner class Inner {
        fun display() {
            println(outerValue)  // 可以直接訪問外部類別的屬性
        }
    }
}

fun main() {
    val outer = Outer()
    val inner = outer.Inner() // 創建內部類別的實例
    inner.display()           // 輸出: Hello from Outer
}
```

## 解釋
在使用 `inner` 類別時，有幾個常見的陷阱和注意事項：

- **內部類別的實例需要外部類別的實例**：由於內部類別持有外部類別的引用，因此必須先創建外部類別的實例，才能創建內部類別的實例。
- **性能考量**：使用 `inner` 類別時，需考慮性能影響，因為內部類別的實例會持有對外部類別的引用，這可能導致更高的內存消耗。
- **可讀性**：過度使用內部類別可能會影響代碼的可讀性，尤其是在內部類別層次過於嵌套的情況下。

## 一句話概述
Kotlin 的 `inner` 類別允許內部類別訪問外部類別的成員，提供了一種強大的封裝和訪問方式。