<!--
Meta Description: # Kotlin의 when 구문: 조건 분기 처리의 효율적인 방법 ## 개요 Kotlin의 `when` 구문은 여러 조건을 평가하여 해당하는 블록을 실행하는 강력한 조건 분기 기능입니다. Java의 `switch` 문과 유사하지만, 훨씬 더 유연하고 강력한 기능을 제공...
Meta Keywords: when, println, 구문은, 조건을, else
-->

# Kotlin의 when 구문: 조건 분기 처리의 효율적인 방법

## 개요
Kotlin의 `when` 구문은 여러 조건을 평가하여 해당하는 블록을 실행하는 강력한 조건 분기 기능입니다. Java의 `switch` 문과 유사하지만, 훨씬 더 유연하고 강력한 기능을 제공합니다.

## 문서화
`when` 구문은 여러 조건을 간단하게 처리할 수 있도록 설계되었습니다. 이를 통해 복잡한 조건문을 간결하게 작성하고, 가독성을 높일 수 있습니다. `when`은 특정 값에 대한 경우(case)를 정의하거나, 조건식을 평가하여 해당하는 블록을 실행할 수 있습니다.

### 사용법
기본적인 `when` 구문의 구조는 다음과 같습니다:

```kotlin
when (value) {
    condition1 -> action1
    condition2 -> action2
    else -> defaultAction
}
```

- `value`: 비교할 값입니다.
- `condition1`, `condition2`: 비교할 조건입니다.
- `action1`, `action2`: 조건이 참일 때 실행할 코드 블록입니다.
- `else`: 모든 조건이 거짓일 경우 실행할 기본 코드 블록입니다.

조건으로는 값 비교뿐만 아니라, 범위, 타입 검사 등도 사용할 수 있습니다.

## 예제
### 기본 예제
```kotlin
val x = 5
when (x) {
    1 -> println("x는 1입니다.")
    2 -> println("x는 2입니다.")
    3, 4 -> println("x는 3 또는 4입니다.")
    in 5..10 -> println("x는 5에서 10 사이입니다.")
    else -> println("x는 1, 2, 3, 4, 5, 6, 7, 8, 9, 10이 아닙니다.")
}
```

### 타입 검사 예제
```kotlin
fun printLength(obj: Any) {
    when (obj) {
        is String -> println("문자열 길이: ${obj.length}")
        is Int -> println("정수: $obj")
        else -> println("알 수 없는 타입")
    }
}
```

## 설명
`when` 구문을 사용할 때 주의할 점은 다음과 같습니다:

- `when` 구문은 반드시 단일 표현식이어야 하므로, 여러 조건을 사용할 경우 각 조건 사이에 적절한 논리 연산자를 사용해야 합니다.
- `when` 구문은 값이 일치하지 않으면 `else` 블록이 실행됩니다. 이를 통해 모든 경우를 처리할 수 있습니다.
- `when`은 특정 값에 대한 여러 조건을 간결하게 처리할 수 있지만, 너무 복잡한 조건문은 오히려 가독성을 떨어뜨릴 수 있으므로 적절히 사용해야 합니다.

## 한 줄 요약
Kotlin의 `when` 구문은 여러 조건을 간단하고 직관적으로 처리할 수 있는 강력한 조건 분기 기능입니다.