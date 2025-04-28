<!--
Meta Description: # Từ Khóa "super" trong Kotlin: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa "super" trong Kotlin được sử dụng để tham chiếu đến lớp cha trong hệ thống ...
Meta Keywords: lớp, super, cha, trong, kotlin
-->

# Từ Khóa "super" trong Kotlin: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa "super" trong Kotlin được sử dụng để tham chiếu đến lớp cha trong hệ thống thừa kế, giúp truy cập các thuộc tính và phương thức của lớp cha.

## Tài Liệu
Trong Kotlin, từ khóa "super" cho phép bạn truy cập các thành phần của lớp cha khi lớp con kế thừa từ lớp đó. Điều này rất hữu ích khi bạn muốn mở rộng hoặc ghi đè các phương thức của lớp cha mà vẫn duy trì khả năng truy cập các thành phần gốc.

### Mục Đích
- Truy cập các phương thức và thuộc tính của lớp cha.
- Hỗ trợ ghi đè phương thức mà vẫn có thể gọi phương thức của lớp cha.

### Cách Sử Dụng
Cú pháp cơ bản để sử dụng "super" trong Kotlin là:
```kotlin
super.methodName()
```
Hoặc truy cập thuộc tính như sau:
```kotlin
val value = super.propertyName
```

## Ví Dụ
Dưới đây là một số ví dụ đơn giản về cách sử dụng "super" trong Kotlin:

### Ví dụ 1: Ghi Đè Phương Thức
```kotlin
open class Animal {
    open fun sound() {
        println("Animal makes sound")
    }
}

class Dog : Animal() {
    override fun sound() {
        super.sound() // Gọi phương thức sound() của lớp cha
        println("Dog barks")
    }
}

fun main() {
    val dog = Dog()
    dog.sound()
}
```
**Kết quả:**
```
Animal makes sound
Dog barks
```

### Ví dụ 2: Truy Cập Thuộc Tính
```kotlin
open class Vehicle {
    open val maxSpeed: Int = 120
}

class Car : Vehicle() {
    override val maxSpeed: Int = 150

    fun showSpeed() {
        println("Max speed of car: ${super.maxSpeed}") // Gọi thuộc tính maxSpeed của lớp cha
    }
}

fun main() {
    val car = Car()
    car.showSpeed()
}
```
**Kết quả:**
```
Max speed of car: 120
```

## Giải Thích
Khi sử dụng "super", có một số điều cần lưu ý:
- **Ghi Đè và Gọi Phương Thức:** Nếu bạn không gọi "super" trong một phương thức được ghi đè, bạn sẽ không truy cập được hành vi của lớp cha. Điều này có thể dẫn đến việc bỏ lỡ các logic quan trọng trong lớp cha.
- **Nhiều Cấp Thừa Kế:** Trong trường hợp có nhiều lớp cha, "super" sẽ chỉ tham chiếu đến lớp cha gần nhất. Cần lưu ý điều này khi thiết kế hệ thống thừa kế phức tạp.

## Tóm Tắt Một Dòng
Từ khóa "super" trong Kotlin là công cụ quan trọng cho phép lớp con truy cập và mở rộng các phương thức và thuộc tính của lớp cha trong hệ thống thừa kế.