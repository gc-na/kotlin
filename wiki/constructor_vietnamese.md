<!--
Meta Description: # Constructor trong Kotlin: Hướng Dẫn Chi Tiết và Ví Dụ ## Tóm Tắt Constructor trong Kotlin là một thành phần quan trọng để khởi tạo đối tượng của lớp...
Meta Keywords: constructor, kotlin, author, string, định
-->

# Constructor trong Kotlin: Hướng Dẫn Chi Tiết và Ví Dụ

## Tóm Tắt
Constructor trong Kotlin là một thành phần quan trọng để khởi tạo đối tượng của lớp. Nó cho phép lập trình viên xác định cách mà các thuộc tính của lớp được thiết lập khi một đối tượng mới được tạo ra.

## Tài Liệu
### Mục Đích
Constructor trong Kotlin được sử dụng để định nghĩa cách thức khởi tạo các thuộc tính của một lớp. Điều này giúp đảm bảo rằng đối tượng được tạo ra có trạng thái hợp lệ ngay từ lúc khởi tạo.

### Cách Sử Dụng
Kotlin hỗ trợ hai loại constructor:
1. **Primary Constructor**: Đây là constructor chính, được định nghĩa ngay sau tên lớp.
2. **Secondary Constructor**: Là constructor phụ, được định nghĩa bên trong thân của lớp.

### Chi Tiết
- **Primary Constructor**: Được định nghĩa với cú pháp đơn giản, có thể bao gồm tham số và có thể gán giá trị mặc định cho các thuộc tính.
  
  ```kotlin
  class Person(val name: String, var age: Int = 0)
  ```

- **Secondary Constructor**: Được định nghĩa với từ khóa `constructor`, có thể gọi đến primary constructor hoặc thực hiện các tác vụ bổ sung.

  ```kotlin
  class Person {
      var name: String
      var age: Int

      constructor(name: String) {
          this.name = name
          this.age = 0
      }

      constructor(name: String, age: Int) {
          this.name = name
          this.age = age
      }
  }
  ```

## Ví Dụ
### Ví Dụ về Primary Constructor
```kotlin
class Car(val model: String, var year: Int) {
    fun displayInfo() {
        println("Model: $model, Year: $year")
    }
}

fun main() {
    val car = Car("Toyota", 2021)
    car.displayInfo() // Output: Model: Toyota, Year: 2021
}
```

### Ví Dụ về Secondary Constructor
```kotlin
class Book {
    var title: String
    var author: String

    constructor(title: String) {
        this.title = title
        this.author = "Unknown"
    }

    constructor(title: String, author: String) {
        this.title = title
        this.author = author
    }
}

fun main() {
    val book1 = Book("Kotlin Programming")
    val book2 = Book("Android Development", "John Doe")

    println("Book 1: ${book1.title}, Author: ${book1.author}") // Output: Book 1: Kotlin Programming, Author: Unknown
    println("Book 2: ${book2.title}, Author: ${book2.author}") // Output: Book 2: Android Development, Author: John Doe
}
```

## Giải Thích
Một số điểm cần lưu ý khi làm việc với constructors trong Kotlin:
- Ký hiệu `val` và `var` trong primary constructor giúp tự động tạo getter và setter cho thuộc tính.
- Nếu không có constructor nào được định nghĩa, Kotlin sẽ tự động tạo một constructor rỗng.
- Bạn không thể định nghĩa constructor trong lớp `object`.

## Tóm Tắt Một Dòng
Constructor trong Kotlin là công cụ chính để khởi tạo các thuộc tính của lớp, bao gồm primary và secondary constructors.