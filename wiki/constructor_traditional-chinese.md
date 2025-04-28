<!--
Meta Description: # Kotlin 建構子（Constructor）：深入了解 Kotlin 中的物件初始化 ## 概述 在 Kotlin 中，建構子是用來初始化物件的特殊函數。它們可以讓開發者在創建類的實例時傳遞參數，並確保物件的屬性在使用之前獲得正確的值。 ## 文檔 建構子分為兩種類型：主建構子（Primary...
Meta Keywords: name, age, kotlin, person, constructor
-->

# Kotlin 建構子（Constructor）：深入了解 Kotlin 中的物件初始化

## 概述
在 Kotlin 中，建構子是用來初始化物件的特殊函數。它們可以讓開發者在創建類的實例時傳遞參數，並確保物件的屬性在使用之前獲得正確的值。

## 文檔
建構子分為兩種類型：主建構子（Primary Constructor）和次建構子（Secondary Constructor）。

### 主建構子
主建構子是類定義的一部分，通常在類名後面括號內定義。它可以有多個參數，並且可以直接初始化屬性。

```kotlin
class Person(val name: String, var age: Int) {
    init {
        println("Person initialized with name: $name and age: $age")
    }
}
```

在上面的範例中，`name` 和 `age` 是主建構子的參數，`init` 區塊用來進行額外的初始化。

### 次建構子
次建構子是使用 `constructor` 關鍵字定義的，並且可以用來提供不同的初始化邏輯或參數。

```kotlin
class Person {
    val name: String
    var age: Int

    constructor(name: String, age: Int) {
        this.name = name
        this.age = age
        println("Person initialized with name: $name and age: $age")
    }

    constructor(name: String) : this(name, 0) {
        println("Person initialized with name: $name and default age: 0")
    }
}
```

在這個例子中，第二個次建構子使用了主建構子的委託來設置預設年齡為0。

## 範例
以下是一些基本的使用範例：

### 使用主建構子
```kotlin
fun main() {
    val person1 = Person("Alice", 30)
}
```

### 使用次建構子
```kotlin
fun main() {
    val person2 = Person("Bob")
}
```

## 解釋
使用建構子時，有一些常見的陷阱需要注意：

1. **不可變性**：在主建構子中使用 `val` 來定義屬性，這樣可以保證屬性在初始化後不會被改變。
2. **初始化順序**：在次建構子的實現中，必須先調用主建構子，否則會導致編譯錯誤。
3. **多重建構子**：雖然可以有多個次建構子，但應保持清晰以避免混淆。

在設計類時，合理選擇主建構子和次建構子，可以提高程式碼的可讀性和可維護性。

## 一句總結
建構子在 Kotlin 中是用來初始化物件的特殊函數，分為主建構子和次建構子，提供靈活的物件創建方式。