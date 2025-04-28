<!--
Meta Description: # Kotlin의 "by" 키워드: 위임 및 프로퍼티 위임 ## 개요 Kotlin의 "by" 키워드는 위임(delegate) 패턴을 구현하는 데 사용되는 강력한 기능입니다. 이 키워드는 프로퍼티 위임, 인터페이스 구현 및 위임 클래스에 대한 간결하고 읽기 쉬운 문법을 ...
Meta Keywords: printer, 프로퍼티, val, fun, 인터페이스
-->

# Kotlin의 "by" 키워드: 위임 및 프로퍼티 위임

## 개요
Kotlin의 "by" 키워드는 위임(delegate) 패턴을 구현하는 데 사용되는 강력한 기능입니다. 이 키워드는 프로퍼티 위임, 인터페이스 구현 및 위임 클래스에 대한 간결하고 읽기 쉬운 문법을 제공하여 코드의 재사용성과 유지보수성을 높입니다.

## 문서화
Kotlin에서 "by"는 주로 두 가지 용도로 사용됩니다: 프로퍼티 위임과 인터페이스 위임입니다. 

### 프로퍼티 위임
프로퍼티 위임을 사용하면, 프로퍼티의 getter 및 setter를 별도의 객체에 위임할 수 있습니다. 이는 코드 중복을 줄이고, 여러 클래스에서 동일한 로직을 재사용할 수 있는 장점을 제공합니다.

예를 들어, `Lazy` 위임을 사용하여 프로퍼티의 초기화를 지연시킬 수 있습니다:
```kotlin
val lazyValue: String by lazy {
    println("Computed!")
    "Hello"
}
```
이 경우, `lazyValue`는 처음 접근할 때만 계산되며, 이후에는 캐시된 값을 반환합니다.

### 인터페이스 위임
인터페이스 위임은 클래스가 인터페이스의 메서드를 다른 객체에 위임할 수 있게 해줍니다. 다음은 인터페이스 위임의 예입니다:
```kotlin
interface Base {
    fun print()
}

class BaseImpl(val x: Int) : Base {
    override fun print() {
        println(x)
    }
}

class Derived(b: Base) : Base by b

fun main() {
    val b = BaseImpl(10)
    val d = Derived(b)
    d.print() // 10 출력
}
```
위의 예에서 `Derived` 클래스는 `Base` 인터페이스의 메서드를 `BaseImpl` 클래스에 위임합니다.

## 예제
1. **Lazy 프로퍼티 위임**
    ```kotlin
    val lazyString: String by lazy {
        println("Lazy initialization")
        "Hello, World!"
    }

    fun main() {
        println(lazyString) // "Lazy initialization"과 "Hello, World!" 출력
        println(lazyString) // "Hello, World!"만 출력
    }
    ```

2. **인터페이스 위임**
    ```kotlin
    interface Printer {
        fun print()
    }

    class SimplePrinter : Printer {
        override fun print() {
            println("Printing...")
        }
    }

    class DelegatedPrinter(printer: Printer) : Printer by printer

    fun main() {
        val printer = SimplePrinter()
        val delegatedPrinter = DelegatedPrinter(printer)
        delegatedPrinter.print() // "Printing..." 출력
    }
    ```

## 설명
"by" 키워드를 사용할 때 주의해야 할 점은 위임된 객체가 null일 수 있는 경우입니다. 이럴 경우, NullPointerException이 발생할 수 있으므로, 위임할 객체가 null이 아닌지 확인하는 로직을 추가해야 합니다. 또한, 위임된 프로퍼티의 상태를 변경할 수 없으므로, 프로퍼티의 값을 직접 설정하려고 하면 컴파일 오류가 발생합니다.

## 한 줄 요약
Kotlin의 "by" 키워드는 프로퍼티 및 인터페이스의 위임을 통해 코드의 재사용성과 가독성을 높여주는 유용한 기능입니다.