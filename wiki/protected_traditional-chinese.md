<!--
Meta Description: # Kotlin 中的 "protected" 關鍵字 ## 摘要 在 Kotlin 中，`protected` 關鍵字用於控制類別成員的可見性，允許其在繼承階層中被訪問，卻不允許在類別外部直接訪問。 ## 文件說明 `protected` 修飾符用於類別的成員（屬性或方法），其主要目的是限制其可見...
Meta Keywords: protected, kotlin, fun, private, class
-->

# Kotlin 中的 "protected" 關鍵字

## 摘要
在 Kotlin 中，`protected` 關鍵字用於控制類別成員的可見性，允許其在繼承階層中被訪問，卻不允許在類別外部直接訪問。

## 文件說明
`protected` 修飾符用於類別的成員（屬性或方法），其主要目的是限制其可見性。與 `private` 不同，`protected` 允許子類別訪問父類別中的成員，但不允許在類別的外部直接存取。

### 用途
- **繼承的可見性控制**：`protected` 成員可以被任何繼承自該類別的子類別訪問，這對於實現封裝和繼承非常有用。
- **避免外部訪問**：保護類別成員不被外部呼叫，強化了類別的封裝性。

### 使用方式
在定義類別時，可以使用 `protected` 修飾符來標記屬性或方法。這樣，只有該類別及其子類別能夠訪問這些成員。

```kotlin
open class Parent {
    protected val protectedProperty: String = "這是保護屬性"

    protected fun protectedMethod() {
        println("這是保護方法")
    }
}

class Child : Parent() {
    fun accessProtectedMembers() {
        println(protectedProperty) // 可以訪問保護屬性
        protectedMethod() // 可以呼叫保護方法
    }
}
```

## 示例
以下是 `protected` 修飾符的基本用法範例：

```kotlin
open class Animal {
    protected fun sound() {
        println("動物的聲音")
    }
}

class Dog : Animal() {
    fun bark() {
        sound() // 可以訪問父類別中的 protected 方法
        println("汪汪")
    }
}

fun main() {
    val dog = Dog()
    dog.bark() // 輸出: 動物的聲音
               //      汪汪
}
```

## 解釋
### 常見的陷阱與注意事項
- **外部訪問問題**：雖然 `protected` 允許子類別訪問父類別的成員，但不能從父類別外部訪問這些 `protected` 成員，這可能會引起誤解。
- **無法在同一包中訪問**：即使在同一個包中，`protected` 成員也無法被其他非子類別訪問。
- **與 `private` 的區別**：`protected` 與 `private` 的主要區別在於，`protected` 允許在子類別中訪問，而 `private` 則完全限制在定義該屬性或方法的類別內部。

## 單行摘要
Kotlin 中的 `protected` 修飾符用於限制類別成員的可見性，使其僅在繼承階層中可訪問。