<!--
Meta Description: # Kotlin 中的「external」關鍵字：用於外部聲明的完整指南 ## 概述 Kotlin 的「external」關鍵字用於聲明外部函數或屬性，這些函數或屬性是在其他語言（如 C 或 C++）中實現的。這使得 Kotlin 可以與這些外部庫進行互動，提供了與底層系統或現有本地代碼的無縫整合。...
Meta Keywords: kotlin, external, fun, val, int
-->

# Kotlin 中的「external」關鍵字：用於外部聲明的完整指南

## 概述
Kotlin 的「external」關鍵字用於聲明外部函數或屬性，這些函數或屬性是在其他語言（如 C 或 C++）中實現的。這使得 Kotlin 可以與這些外部庫進行互動，提供了與底層系統或現有本地代碼的無縫整合。

## 文檔
### 目的
「external」關鍵字的主要目的是讓 Kotlin 開發者能夠調用用其他語言編寫的函數或使用其他語言中定義的變量。這對於需要利用現有 C/C++ 代碼的場景特別有用，尤其是在需要高性能計算或訪問特定硬體功能時。

### 使用
在 Kotlin 中，使用「external」關鍵字來聲明一個外部函數或屬性，語法如下：

```kotlin
external fun functionName(param: Type): ReturnType
external val propertyName: Type
```

這些函數或屬性的實現將在其他語言中提供，Kotlin 只需要知道它們的簽名。

### 詳細信息
- **連結外部函數**: 在 Kotlin 中，當你聲明一個外部函數時，必須確保該函數在相應的本地庫中已經實現。
- **JNI 支持**: Kotlin 支持 Java Native Interface (JNI)，這使得與 C/C++ 代碼的互操作變得更加方便。
- **編譯器選項**: 當使用外部函數時，需確保在編譯時提供正確的本地庫路徑。

## 例子
### 基本使用範例
以下是如何使用「external」關鍵字來聲明和調用外部函數的示例：

```kotlin
// 在 Kotlin 中聲明外部函數
external fun add(a: Int, b: Int): Int

fun main() {
    // 調用外部函數
    val result = add(5, 10)
    println("Result of addition: $result")
}
```

### 聲明外部屬性
```kotlin
external val nativeString: String

fun main() {
    println("Native String: $nativeString")
}
```

## 解釋
### 常見陷阱
- **實現不存在**: 如果外部函數在本地庫中未找到，將會在運行時出現錯誤。
- **類型不匹配**: 確保 Kotlin 中的類型與外部函數中定義的類型完全一致，否則將導致運行時錯誤。
- **性能考量**: 調用外部函數可能會有額外的性能開銷，尤其是在頻繁調用的情況下。

### 附加注意事項
- 在多平台開發時，確保外部函數的可用性和兼容性。
- 使用「external」關鍵字時，建議撰寫清晰的文檔和註釋，以便將來的維護。

## 一句總結
Kotlin 的「external」關鍵字允許開發者聲明和使用外部定義的函數和屬性，從而實現與其他語言的高效互操作性。