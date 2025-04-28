<!--
Meta Description: # Kotlin 中的 Enum：完整指南與使用範例 ## 摘要 在 Kotlin 中，`enum` 是用來定義一組具名常數的特殊類型，能夠提高程式碼的可讀性和可維護性。 ## 文檔 `enum` 類型（枚舉類型）允許開發者創建一組固定的常數，這些常數通常代表了一個特定的類型或狀態。例如，星期幾、顏...
Meta Keywords: enum, direction, kotlin, color, println
-->

# Kotlin 中的 Enum：完整指南與使用範例

## 摘要
在 Kotlin 中，`enum` 是用來定義一組具名常數的特殊類型，能夠提高程式碼的可讀性和可維護性。

## 文檔
`enum` 類型（枚舉類型）允許開發者創建一組固定的常數，這些常數通常代表了一個特定的類型或狀態。例如，星期幾、顏色、方向等都是可以使用 `enum` 來表示的概念。

### 目的
使用 `enum` 主要是為了提供一個清晰的命名方式來表示具有限定值的類型。這樣的結構不僅提高了代碼的可讀性，還能夠減少錯誤的發生。

### 使用方式
在 Kotlin 中，定義 `enum` 類型的語法如下：

```kotlin
enum class Color {
    RED, GREEN, BLUE
}
```

這裡，`Color` 是一個枚舉類型，包含了三個值：`RED`、`GREEN` 和 `BLUE`。

你可以像使用普通類型一樣使用 `enum`：

```kotlin
fun printColor(color: Color) {
    when (color) {
        Color.RED -> println("紅色")
        Color.GREEN -> println("綠色")
        Color.BLUE -> println("藍色")
    }
}
```

## 範例
以下是使用 `enum` 的一些基本範例：

### 範例 1：定義和使用枚舉
```kotlin
enum class Direction {
    NORTH, SOUTH, EAST, WEST
}

fun describeDirection(direction: Direction) {
    when (direction) {
        Direction.NORTH -> println("北方")
        Direction.SOUTH -> println("南方")
        Direction.EAST -> println("東方")
        Direction.WEST -> println("西方")
    }
}

fun main() {
    describeDirection(Direction.NORTH)
}
```

### 範例 2：帶屬性的枚舉
```kotlin
enum class Weekday(val dayNumber: Int) {
    MONDAY(1),
    TUESDAY(2),
    WEDNESDAY(3),
    THURSDAY(4),
    FRIDAY(5),
    SATURDAY(6),
    SUNDAY(7)
}

fun main() {
    println("星期一是第 ${Weekday.MONDAY.dayNumber} 天")
}
```

## 解釋
使用 `enum` 類型時，有一些常見的注意事項：

- `enum` 類型的值是不可變的，這意味著你不能在運行時創建新的枚舉常數。
- `enum` 類型可以有屬性和方法，這使得它們更加靈活和強大。
- 在 `when` 表達式中，使用 `enum` 類型時不需要使用 `else` 分支，因為所有可能的值都是已知的。

## 一行總結
Kotlin 中的 `enum` 允許開發者定義一組具名常數，從而提高程式碼的可讀性和可維護性。