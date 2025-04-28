<!--
Meta Description: # Kotlin의 Sealed 클래스: 강력한 타입 안전성을 위한 선택 ## 개요 Kotlin의 sealed 클래스는 제한된 수의 하위 클래스만 가질 수 있는 클래스입니다. 이를 통해 데이터 모델의 타입 안전성을 강화하고, 패턴 매칭을 쉽게 할 수 있습니다. 이 기능은...
Meta Keywords: sealed, shape, 클래스는, val, class
-->

# Kotlin의 Sealed 클래스: 강력한 타입 안전성을 위한 선택

## 개요
Kotlin의 sealed 클래스는 제한된 수의 하위 클래스만 가질 수 있는 클래스입니다. 이를 통해 데이터 모델의 타입 안전성을 강화하고, 패턴 매칭을 쉽게 할 수 있습니다. 이 기능은 복잡한 데이터 구조를 안전하게 다루기 위해 유용합니다.

## 문서화
Sealed 클래스는 Kotlin에서 제공하는 강력한 기능으로, 특정 클래스의 하위 클래스들을 제한함으로써 코드의 안정성과 가독성을 높입니다. Sealed 클래스를 사용하면, 모든 하위 클래스가 같은 파일 내에 정의되어야 하며, 이는 코드의 관리성을 높여 줍니다. 주로 `when` 표현식과 함께 사용되어, 모든 가능성을 고려한 안전한 패턴 매칭을 가능하게 합니다.

### 사용법
Sealed 클래스를 정의하려면, `sealed` 키워드를 클래스 앞에 붙이면 됩니다. 하위 클래스는 같은 파일 내에서만 정의할 수 있습니다. 예를 들어:

```kotlin
sealed class Result

data class Success(val data: String) : Result()
data class Error(val message: String) : Result()
```

이렇게 정의된 후, `when` 표현식을 사용하여 결과를 처리할 수 있습니다.

## 예제
다음은 sealed 클래스를 사용하는 간단한 예제입니다:

```kotlin
sealed class Shape {
    data class Circle(val radius: Double) : Shape()
    data class Rectangle(val width: Double, val height: Double) : Shape()
}

fun calculateArea(shape: Shape): Double {
    return when (shape) {
        is Shape.Circle -> Math.PI * shape.radius * shape.radius
        is Shape.Rectangle -> shape.width * shape.height
    }
}

fun main() {
    val circle = Shape.Circle(2.0)
    val rectangle = Shape.Rectangle(3.0, 4.0)

    println("Circle Area: ${calculateArea(circle)}")
    println("Rectangle Area: ${calculateArea(rectangle)}")
}
```

## 설명
Sealed 클래스는 하위 클래스가 제한적이기 때문에, `when` 표현식에서 모든 경우의 수를 처리했는지 확인할 수 있습니다. 하위 클래스가 추가되지 않도록 보장되므로, 예기치 않은 상황에서 발생할 수 있는 오류를 줄일 수 있습니다. 

### 일반적인 함정
1. **하위 클래스의 위치**: Sealed 클래스의 하위 클래스는 반드시 같은 파일 내에 있어야 하며, 다른 파일로 이동할 수 없습니다.
2. **상태 불변성**: Sealed 클래스와 그 하위 클래스는 데이터의 불변성을 염두에 두고 설계해야 합니다.
3. **서브타입 제한**: Sealed 클래스는 다중 상속을 지원하지 않기 때문에, 상속 구조에 신중해야 합니다.

## 한 줄 요약
Kotlin의 sealed 클래스는 제한된 하위 클래스만 허용하여 타입 안전성을 높이고, 패턴 매칭을 간편하게 만들어 줍니다.