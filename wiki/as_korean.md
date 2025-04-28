<!--
Meta Description: # Kotlin의 "as" 키워드: 타입 변환과 안전성 ## 개요 Kotlin에서 "as" 키워드는 객체의 타입을 변환하는 데 사용됩니다. 이 키워드는 안전한 타입 캐스팅을 지원하며, 올바른 타입으로 변환될 수 없는 경우 예외를 발생시킵니다. ## 문서화 "as" 키워...
Meta Keywords: val, string, 안전한, kotlin, null
-->

# Kotlin의 "as" 키워드: 타입 변환과 안전성

## 개요
Kotlin에서 "as" 키워드는 객체의 타입을 변환하는 데 사용됩니다. 이 키워드는 안전한 타입 캐스팅을 지원하며, 올바른 타입으로 변환될 수 없는 경우 예외를 발생시킵니다.

## 문서화
"as" 키워드는 Kotlin의 타입 시스템에서 중요한 역할을 합니다. 주로 두 가지 형태로 사용됩니다:

1. **강제 타입 변환 (as)**: 객체를 특정 타입으로 변환하고, 변환이 불가능할 경우 `ClassCastException`을 발생시킵니다.
   
   ```kotlin
   val obj: Any = "Hello, Kotlin"
   val str: String = obj as String // 정상적으로 변환
   ```

2. **안전한 타입 변환 (as?)**: 객체를 특정 타입으로 변환하되, 변환이 불가능할 경우 null을 반환합니다. 이는 NullPointerException을 방지하는 데 유용합니다.

   ```kotlin
   val obj: Any = 123
   val str: String? = obj as? String // 변환 실패 시 null 반환
   ```

이러한 방식으로 "as"는 동적 타입의 안전한 처리를 도와줍니다.

## 예제
다음은 "as" 키워드의 기본 사용 예제입니다.

```kotlin
fun main() {
    val obj1: Any = "Kotlin"
    val str1: String = obj1 as String // 정상 변환
    println(str1)

    val obj2: Any = 42
    val str2: String? = obj2 as? String // 변환 실패, null 반환
    println(str2) // 출력: null
}
```

## 설명
"as" 키워드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **타입 불일치**: 강제 타입 변환을 사용할 때, 객체가 지정된 타입이 아닐 경우 `ClassCastException`이 발생하므로, 안전한 변환인 "as?"를 사용하는 것이 좋습니다.
- **Null 처리**: "as?"를 사용하면 변환이 실패할 경우 null을 반환하므로, null 체크를 통해 예외를 방지할 수 있습니다.
- **타입 시스템**: Kotlin의 타입 시스템은 정적이며, 런타임에서 타입이 결정되는 안전성을 제공합니다. 따라서 "as" 키워드를 잘 활용하면 더 안전한 코드를 작성할 수 있습니다.

## 한 줄 요약
Kotlin의 "as" 키워드는 객체를 특정 타입으로 변환하는 데 사용되며, 안전한 타입 캐스팅을 지원합니다.