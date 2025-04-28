<!--
Meta Description: # Kotlin의 "return" 키워드 이해하기 ## 개요 Kotlin에서 `return` 키워드는 함수나 람다 표현식에서 값을 반환하는 데 사용됩니다. 이 키워드는 함수의 실행을 종료하고, 호출자에게 값을 전달하는 중요한 역할을 합니다. ## 문서화 ### 목적 `...
Meta Keywords: return, int, 키워드는, 합니다, kotlin
-->

# Kotlin의 "return" 키워드 이해하기

## 개요
Kotlin에서 `return` 키워드는 함수나 람다 표현식에서 값을 반환하는 데 사용됩니다. 이 키워드는 함수의 실행을 종료하고, 호출자에게 값을 전달하는 중요한 역할을 합니다.

## 문서화

### 목적
`return` 키워드는 Kotlin 프로그램의 제어 흐름을 관리하는 데 필수적입니다. 이는 함수를 종료하고, 특정 값을 반환하고자 할 때 사용됩니다. 

### 사용법
함수 내에서 `return` 문을 사용하여 값을 반환할 수 있습니다. 다음은 기본적인 구문입니다:

```kotlin
fun functionName(parameters): ReturnType {
    // some logic
    return value
}
```

이때, `ReturnType`은 반환할 값의 데이터 타입을 의미하며, `value`는 반환할 실제 값을 나타냅니다.

### 세부사항
- `return` 문이 호출되면 함수의 실행이 즉시 종료됩니다.
- 반환할 값의 타입은 함수의 반환 타입과 일치해야 합니다.
- 람다 표현식에서도 `return`을 사용할 수 있지만, 외부 함수와의 관계를 고려해야 합니다.
- `return` 문은 조건문 안에서도 사용될 수 있습니다.

## 예제

### 기본 사용 예
```kotlin
fun add(a: Int, b: Int): Int {
    return a + b
}

fun main() {
    val sum = add(5, 3)
    println(sum) // 출력: 8
}
```

### 람다 표현식에서의 사용
```kotlin
val multiply: (Int, Int) -> Int = { a, b ->
    return@multiply a * b
}

fun main() {
    val product = multiply(4, 5)
    println(product) // 출력: 20
}
```

## 설명

### 일반적인 실수 및 주의 사항
- `return` 문이 없는 함수는 자동으로 `Unit`을 반환합니다. 이는 Java의 `void`와 유사합니다.
- 람다 표현식에서 `return`을 사용할 때는 레이블을 명시적으로 지정해야 합니다. 그렇지 않으면, 외부 함수에 대한 `return`으로 간주될 수 있습니다.
- `return` 문이 없는 경우, 최종 표현식의 결과가 자동으로 반환됩니다.

## 한 줄 요약
Kotlin의 `return` 키워드는 함수와 람다 표현식에서 값을 반환하고 실행을 종료하는 데 사용됩니다.