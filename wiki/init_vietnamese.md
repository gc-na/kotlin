<!--
Meta Description: # Tìm hiểu về "init" trong Kotlin: Khởi Tạo Đối Tượng và Giá Trị ## Tóm tắt Trong Kotlin, `init` là một khối khởi tạo được sử dụng trong lớp để khởi t...
Meta Keywords: tạo, được, init, khối, trong
-->

# Tìm hiểu về "init" trong Kotlin: Khởi Tạo Đối Tượng và Giá Trị

## Tóm tắt
Trong Kotlin, `init` là một khối khởi tạo được sử dụng trong lớp để khởi tạo các thuộc tính của đối tượng khi nó được tạo. Khối này cho phép lập trình viên thực hiện các hành động cần thiết ngay khi một đối tượng được khởi tạo.

## Tài liệu
Khối `init` trong Kotlin được sử dụng để thực hiện khởi tạo đối tượng và thiết lập các giá trị cho thuộc tính của lớp. Khi một lớp được khởi tạo, khối `init` sẽ được gọi ngay lập tức và thực thi mã bên trong nó. Điều này rất hữu ích cho việc kiểm tra dữ liệu đầu vào hoặc thực hiện các thao tác khởi tạo phức tạp.

### Cú pháp
```kotlin
class ClassName(param1: Type1, param2: Type2) {
    // Khai báo thuộc tính
    var property1: Type1 = param1
    var property2: Type2 = param2

    // Khối init
    init {
        // Mã khởi tạo
    }
}
```

### Mục đích
- **Khởi tạo thuộc tính**: Thiết lập giá trị ban đầu cho các thuộc tính của lớp.
- **Thực hiện logic**: Thực hiện các thao tác cần thiết ngay khi đối tượng được tạo.

## Ví dụ
### Ví dụ Cơ Bản
```kotlin
class Person(name: String, age: Int) {
    var name: String = name
    var age: Int = age

    init {
        println("Đối tượng Person được tạo với tên: $name và tuổi: $age")
    }
}

fun main() {
    val person = Person("Nguyễn Văn A", 30)
}
```

Khi chạy đoạn mã trên, sẽ in ra:
```
Đối tượng Person được tạo với tên: Nguyễn Văn A và tuổi: 30
```

## Giải thích
### Cạm bẫy Thường Gặp
- **Không gọi khối `init`**: Nếu lớp không có khối `init`, thì không có bất kỳ hành động nào được thực hiện khi đối tượng được tạo.
- **Khó khăn trong việc sửa đổi**: Nếu khối `init` quá phức tạp, có thể gây ra khó khăn trong việc đọc và bảo trì mã.

### Lưu ý
- Có thể có nhiều khối `init` trong một lớp, và chúng sẽ được thực hiện theo thứ tự từ trên xuống dưới.
- Khối `init` có thể sử dụng các thuộc tính đã được khai báo trong lớp.

## Tóm tắt Một Dòng
Khối `init` trong Kotlin cho phép thiết lập và khởi tạo thuộc tính của lớp ngay khi đối tượng được tạo ra.