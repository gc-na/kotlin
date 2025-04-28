<!--
Meta Description: # Kotlin 中的類別 (Class) 使用指南 ## 概述 在 Kotlin 中，類別（Class）是物件導向程式設計的核心組件之一。類別用於定義物件的結構、行為和屬性，是創建可重用代碼的基石。 ## 文檔 ### 目的 類別用來封裝數據和行為，方便管理和維護代碼。透過類別，我們可以創建物件，...
Meta Keywords: kotlin, class, val, user, string
-->

# Kotlin 中的類別 (Class) 使用指南

## 概述
在 Kotlin 中，類別（Class）是物件導向程式設計的核心組件之一。類別用於定義物件的結構、行為和屬性，是創建可重用代碼的基石。

## 文檔
### 目的
類別用來封裝數據和行為，方便管理和維護代碼。透過類別，我們可以創建物件，這些物件包含屬性（變數）和方法（函數）。

### 使用方式
在 Kotlin 中，使用 `class` 關鍵字來定義一個類別。類別可以包含屬性、方法、建構子和其他成員。

```kotlin
class Person(val name: String, var age: Int) {
    fun introduce() {
        println("你好，我叫 $name，今年 $age 歲。")
    }
}
```

在這個例子中，我們定義了一個名為 `Person` 的類別，擁有 `name` 和 `age` 屬性，以及一個 `introduce` 方法。

### 詳細說明
Kotlin 類別支援繼承、封裝和多型等物件導向特性。類別內的屬性可以是只讀（用 `val` 定義）或可變（用 `var` 定義）。建構子可用來初始化屬性，並可定義默認值。Kotlin 還提供資料類（data class），專門用於簡化數據持有類別的創建。

## 範例
以下是一些基本的類別使用範例：

### 定義類別
```kotlin
class Animal(val type: String) {
    fun sound() {
        println("$type 發出聲音！")
    }
}
```

### 創建物件
```kotlin
val dog = Animal("狗")
dog.sound()  // 輸出：狗 發出聲音！
```

### 資料類範例
```kotlin
data class User(val username: String, val email: String)

val user = User("alice", "alice@example.com")
println(user)  // 輸出：User(username=alice, email=alice@example.com)
```

## 解釋
在使用類別時，需要注意以下幾點：
1. **繼承**：Kotlin 中的類別預設是 `final`，這意味著不能被繼承。若要允許繼承，需使用 `open` 關鍵字。
2. **初始化**：所有屬性必須在建構子中初始化，否則會導致編譯錯誤。
3. **資料類**：資料類自動生成 `toString()`、`equals()` 和 `hashCode()` 方法，適合用於持有數據的場景。

## 總結
Kotlin 的類別是物件導向編程的基礎，提供了結構化和模組化代碼的能力，是開發高效、可維護應用程序的關鍵工具。