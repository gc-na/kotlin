<!--
Meta Description: # Kotlin의 "super" 키워드: 상속과 다형성을 통한 클래스 확장 ## 개요 Kotlin에서 "super" 키워드는 클래스 상속 구조에서 부모 클래스의 속성이나 메서드에 접근할 때 사용됩니다. 이를 통해 자식 클래스는 부모 클래스의 기능을 재사용하고 확장할 수...
Meta Keywords: super, 클래스의, sound, greet, 메서드를
-->

# Kotlin의 "super" 키워드: 상속과 다형성을 통한 클래스 확장

## 개요
Kotlin에서 "super" 키워드는 클래스 상속 구조에서 부모 클래스의 속성이나 메서드에 접근할 때 사용됩니다. 이를 통해 자식 클래스는 부모 클래스의 기능을 재사용하고 확장할 수 있습니다.

## 문서화
### 목적
Kotlin의 "super" 키워드는 자식 클래스가 부모 클래스의 메서드나 속성을 호출하고, 이를 오버라이드할 수 있도록 지원합니다. 이는 상속의 기본적인 원칙 중 하나로, 코드의 재사용성을 높이고, 다형성을 구현하는 데 중요한 역할을 합니다.

### 사용법
"super" 키워드는 메서드나 속성을 호출할 때 다음과 같이 사용됩니다:
```kotlin
open class Parent {
    open fun greet() {
        println("Hello from Parent")
    }
}

class Child : Parent() {
    override fun greet() {
        super.greet() // 부모 클래스의 greet() 메서드를 호출
        println("Hello from Child")
    }
}
```
위의 예제에서 `Child` 클래스는 `Parent` 클래스의 `greet()` 메서드를 오버라이드하며, `super.greet()`를 사용하여 부모 클래스의 메서드를 호출하고 있습니다.

### 세부 사항
- "super" 키워드는 여러 부모 클래스를 상속받는 다중 상속에서는 주의해서 사용해야 합니다. 이 경우, 어떤 부모 클래스의 메서드를 호출할지 명확히 지정해야 합니다.
- Kotlin에서는 "super" 키워드를 통해 직접 부모 클래스의 메서드에 접근할 수 있지만, 자식 클래스에서 메서드를 오버라이드하여 새로운 기능을 추가할 수도 있습니다.

## 예제
```kotlin
open class Animal {
    open fun sound() {
        println("Animal sound")
    }
}

class Dog : Animal() {
    override fun sound() {
        super.sound() // 부모 클래스의 sound() 메서드 호출
        println("Bark")
    }
}

fun main() {
    val myDog = Dog()
    myDog.sound() // 출력: Animal sound \n Bark
}
```

## 설명
- "super" 키워드를 사용할 때 주의할 점은 부모 클래스의 메서드가 오버라이드 가능한지 확인하는 것입니다. 만약 부모 클래스의 메서드가 `final`로 선언되어 있다면, 자식 클래스에서 이를 오버라이드할 수 없습니다.
- 다중 상속을 사용할 경우, `super` 키워드를 통해 어떤 부모 클래스의 메서드를 호출할 것인지 명확하게 지정해야 하며, 이를 위해 `super<ParentClass>`와 같이 사용할 수 있습니다.

## 한 줄 요약
Kotlin에서 "super" 키워드는 자식 클래스가 부모 클래스의 속성과 메서드에 접근하여 상속과 다형성을 활용할 수 있도록 해주는 키워드입니다.