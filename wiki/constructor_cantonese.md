<!--
Meta Description: # Kotlin 中的建構子 (Constructor) ## 概述 建構子是 Kotlin 中的一個重要概念，用於初始化類別的實例。透過建構子，我們能夠設定類別屬性的初始值，並且執行必要的初始化邏輯。 ## 文檔 在 Kotlin 中，建構子分為兩種類型：主建構子（Primary Construc...
Meta Keywords: name, kotlin, person, age, constructor
-->

# Kotlin 中的建構子 (Constructor)

## 概述
建構子是 Kotlin 中的一個重要概念，用於初始化類別的實例。透過建構子，我們能夠設定類別屬性的初始值，並且執行必要的初始化邏輯。

## 文檔
在 Kotlin 中，建構子分為兩種類型：主建構子（Primary Constructor）和次建構子（Secondary Constructor）。

### 主建構子
主建構子是類別的一部分，定義在類別名稱之後。它可以包含參數，並且可以直接在類別的主體中用於初始化屬性。

```kotlin
class Person(val name: String, var age: Int) {
    init {
        println("Person created: Name = $name, Age = $age")
    }
}
```

### 次建構子
次建構子是用 `constructor` 關鍵字定義的，通常用於需要多個建構方式的情況。

```kotlin
class Person {
    var name: String
    var age: Int

    constructor(name: String, age: Int) {
        this.name = name
        this.age = age
    }

    constructor(name: String) : this(name, 0) {
        println("Person created: Name = $name, Age = 0")
    }
}
```

## 範例
以下是使用 Kotlin 建構子的基本範例：

### 主建構子範例
```kotlin
fun main() {
    val person1 = Person("Alice", 30)
    val person2 = Person("Bob", 25)
}
```

### 次建構子範例
```kotlin
fun main() {
    val person1 = Person("Charlie", 22)
    val person2 = Person("Daisy")
}
```

## 解釋
使用建構子時，開發者應注意以下幾點：

- **可見性修飾符**：建構子的可見性可以使用 `public`、`private` 或 `protected` 修飾符來控制。
- **初始化邏輯**：在主建構子中，初始化區塊 `init` 可以用來執行其他邏輯，比如檢查參數的有效性。
- **多重建構子**：可以在類別中定義多個次建構子，但每個次建構子必須呼叫主建構子或者其他次建構子。

## 一句總結
Kotlin 的建構子使得類別實例化過程中能夠靈活地初始化屬性和執行邏輯。