<!--
Meta Description: # Lớp (Class) trong Kotlin: Khám Phá và Áp Dụng ## Tóm Tắt Lớp (class) trong Kotlin là một cấu trúc cơ bản cho phép lập trình viên định nghĩa các đối ...
Meta Keywords: lớp, kotlin, class, một, tượng
-->

# Lớp (Class) trong Kotlin: Khám Phá và Áp Dụng

## Tóm Tắt
Lớp (class) trong Kotlin là một cấu trúc cơ bản cho phép lập trình viên định nghĩa các đối tượng với thuộc tính và phương thức, giúp tổ chức và quản lý mã nguồn một cách hiệu quả.

## Tài Liệu
Trong Kotlin, lớp được sử dụng để tạo ra các đối tượng, cho phép bạn đóng gói dữ liệu và hành vi liên quan. Một lớp có thể bao gồm các thuộc tính (properties) và phương thức (methods). 

### Định Nghĩa Lớp
Cú pháp để định nghĩa một lớp trong Kotlin như sau:

```kotlin
class TenLop {
    // thuộc tính
    var tenThuocTinh: T = giáTrịMặcĐịnh

    // phương thức
    fun tenPhuongThuc() {
        // hành động
    }
}
```

### Tạo Đối Tượng
Sau khi định nghĩa lớp, bạn có thể tạo ra các đối tượng từ lớp đó:

```kotlin
val doiTuong = TenLop()
```

### Khởi Tạo Lớp
Kotlin hỗ trợ khởi tạo lớp với các tham số:

```kotlin
class Person(val name: String, var age: Int) {
    fun introduce() {
        println("Xin chào, tôi là $name và tôi $age tuổi.")
    }
}
```

## Ví Dụ
Dưới đây là một số ví dụ về cách sử dụng lớp trong Kotlin:

### Ví Dụ 1: Định Nghĩa Lớp Cơ Bản
```kotlin
class Dog {
    var name: String = "Chó"
    
    fun bark() {
        println("$name đang sủa!")
    }
}

fun main() {
    val myDog = Dog()
    myDog.bark() // Xuất: Chó đang sủa!
}
```

### Ví Dụ 2: Khởi Tạo Lớp với Tham Số
```kotlin
class Car(val model: String, var year: Int) {
    fun displayInfo() {
        println("Mô hình: $model, Năm sản xuất: $year")
    }
}

fun main() {
    val myCar = Car("Toyota", 2020)
    myCar.displayInfo() // Xuất: Mô hình: Toyota, Năm sản xuất: 2020
}
```

## Giải Thích
Khi làm việc với lớp trong Kotlin, có một số điểm cần lưu ý:

- **Kế thừa**: Kotlin hỗ trợ kế thừa lớp thông qua từ khóa `open`. Nếu không đánh dấu lớp là `open`, bạn không thể kế thừa lớp đó.
  
```kotlin
open class Animal {
    open fun makeSound() {
        println("Âm thanh động vật")
    }
}

class Cat : Animal() {
    override fun makeSound() {
        println("Meo meo")
    }
}
```

- **Lớp trừu tượng**: Bạn có thể định nghĩa lớp trừu tượng bằng từ khóa `abstract`, không thể tạo đối tượng từ lớp này trực tiếp.

- **Lớp dữ liệu (data class)**: Kotlin cung cấp lớp dữ liệu để giảm thiểu mã lặp lại khi chỉ cần lưu trữ dữ liệu.

```kotlin
data class User(val name: String, val age: Int)
```

## Tóm Tắt Một Dòng
Lớp trong Kotlin là một cấu trúc mạnh mẽ cho phép lập trình viên định nghĩa các đối tượng với thuộc tính và phương thức, giúp tối ưu hóa việc quản lý mã nguồn.