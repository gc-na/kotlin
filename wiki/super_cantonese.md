<!--
Meta Description: # Kotlin 中的 "super" 關鍵字：用法與示例 ## 概述 在 Kotlin 中，`super` 關鍵字用於訪問父類別的屬性和方法。這對於在類別繼承結構中，當子類別需要調用父類別的實現時特別重要。 ## 文件說明 `super` 是一個關鍵字，主要用於從子類別調用父類別的成員。這在多層繼...
Meta Keywords: super, kotlin, display, child, parent
-->

# Kotlin 中的 "super" 關鍵字：用法與示例

## 概述
在 Kotlin 中，`super` 關鍵字用於訪問父類別的屬性和方法。這對於在類別繼承結構中，當子類別需要調用父類別的實現時特別重要。

## 文件說明
`super` 是一個關鍵字，主要用於從子類別調用父類別的成員。這在多層繼承或重寫方法的情況下尤為重要。當你需要在覆寫一個方法時，使用 `super` 可以讓你保留父類別的行為，然後在此基礎上添加或修改功能。

### 用法
在 Kotlin 中，使用 `super` 來調用父類別的方法或屬性，語法如下：

```kotlin
super.methodName()
super.propertyName
```

### 詳細說明
1. **調用父類別方法**：當子類別重寫了父類別的方法時，可以使用 `super` 調用父類別的原始方法，以維持原有的邏輯。
2. **屬性訪問**：`super` 也可以用來訪問父類別的屬性，這在重寫屬性時特別有用。
3. **多重繼承**：在 Kotlin 中，類別不支持多重繼承，但可以通過實現多個接口來達到類似的效果。這時，`super` 可以用來區分不同接口的實現。

## 示例
以下是使用 `super` 的基本範例：

```kotlin
open class Parent {
    open fun display() {
        println("父類別的方法")
    }
}

class Child : Parent() {
    override fun display() {
        super.display() // 調用父類別的方法
        println("子類別的方法")
    }
}

fun main() {
    val child = Child()
    child.display()
}
```

輸出：
```
父類別的方法
子類別的方法
```

在這個例子中，`Child` 類別覆寫了 `Parent` 類別的 `display` 方法，並使用 `super.display()` 調用父類別的方法。

## 解釋
- **常見陷阱**：在使用 `super` 時，必須確保父類別中存在你要調用的屬性或方法，否則會導致編譯錯誤。
- **多層繼承**：在有多層繼承的情況下，`super` 會按照繼承鏈向上查找，因此需要注意調用的正確性。
- **覆寫限制**：如果父類別的成員方法被標記為 `final`，則不能被子類別覆寫，這意味著不能使用 `super` 調用該方法。

## 一句總結
在 Kotlin 中，`super` 關鍵字用於訪問父類別的屬性和方法，是實現繼承和方法重寫的重要工具。