<!--
Meta Description: # Kotlin 中的委託 (Delegate) ## 摘要 在 Kotlin 中，委託是一種強大的語言特性，允許對屬性進行委託，以簡化代碼並促進重用。這個特性使得對屬性讀取和寫入的行為可以被封裝到其他類中，從而提高了代碼的可維護性。 ## 文檔 ### 目的 Kotlin 的委託功能主要用於將屬性...
Meta Keywords: kotlin, name, string, value, example
-->

# Kotlin 中的委託 (Delegate)

## 摘要
在 Kotlin 中，委託是一種強大的語言特性，允許對屬性進行委託，以簡化代碼並促進重用。這個特性使得對屬性讀取和寫入的行為可以被封裝到其他類中，從而提高了代碼的可維護性。

## 文檔
### 目的
Kotlin 的委託功能主要用於將屬性的 getter 和 setter 的實現委託給另一個對象。這樣可以使代碼更加簡潔，並促進屬性的重用和擴展。

### 用法
在 Kotlin 中，委託屬性是通過關鍵字 `by` 來實現的。當你使用 `by` 關鍵字時，Kotlin 會自動將屬性的行為委託給指定的對象。

基本語法如下：
```kotlin
var propertyName: Type by DelegateType()
```

### 詳細說明
Kotlin 支援兩種主要的委託方式：
1. **標準委託屬性**：例如，lazy 委託和 observable 委託。
2. **自訂委託屬性**：用戶可以定義自己的委託類，並實現 `getValue` 和 `setValue` 方法。

#### 標準委託屬性示例
- **lazy 委託**：在第一次訪問時初始化屬性。
- **observable 委託**：在屬性變化時執行特定操作。

#### 自訂委託屬性
自訂委託需要實現 `ReadWriteProperty` 接口，並提供 `getValue` 和 `setValue` 方法。

## 示例
### 基本用法示例
```kotlin
class User {
    var name: String by Delegates.observable("初始值") { prop, old, new ->
        println("屬性 '${prop.name}' 改變: 從 '$old' 改為 '$new'")
    }
}

fun main() {
    val user = User()
    user.name = "新名字"  // 將打印屬性改變的訊息
}
```

### 自訂委託示例
```kotlin
import kotlin.properties.ReadWriteProperty
import kotlin.reflect.KProperty

class StringDelegate : ReadWriteProperty<Any?, String> {
    private var value: String = ""

    override fun getValue(thisRef: Any?, property: KProperty<*>): String {
        return value
    }

    override fun setValue(thisRef: Any?, property: KProperty<*>, value: String) {
        this.value = value.trim()  // 儲存時去除空白
    }
}

class Example {
    var name: String by StringDelegate()
}

fun main() {
    val example = Example()
    example.name = "  Hello World  "
    println(example.name)  // 輸出: "Hello World"
}
```

## 解釋
### 常見陷阱
- **未初始化的委託屬性**：在使用 lazy 委託時，如果在屬性初始化之前訪問，會導致異常。
- **多重委託**：對於不適當的多重委託，可能導致屬性行為不如預期，需謹慎處理。

### 附加說明
使用委託屬性可以使代碼更具可讀性和可維護性，但同時要注意不要過度使用，因為這可能使代碼變得難以理解。

## 單行摘要
Kotlin 的委託功能允許將屬性行為委託給其他對象，以簡化代碼和增強重用性。