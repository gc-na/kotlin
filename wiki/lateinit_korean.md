<!--
Meta Description: # Kotlin의 lateinit: 지연 초기화에 대한 완벽 가이드 ## 개요 Kotlin의 `lateinit`는 변수를 초기화할 때 즉시 값을 지정하지 않고, 나중에 초기화할 수 있도록 허용하는 기능입니다. 주로 비어 있는 속성을 선언할 때 사용되며, null이 아닌...
Meta Keywords: lateinit, sample, name, 초기화, 변수를
-->

# Kotlin의 lateinit: 지연 초기화에 대한 완벽 가이드

## 개요
Kotlin의 `lateinit`는 변수를 초기화할 때 즉시 값을 지정하지 않고, 나중에 초기화할 수 있도록 허용하는 기능입니다. 주로 비어 있는 속성을 선언할 때 사용되며, null이 아닌 타입을 요구하는 경우 유용합니다.

## 문서화
`lateinit`는 Kotlin에서 클래스 속성을 지연 초기화하기 위한 키워드로, 주로 `var`로 선언된 비기본형(non-nullable) 변수를 사용할 때 사용됩니다. `lateinit`를 사용하면 객체가 생성된 후 특정 시점에 값을 할당할 수 있습니다. 이로 인해 초기화 단계에서 부적절한 값을 피할 수 있습니다.

### 용도
- `lateinit`은 객체가 생성된 직후에는 값을 할당할 수 없는 경우에 유용합니다.
- 주로 의존성 주입(Dependency Injection) 및 다양한 테스트 시나리오에서 사용됩니다.

### 사용법
`lateinit` 키워드를 사용하려면, 클래스 속성을 선언할 때 `lateinit`을 붙여줍니다. 아래는 기본 문법입니다.

```kotlin
lateinit var variableName: Type
```

변수에 접근하기 전에 반드시 초기화해야 하며, 초기화되지 않은 상태에서 접근하면 `UninitializedPropertyAccessException`이 발생합니다.

## 예제
```kotlin
class Sample {
    lateinit var name: String

    fun initializeName() {
        name = "Kotlin"
    }

    fun printName() {
        if (::name.isInitialized) {
            println(name)
        } else {
            println("Name is not initialized")
        }
    }
}

fun main() {
    val sample = Sample()
    sample.printName() // Name is not initialized
    sample.initializeName()
    sample.printName() // Kotlin
}
```

## 설명
- **초기화 체크**: `lateinit`으로 선언된 변수는 접근하기 전에 초기화 여부를 확인할 수 있습니다. `::variableName.isInitialized`를 사용하여 초기화 여부를 확인할 수 있습니다.
- **제약 사항**: `lateinit`은 기본형(Int, Double 등) 변수에는 사용할 수 없습니다. 이러한 타입에는 nullable 타입을 사용하는 것이 좋습니다.
- **예외 처리**: 초기화되지 않은 상태에서 변수를 접근하려고 할 경우 `UninitializedPropertyAccessException`이 발생하므로 반드시 초기화 후 사용해야 합니다.

## 한 줄 요약
Kotlin의 `lateinit`는 변수를 나중에 초기화할 수 있도록 하여 null이 아닌 타입을 안전하게 처리할 수 있게 해주는 기능입니다.