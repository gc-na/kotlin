<!--
Meta Description: # Kotlin中的「for」迴圈：使用與範例 ## 簡介 在Kotlin中，「for」迴圈是一個用於遍歷集合、數組或任何可迭代對象的控制結構。它提供了一種簡潔而高效的方式來處理循環操作，提高程式碼的可讀性與維護性。 ## 文件說明 「for」迴圈的主要目的是重複執行一段程式碼，直到滿足特定的條件。...
Meta Keywords: kotlin, println, kotlin的, item, collection
-->

# Kotlin中的「for」迴圈：使用與範例

## 簡介
在Kotlin中，「for」迴圈是一個用於遍歷集合、數組或任何可迭代對象的控制結構。它提供了一種簡潔而高效的方式來處理循環操作，提高程式碼的可讀性與維護性。

## 文件說明
「for」迴圈的主要目的是重複執行一段程式碼，直到滿足特定的條件。Kotlin的「for」迴圈可以與各種集合類型（如列表、數組和範圍）搭配使用。這使得開發者能夠輕鬆地遍歷數據集，進行操作和計算。

### 使用方式
基本語法如下：
```kotlin
for (item in collection) {
    // 執行的程式碼
}
```
在這裡，`item`是集合中的每一個元素，而`collection`是要被遍歷的集合或範圍。

#### 遍歷範圍
Kotlin還支持使用範圍來遍歷整數：
```kotlin
for (i in 1..5) {
    println(i)
}
```
這將輸出1到5之間的所有整數。

### 其他用法
- **步進**：可以指定步長，如每次增加2：
  ```kotlin
  for (i in 1..10 step 2) {
      println(i)
  }
  ```
- **反向遍歷**：可以使用`downTo`來倒序遍歷：
  ```kotlin
  for (i in 5 downTo 1) {
      println(i)
  }
  ```

## 範例
以下是一些「for」迴圈的基本用法範例：

1. 遍歷列表：
   ```kotlin
   val fruits = listOf("Apple", "Banana", "Cherry")
   for (fruit in fruits) {
       println(fruit)
   }
   ```

2. 遍歷數組：
   ```kotlin
   val numbers = arrayOf(1, 2, 3, 4, 5)
   for (number in numbers) {
       println(number)
   }
   ```

3. 使用範圍：
   ```kotlin
   for (i in 1..3) {
       println("Iteration $i")
   }
   ```

## 解釋
在使用「for」迴圈時，開發者應注意以下幾點：

- **空集合**：如果遍歷的集合是空的，則「for」迴圈內的程式碼將不會執行。
- **不可變性**：Kotlin的「for」迴圈不允許在迴圈內部修改迴圈遍歷的集合，這可能會導致不可預期的行為。
- **範圍邊界**：使用範圍時，注意範圍的上限與下限，避免超出邊界導致的錯誤。

## 一句總結
Kotlin的「for」迴圈是一個強大且靈活的工具，能夠高效地遍歷集合和範圍，簡化程式碼的撰寫。