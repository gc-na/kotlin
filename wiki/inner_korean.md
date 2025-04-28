<!--
Meta Description: # Kotlin의 Inner 클래스: 개념과 활용법 ## 개요 Kotlin의 Inner 클래스는 외부 클래스의 인스턴스와 연결된 내부 클래스를 정의하는 방법으로, 객체 지향 프로그래밍에서 유용하게 사용됩니다. Inner 클래스는 외부 클래스의 프로퍼티와 메서드에 접근할...
Meta Keywords: inner, 클래스는, 클래스의, val, 클래스를
-->

# Kotlin의 Inner 클래스: 개념과 활용법

## 개요
Kotlin의 Inner 클래스는 외부 클래스의 인스턴스와 연결된 내부 클래스를 정의하는 방법으로, 객체 지향 프로그래밍에서 유용하게 사용됩니다. Inner 클래스는 외부 클래스의 프로퍼티와 메서드에 접근할 수 있는 특징을 가지고 있습니다.

## 문서화

### 목적
Inner 클래스는 외부 클래스의 컨텍스트에서 동작하는 클래스를 정의할 수 있게 해줍니다. 이를 통해 코드의 구조를 보다 명확하게 하고, 클래스 간의 관계를 더 쉽게 표현할 수 있습니다.

### 사용법
Inner 클래스를 정의하려면, 외부 클래스 내부에서 `inner` 키워드를 사용하여 선언합니다. 다음은 기본적인 사용법입니다:

```kotlin
class OuterClass {
    private val outerProperty = "Outer Property"

    inner class InnerClass {
        fun accessOuterProperty() = outerProperty
    }
}
```

위의 예제에서 `InnerClass`는 `OuterClass`의 인스턴스에 접근할 수 있으며, `outerProperty`를 사용할 수 있습니다.

### 세부사항
- Inner 클래스는 외부 클래스의 인스턴스에 대한 참조를 암묵적으로 유지합니다. 이는 메모리 사용에 영향을 미칠 수 있으므로 주의해야 합니다.
- Inner 클래스는 외부 클래스의 private 멤버에도 접근할 수 있습니다.
- Kotlin에서 Inner 클래스를 사용할 때는 `inner` 키워드를 반드시 명시해야 하며, 그렇지 않으면 컴파일 오류가 발생합니다.

## 예제

### 기본 사용 예
다음은 Inner 클래스를 사용하는 간단한 예제입니다:

```kotlin
class House(val address: String) {
    inner class Room(val roomName: String) {
        fun getAddress() = "Room: $roomName, House Address: $address"
    }
}

fun main() {
    val myHouse = House("123 Main St")
    val myRoom = myHouse.Room("Living Room")
    println(myRoom.getAddress())  // 출력: Room: Living Room, House Address: 123 Main St
}
```

### 더 복잡한 예
Inner 클래스를 활용하여 더 복잡한 구조를 구현할 수 있습니다:

```kotlin
class Car(val model: String) {
    inner class Engine(val horsepower: Int) {
        fun getCarDetails() = "Car Model: $model, Horsepower: $horsepower"
    }
}

fun main() {
    val myCar = Car("Toyota")
    val myEngine = myCar.Engine(200)
    println(myEngine.getCarDetails())  // 출력: Car Model: Toyota, Horsepower: 200
}
```

## 설명

### 일반적인 함정
- Inner 클래스는 외부 클래스의 인스턴스에 대한 참조를 가지고 있으므로, 필요하지 않은 경우 사용을 피하는 것이 좋습니다. 그렇지 않으면 메모리 누수의 원인이 될 수 있습니다.
- Inner 클래스를 사용할 때 `inner` 키워드를 잘못 사용하거나 누락할 경우 컴파일 오류가 발생하므로 주의해야 합니다.

### 추가 메모
- Nested 클래스와 Inner 클래스는 다릅니다. Nested 클래스는 외부 클래스의 인스턴스와 연결되지 않으며, `inner` 키워드를 사용하지 않아도 됩니다.
- Inner 클래스는 외부 클래스의 상태에 접근할 수 있는 장점이 있지만, 이는 설계를 복잡하게 만들 수 있다는 점도 고려해야 합니다.

## 한줄 요약
Kotlin의 Inner 클래스는 외부 클래스의 인스턴스에 직접 연결되어 해당 클래스의 프로퍼티와 메서드에 접근할 수 있는 유용한 기능입니다.