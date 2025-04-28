<!--
Meta Description: # Kotlin 中的數據類（Data Class） ## 簡介 Kotlin 的數據類（Data Class）是一種特殊類型的類，用於簡化數據的存儲和處理。其主要目的是自動生成與數據相關的常用功能，如 `toString()`、`equals()`、`hashCode()` 和 `copy()` ...
Meta Keywords: val, kotlin, data, class, copy
-->

# Kotlin 中的數據類（Data Class）

## 簡介
Kotlin 的數據類（Data Class）是一種特殊類型的類，用於簡化數據的存儲和處理。其主要目的是自動生成與數據相關的常用功能，如 `toString()`、`equals()`、`hashCode()` 和 `copy()` 方法，從而提高開發效率。

## 文檔
數據類的主要用途是作為持有數據的容器。當你需要一組屬性來代表一個實體時，數據類提供了一個簡潔的解決方案。使用數據類，開發者無需手動編寫冗長的代碼來實現這些基本功能。

### 定義數據類
要定義一個數據類，只需在類前添加 `data` 關鍵字，並在主構造函數中定義屬性。以下是數據類的基本結構：

```kotlin
data class User(val name: String, val age: Int)
```

### 自動生成功能
Kotlin 為數據類自動生成以下功能：
- `toString()`：返回類的字符串表示形式。
- `equals()`：比較兩個對象的內容是否相等。
- `hashCode()`：生成對象的哈希碼，便於用於集合中。
- `copy()`：創建對象的副本，允許修改屬性。

## 範例
以下是數據類的基本使用示例：

```kotlin
data class Book(val title: String, val author: String)

fun main() {
    val book1 = Book("1984", "George Orwell")
    val book2 = book1.copy(author = "Orwell")
    
    println(book1) // 輸出: Book(title=1984, author=George Orwell)
    println(book1 == book2) // 輸出: false
}
```

## 解釋
使用數據類時，有一些常見的陷阱和注意事項：
1. **不可變性**：數據類的屬性預設是 `val`，這意味著一旦創建對象，其屬性值無法改變。如果需要可變性，必須使用 `var`，但這會影響 `copy()` 方法的使用。
2. **繼承限制**：數據類不能直接繼承其他數據類。如果需要建立層次結構，可以考慮使用普通類。
3. **多參數的情況**：如果數據類有多個屬性，會自動生成 `toString()` 方法，這會讓調試時更加方便，但也可能導致輸出過於冗長。

## 一句總結
Kotlin 的數據類是一種用於簡化數據封裝的設計模式，自動生成常用方法以提升開發效率。