<!--
Meta Description: # Sử Dụng `const` Trong Kotlin: Định Nghĩa và Hướng Dẫn Cụ Thể ## Tóm Tắt `const` là một từ khóa trong Kotlin được sử dụng để khai báo hằng số, cho ph...
Meta Keywords: const, các, trong, được, dụng
-->

# Sử Dụng `const` Trong Kotlin: Định Nghĩa và Hướng Dẫn Cụ Thể

## Tóm Tắt
`const` là một từ khóa trong Kotlin được sử dụng để khai báo hằng số, cho phép bạn định nghĩa các giá trị không thay đổi trong thời gian chạy của chương trình. Những hằng số này có thể được sử dụng để tối ưu hóa hiệu suất và tính rõ ràng của mã nguồn.

## Tài Liệu
### Mục Đích
Trong Kotlin, từ khóa `const` được sử dụng để đánh dấu một biến là hằng số, nghĩa là giá trị của nó sẽ không thay đổi trong suốt vòng đời của ứng dụng. Các hằng số được khai báo với `const` phải là kiểu dữ liệu nguyên thủy (như `Int`, `Double`, `String`, v.v.) và phải được khởi tạo tại thời điểm biên dịch.

### Cách Sử Dụng
Để sử dụng `const`, bạn cần khai báo biến bên trong một object, class hoặc interface. Ví dụ:

```kotlin
const val PI = 3.14
```

Biến `PI` ở trên được khai báo là một hằng số có giá trị là 3.14. Bạn có thể sử dụng `const` để định nghĩa các giá trị như URL, các thông số cấu hình, hoặc các hằng số toán học.

### Chi Tiết
- Hằng số `const` chỉ có thể được định nghĩa ở cấp độ top-level hoặc trong các companion object.
- `const` chỉ có thể được áp dụng cho các kiểu dữ liệu nguyên thủy (primitive types) và `String`.
- Các hằng số được khai báo với `const` được biên dịch thành các giá trị cụ thể trong mã bytecode, giúp tối ưu hóa hiệu suất.

## Ví Dụ
### Ví Dụ Cơ Bản
```kotlin
const val MAX_USERS = 100
const val BASE_URL = "https://api.example.com/"

// Sử dụng trong hàm
fun printInfo() {
    println("Số người dùng tối đa: $MAX_USERS")
    println("URL cơ sở: $BASE_URL")
}
```

### Ví Dụ Trong Companion Object
```kotlin
class Config {
    companion object {
        const val TIMEOUT = 5000
    }
}

fun main() {
    println("Thời gian chờ: ${Config.TIMEOUT} ms")
}
```

## Giải Thích
### Những Cạm Bẫy Thường Gặp
- Hằng số `const` không thể được khởi tạo bằng các biểu thức không phải hằng số (như các phép toán, hàm, v.v.), điều này có thể gây nhầm lẫn cho lập trình viên mới.
- Không nên sử dụng `const` cho các kiểu dữ liệu phức tạp (như danh sách, map), vì nó chỉ chấp nhận các kiểu nguyên thủy và `String`.
- Khai báo `const` trong một class thông thường sẽ không hợp lệ; chỉ được thực hiện trong companion object hoặc top-level.

## Tóm Tắt Một Dòng
`const` trong Kotlin cho phép bạn khai báo các hằng số không thay đổi, giúp tối ưu hóa mã nguồn và cải thiện hiệu suất chương trình.