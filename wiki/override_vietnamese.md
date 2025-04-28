<!--
Meta Description: # Override trong Kotlin: Hướng dẫn Chi Tiết và Ví Dụ Cụ Thể ## Tóm tắt Trong Kotlin, từ khóa `override` được sử dụng để ghi đè các phương thức và thuộ...
Meta Keywords: lớp, trong, phương, thức, ghi
-->

# Override trong Kotlin: Hướng dẫn Chi Tiết và Ví Dụ Cụ Thể

## Tóm tắt
Trong Kotlin, từ khóa `override` được sử dụng để ghi đè các phương thức và thuộc tính của lớp cha trong một lớp con. Điều này cho phép lập trình viên tùy chỉnh hành vi của lớp con mà không cần thay đổi lớp cha.

## Tài liệu
### Mục đích
Từ khóa `override` trong Kotlin được sử dụng để xác định rằng một phương thức hoặc thuộc tính trong lớp con đang ghi đè một phương thức hoặc thuộc tính tương ứng trong lớp cha. Việc này thường được áp dụng trong lập trình hướng đối tượng, nơi các lớp con kế thừa từ các lớp cha.

### Cách sử dụng
Để sử dụng `override`, bạn cần:
1. Định nghĩa một phương thức hoặc thuộc tính trong lớp cha với từ khóa `open`.
2. Trong lớp con, sử dụng từ khóa `override` trước phương thức hoặc thuộc tính mà bạn muốn ghi đè.

### Chi tiết
- **Phương thức**: Nếu bạn muốn ghi đè một phương thức, phương thức trong lớp cha cần phải được khai báo với từ khóa `open`. Sau đó, trong lớp con, bạn có thể định nghĩa lại phương thức đó với từ khóa `override`.
- **Thuộc tính**: Tương tự, thuộc tính trong lớp cha cũng cần có từ khóa `open` để có thể được ghi đè trong lớp con.

## Ví dụ
### Ví dụ 1: Ghi đè phương thức
```kotlin
open class Animal {
    open fun sound() {
        println("Animal sound")
    }
}

class Dog : Animal() {
    override fun sound() {
        println("Bark")
    }
}

fun main() {
    val dog = Dog()
    dog.sound() // Kết quả: Bark
}
```

### Ví dụ 2: Ghi đè thuộc tính
```kotlin
open class Vehicle {
    open val speed: Int = 60
}

class Car : Vehicle() {
    override val speed: Int = 120
}

fun main() {
    val car = Car()
    println(car.speed) // Kết quả: 120
}
```

## Giải thích
### Những cạm bẫy phổ biến
- **Không sử dụng `open`**: Nếu bạn không khai báo phương thức hoặc thuộc tính trong lớp cha với từ khóa `open`, bạn sẽ không thể ghi đè chúng trong lớp con. Kotlin mặc định coi các phương thức và thuộc tính là `final`, nghĩa là không thể ghi đè.
- **Ghi đè không tương thích**: Khi ghi đè, bạn cần đảm bảo rằng chữ ký của phương thức hoặc thuộc tính trong lớp con phải khớp với lớp cha. Nếu không, trình biên dịch sẽ báo lỗi.

### Ghi chú bổ sung
- Việc sử dụng `override` giúp tăng tính linh hoạt và tái sử dụng mã trong lập trình hướng đối tượng.
- Bạn có thể ghi đè nhiều phương thức và thuộc tính trong một lớp con dựa trên nhu cầu của ứng dụng.

## Tóm tắt một dòng
Từ khóa `override` trong Kotlin cho phép ghi đè các phương thức và thuộc tính từ lớp cha trong lớp con, giúp tùy chỉnh hành vi của lớp con.