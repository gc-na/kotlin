<!--
Meta Description: # Kotlin 中的 "open" 關鍵字：擴展與繼承的基本概念 ## 摘要 在 Kotlin 中，"open" 關鍵字用於標記類別和方法，以允許其他類別繼承和覆寫。這一特性使得 Kotlin 在繼承和多型的使用上更加靈活。 ## 文檔 ### 目的 Kotlin 預設所有類別和方法為 "fina...
Meta Keywords: open, kotlin, class, fun, println
-->

# Kotlin 中的 "open" 關鍵字：擴展與繼承的基本概念

## 摘要
在 Kotlin 中，"open" 關鍵字用於標記類別和方法，以允許其他類別繼承和覆寫。這一特性使得 Kotlin 在繼承和多型的使用上更加靈活。

## 文檔
### 目的
Kotlin 預設所有類別和方法為 "final"，這意味著它們不能被繼承或覆寫。使用 "open" 關鍵字可以明確指定某個類別或方法是可被繼承的，從而支持更靈活的物件導向程式設計。

### 使用方式
要使用 "open" 關鍵字，只需在類別或方法的定義前加上 "open"。例如：

```kotlin
open class Parent {
    open fun show() {
        println("Parent class show method")
    }
}
```

在這個例子中，`Parent` 類別和 `show` 方法都被標記為 "open"，這允許其他類別繼承並覆寫它們。

### 詳情
- **類別的開放性**: 當你將類別標記為 "open" 時，這表示該類別可以被其他類別繼承。例如：
  ```kotlin
  class Child : Parent() {
      override fun show() {
          println("Child class show method")
      }
  }
  ```

- **方法的開放性**: 只有當方法被標記為 "open" 時，才能在子類別中覆寫。未標記為 "open" 的方法將無法被覆寫。

- **屬性**: Kotlin 也允許使用 "open" 標記屬性，以便在子類別中覆寫。

## 示例
1. **開放類別示例**
   ```kotlin
   open class Animal {
       open fun sound() {
           println("Animal sound")
       }
   }

   class Dog : Animal() {
       override fun sound() {
           println("Bark")
       }
   }
   ```

2. **開放方法示例**
   ```kotlin
   open class Vehicle {
       open fun start() {
           println("Vehicle starting")
       }
   }

   class Car : Vehicle() {
       override fun start() {
           println("Car starting")
       }
   }
   ```

## 解釋
### 常見陷阱
- **未使用 open 的類別和方法**: 如果你忘記使用 "open" 標記，將會導致子類無法繼承或覆寫，這可能會導致設計的不一致。
  
- **無法覆寫的情況**: 如果你試圖在沒有標記為 "open" 的類別或方法上進行覆寫，編譯器會報錯。

- **嚴謹性**: 在設計類別結構時，必須清楚哪些類別和方法需要被擴展，這樣可以避免不必要的開放性，保持設計的嚴謹性。

## 一句話總結
Kotlin 的 "open" 關鍵字允許類別和方法被繼承和覆寫，是物件導向設計中靈活性的關鍵。