<!--
Meta Description: # Kotlin 中的內部類別（Inner Class）詳解 ## 簡介 在 Kotlin 中，內部類別（Inner Class）是一種特殊的類別，允許定義在其他類別的範疇內，並可以訪問外部類別的成員。 ## 文件說明 內部類別是一種具有強大功能的結構，能夠提高代碼的可讀性及組織性。與靜態類別不同，...
Meta Keywords: class, kotlin, inner, car, val
-->

# Kotlin 中的內部類別（Inner Class）詳解

## 簡介
在 Kotlin 中，內部類別（Inner Class）是一種特殊的類別，允許定義在其他類別的範疇內，並可以訪問外部類別的成員。

## 文件說明
內部類別是一種具有強大功能的結構，能夠提高代碼的可讀性及組織性。與靜態類別不同，內部類別持有對外部類別的引用，這使得它能夠直接訪問外部類別的屬性和方法。這個特性在需要將某些功能緊密結合在一起時特別有用。

### 用法
在 Kotlin 中，使用 `inner` 關鍵字來定義內部類別。下面是內部類別的基本語法：
```kotlin
class OuterClass {
    private val outerProperty = "Outer Property"

    inner class InnerClass {
        fun accessOuterProperty() = outerProperty
    }
}
```

### 詳細說明
- **訪問權限**：內部類別可以訪問外部類別的私有成員，這是其主要特點之一。
- **創建實例**：要創建內部類別的實例，必須首先創建外部類別的實例。
- **性能考量**：由於內部類別持有外部類別的引用，因此在某些情況下可能會導致額外的內存開銷。

## 範例
以下是使用內部類別的基本範例：

```kotlin
class Car(val model: String) {
    private val brand = "Toyota"

    inner class Engine {
        fun printDetails() {
            println("Car Model: $model, Brand: $brand")
        }
    }
}

fun main() {
    val car = Car("Corolla")
    val engine = car.Engine()
    engine.printDetails()  // 輸出: Car Model: Corolla, Brand: Toyota
}
```

## 解釋
在使用內部類別時，有幾個常見的注意事項：
- **內部類別的實例化**：內部類別的實例必須依賴於外部類別的實例，這意味著要在外部類別被實例化後才能使用內部類別。
- **潛在的內存洩漏**：如果內部類別的實例被長時間持有，可能會導致外部類別無法被回收，從而引發內存洩漏的問題。
- **設計考量**：內部類別的使用應該合理，過度使用可能會使代碼的結構變得複雜。

## 一句總結
Kotlin 中的內部類別（Inner Class）是一種能夠訪問外部類別成員的特殊類別結構，適合用於需要緊密結合的功能組織。