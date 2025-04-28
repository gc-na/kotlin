<!--
Meta Description: # Kotlin Enum: 열거형의 모든 것 ## 개요 Kotlin에서 enum(열거형)은 상수 집합을 정의하고 사용할 수 있는 강력한 도구입니다. 열거형을 사용하면 관련된 상수 값을 그룹화하여 코드의 가독성을 높이고 오류를 줄일 수 있습니다. ## 문서화 Kotlin...
Meta Keywords: color, enum, green, kotlin, kotlin의
-->

# Kotlin Enum: 열거형의 모든 것

## 개요
Kotlin에서 enum(열거형)은 상수 집합을 정의하고 사용할 수 있는 강력한 도구입니다. 열거형을 사용하면 관련된 상수 값을 그룹화하여 코드의 가독성을 높이고 오류를 줄일 수 있습니다.

## 문서화
Kotlin의 enum 클래스는 특정 값의 집합을 정의하는데 사용됩니다. enum은 주로 상태나 옵션을 나타내며, 각 상수는 고유한 인스턴스입니다. 열거형은 다음과 같은 용도로 사용됩니다:

- **상수 집합 정의**: 특정 카테고리의 고정된 값을 정의합니다.
- **타입 안전성 제공**: 각 열거형 값은 특정 타입으로 제한되어 잘못된 값 사용을 방지합니다.
- **스위치 문과 결합**: when 문과 함께 사용하여 조건부 로직을 쉽게 작성할 수 있습니다.

```kotlin
enum class Direction {
    NORTH, SOUTH, EAST, WEST
}
```

위의 예제에서 `Direction` 열거형은 네 가지 방향을 정의합니다.

## 예제
다음은 Kotlin에서 열거형을 사용하는 기본 예제입니다.

```kotlin
enum class Color {
    RED, GREEN, BLUE
}

fun printColor(color: Color) {
    when (color) {
        Color.RED -> println("Red color")
        Color.GREEN -> println("Green color")
        Color.BLUE -> println("Blue color")
    }
}

fun main() {
    printColor(Color.GREEN) // 출력: Green color
}
```

위의 예제에서는 `Color`라는 열거형을 정의하고, `printColor` 함수를 통해 해당 색상을 출력합니다.

## 설명
Kotlin의 enum 사용 시 주의할 점은 다음과 같습니다:

- **상수 추가**: 열거형에 새로운 상수를 추가할 때는 기존 코드의 호환성에 유의해야 합니다.
- **상속 불가**: Kotlin의 enum 클래스는 다른 클래스를 상속받을 수 없습니다. 이는 열거형이 고유한 인스턴스를 가지기 위해서입니다.
- **추가 속성**: 열거형에 속성을 추가할 수 있지만, 이를 위해서는 생성자를 정의해야 합니다.

```kotlin
enum class Status(val code: Int) {
    SUCCESS(200),
    NOT_FOUND(404),
    SERVER_ERROR(500)
}
```

위 예제에서는 각 상태에 대해 코드 값을 추가했습니다.

## 한 문장 요약
Kotlin의 enum은 관련된 상수 값을 그룹화하여 코드의 가독성을 높이고 오류를 방지하는데 유용한 열거형 기능입니다.