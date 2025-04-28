<!--
Meta Description: # Kotlin 클래스: 객체지향 프로그래밍의 기초 ## 개요 Kotlin의 클래스는 객체지향 프로그래밍(OOP)에서 중요한 역할을 하며, 데이터와 기능을 하나의 단위로 묶어줍니다. 클래스를 통해 사용자 정의 데이터 타입을 생성하고, 이를 통해 객체를 인스턴스화하여 다...
Meta Keywords: kotlin, class, 클래스는, 기능을, 데이터
-->

# Kotlin 클래스: 객체지향 프로그래밍의 기초

## 개요
Kotlin의 클래스는 객체지향 프로그래밍(OOP)에서 중요한 역할을 하며, 데이터와 기능을 하나의 단위로 묶어줍니다. 클래스를 통해 사용자 정의 데이터 타입을 생성하고, 이를 통해 객체를 인스턴스화하여 다양한 기능을 구현할 수 있습니다.

## 문서
Kotlin에서 클래스는 객체를 생성하는 템플릿 역할을 합니다. 클래스는 속성(변수)과 메서드(함수)를 포함하여, 특정 데이터 구조와 그 데이터를 조작하는 기능을 정의합니다. Kotlin 클래스는 기본적으로 다음과 같은 구성 요소로 이루어져 있습니다:

- **속성(Property)**: 클래스의 상태를 나타내는 변수입니다.
- **메서드(Method)**: 클래스의 기능을 수행하는 함수입니다.
- **생성자(Constructor)**: 객체를 생성할 때 호출되는 특수한 메서드입니다.

### 클래스 정의
Kotlin에서 클래스를 정의하는 기본 구문은 다음과 같습니다:

```kotlin
class ClassName {
    // 속성
    var propertyName: Type = initialValue

    // 메서드
    fun methodName(parameters) {
        // 메서드 구현
    }
}
```

### 기본 생성자와 보조 생성자
Kotlin은 기본 생성자와 보조 생성자를 제공합니다. 기본 생성자는 클래스 선언과 함께 정의되며, 보조 생성자는 `constructor` 키워드를 사용하여 추가적으로 정의할 수 있습니다.

```kotlin
class Person(val name: String, var age: Int) { // 기본 생성자
    constructor(name: String) : this(name, 0) // 보조 생성자
}
```

## 예제
아래는 Kotlin 클래스의 기본 사용 예제입니다.

```kotlin
class Car(val model: String, var year: Int) {
    fun displayInfo() {
        println("모델: $model, 연도: $year")
    }
}

fun main() {
    val myCar = Car("현대 아반떼", 2020)
    myCar.displayInfo() // 출력: 모델: 현대 아반떼, 연도: 2020
}
```

## 설명
Kotlin 클래스를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

1. **상속**: Kotlin은 기본적으로 클래스가 final로 선언되어 상속이 불가능합니다. 상속을 허용하려면 `open` 키워드를 사용해야 합니다.
   
   ```kotlin
   open class Animal {
       open fun sound() {
           println("동물의 소리")
       }
   }

   class Dog : Animal() {
       override fun sound() {
           println("멍멍")
       }
   }
   ```

2. **데이터 클래스**: 데이터 클래스를 사용하면 불변 객체를 쉽게 만들 수 있습니다. `data` 키워드를 사용하여 정의합니다.

   ```kotlin
   data class User(val name: String, val age: Int)
   ```

3. **주 생성자와 보조 생성자**: 클래스에 여러 생성자를 정의할 수 있지만, 기본 생성자를 잘 활용하는 것이 좋습니다. 보조 생성자는 필수적이지 않습니다.

## 한 줄 요약
Kotlin 클래스는 객체지향 프로그래밍의 핵심 요소로, 데이터와 기능을 결합하여 사용자 정의 데이터 타입을 생성하는 데 사용됩니다.