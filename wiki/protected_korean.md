<!--
Meta Description: # Kotlin에서의 "protected" 접근 제어자 ## 개요 Kotlin에서 "protected"는 클래스와 그 하위 클래스에서만 접근할 수 있는 속성이나 메서드를 정의하는 접근 제어자입니다. 이는 객체지향 프로그래밍에서 캡슐화를 강화하고, 클래스의 내부 구현을 ...
Meta Keywords: protected, 접근할, 클래스, fun, 클래스에서만
-->

# Kotlin에서의 "protected" 접근 제어자

## 개요
Kotlin에서 "protected"는 클래스와 그 하위 클래스에서만 접근할 수 있는 속성이나 메서드를 정의하는 접근 제어자입니다. 이는 객체지향 프로그래밍에서 캡슐화를 강화하고, 클래스의 내부 구현을 외부에 노출하지 않도록 도와줍니다.

## 문서화
"protected" 접근 제어자는 클래스의 속성이나 메서드를 외부에서 직접 접근할 수 없게 제한하지만, 그 클래스를 상속받는 하위 클래스에서는 접근할 수 있도록 허용합니다. 이는 클래스 간의 관계를 명확하게 하고, 유지보수성을 높이는 데 기여합니다.

### 목적
- **캡슐화**: 클래스 내부의 데이터를 보호하여 외부 클래스가 직접 접근하지 못하도록 합니다.
- **재사용성**: 하위 클래스에서 상위 클래스의 기능을 재사용할 수 있게 합니다.

### 사용법
"protected"는 클래스 내에서 속성이나 메서드를 정의할 때 사용됩니다. 예를 들어:

```kotlin
open class Parent {
    protected val protectedProperty: String = "Protected Property"
    
    protected fun protectedMethod() {
        println("This is a protected method.")
    }
}

class Child : Parent() {
    fun display() {
        println(protectedProperty) // 접근 가능
        protectedMethod()           // 접근 가능
    }
}
```

## 예시
다음은 "protected" 접근 제어자를 사용한 간단한 예제입니다.

```kotlin
open class Animal {
    protected val species: String = "Unknown"
    
    protected fun makeSound() {
        println("Animal sound")
    }
}

class Dog : Animal() {
    fun bark() {
        println("Bark! Species: $species") // protected 속성 접근
        makeSound()                         // protected 메서드 접근
    }
}

fun main() {
    val dog = Dog()
    dog.bark() // 출력: Bark! Species: Unknown
}
```

## 설명
"protected" 접근 제어자를 사용할 때는 다음과 같은 몇 가지 주의사항이 있습니다.

- **하위 클래스에서만 접근 가능**: "protected"로 지정된 속성이나 메서드는 해당 클래스를 상속받은 하위 클래스에서만 접근할 수 있습니다. 다른 클래스에서는 접근할 수 없습니다.
- **인터페이스에서는 사용 불가**: "protected"는 클래스 내부에서만 의미가 있으며, 인터페이스에서는 사용될 수 없습니다. 인터페이스의 모든 멤버는 기본적으로 공개(public)입니다.
- **혼동 주의**: "protected"는 클래스 내에서만 접근 가능하므로, 다른 패키지의 클래스에서는 접근할 수 없습니다. 이는 "public"과의 혼동을 피하는 것이 중요합니다.

## 한 줄 요약
Kotlin의 "protected" 접근 제어자는 클래스와 하위 클래스에서만 접근 가능한 멤버를 정의하여 캡슐화를 강화하는 역할을 합니다.