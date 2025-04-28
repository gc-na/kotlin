<!--
Meta Description: # Kotlin 的類別 (Class) 教學指南 ## 簡介 在 Kotlin 中，類別（Class）是對象導向編程的核心構建塊。它定義了對象的屬性和行為，並允許開發者建立結構化和可重用的代碼。 ## 文檔 類別是 Kotlin 中一種重要的數據類型，用於創建對象。每個類別都可以包含屬性（變數）和...
Meta Keywords: kotlin, class, person, name, fun
-->

# Kotlin 的類別 (Class) 教學指南

## 簡介
在 Kotlin 中，類別（Class）是對象導向編程的核心構建塊。它定義了對象的屬性和行為，並允許開發者建立結構化和可重用的代碼。

## 文檔
類別是 Kotlin 中一種重要的數據類型，用於創建對象。每個類別都可以包含屬性（變數）和方法（函數），並且可以透過繼承來擴展功能。Kotlin 支援封裝、繼承和多型等對象導向特性。

### 使用方法
可以使用 `class` 關鍵字來定義一個類別。以下是一個基本的類別定義範本：

```kotlin
class ClassName {
    // 屬性
    var propertyName: Type = initialValue

    // 方法
    fun methodName() {
        // 方法體
    }
}
```

### 詳細說明
- **屬性**：類別中的變數，定義對象的狀態。
- **方法**：類別中的函數，定義對象的行為。
- **主建構函數**：在類別名後面定義的參數，可以用來初始化屬性。
- **次建構函數**：使用 `constructor` 關鍵字定義，提供多種初始化方式。

## 範例
以下是一個簡單的 Kotlin 類別範例，展示了屬性和方法的使用：

```kotlin
class Person(val name: String, var age: Int) {
    fun greet() {
        println("Hello, my name is $name and I am $age years old.")
    }
}

fun main() {
    val person = Person("Alice", 30)
    person.greet()  // 輸出: Hello, my name is Alice and I am 30 years old.
}
```

## 說明
- **常見陷阱**：在 Kotlin 中，類別的屬性如果不初始化，會需要使用 `lateinit` 或者提供預設值。
- **繼承**：Kotlin 中的類別預設是 `final`，如果需要讓其他類別繼承，必須使用 `open` 關鍵字。
- **資料類別**：如果一個類別主要用來儲存數據，可以考慮使用資料類別（data class），它會自動生成 `equals()`、`hashCode()` 和 `toString()` 方法。

## 一句總結
Kotlin 的類別是建立對象的藍圖，透過屬性和方法來定義對象的狀態和行為。