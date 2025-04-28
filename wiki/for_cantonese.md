<!--
Meta Description: # Kotlin 中的 for 循環：完整指南 ## 概要 Kotlin 中的 `for` 循環是一種控制結構，用於遍歷數據結構（如數組、集合或範圍）。它提供了一種簡潔且高效的方式來執行重複任務。 ## 文件說明 `for` 循環在 Kotlin 中的主要目的是簡化重複操作的編寫，使代碼更具可讀性和...
Meta Keywords: kotlin, println, val, array, element
-->

# Kotlin 中的 for 循環：完整指南

## 概要
Kotlin 中的 `for` 循環是一種控制結構，用於遍歷數據結構（如數組、集合或範圍）。它提供了一種簡潔且高效的方式來執行重複任務。

## 文件說明
`for` 循環在 Kotlin 中的主要目的是簡化重複操作的編寫，使代碼更具可讀性和可維護性。它可以用來遍歷各種集合類型，包括列表、數組和範圍，並且支持多種語法形式，以適應不同的使用場景。

### 語法
基本的 `for` 循環語法如下：

```kotlin
for (item in collection) {
    // 執行操作
}
```

### 用法
1. **遍歷範圍**：
   ```kotlin
   for (i in 1..5) {
       println(i)
   }
   ```

2. **遍歷數組**：
   ```kotlin
   val array = arrayOf(1, 2, 3, 4, 5)
   for (element in array) {
       println(element)
   }
   ```

3. **遍歷集合**：
   ```kotlin
   val list = listOf("apple", "banana", "cherry")
   for (fruit in list) {
       println(fruit)
   }
   ```

## 示例
### 示例 1：範圍內的數字
```kotlin
for (i in 1..3) {
    println("Number: $i")
}
```

### 示例 2：反向範圍
```kotlin
for (i in 3 downTo 1) {
    println("Countdown: $i")
}
```

### 示例 3：步進遍歷
```kotlin
for (i in 1..10 step 2) {
    println("Odd number: $i")
}
```

## 解釋
在使用 `for` 循環時，有幾個常見的陷阱和注意事項：
- **範圍運算符**：使用 `..` 運算符創建的範圍是包含結束值的。如果不希望包含，可以使用 `until`，例如 `1 until 5` 只會遍歷到 4。
- **集合的變化**：在遍歷集合時，如果在循環內部對集合進行修改，會導致異常或不正確的結果。
- **自定義對象**：如果要遍歷自定義對象，需要實現 `Iterable` 接口或提供相應的迭代器。

## 一行總結
Kotlin 的 `for` 循環提供了一種靈活且高效的方法來遍歷數據結構，簡化了重複任務的代碼。