<!--
Meta Description: # Câu lệnh "catch" trong Kotlin: Xử lý ngoại lệ hiệu quả ## Tóm tắt Câu lệnh `catch` trong Kotlin được sử dụng để xử lý ngoại lệ, cho phép lập trình v...
Meta Keywords: ngoại, catch, trong, kotlin, trình
-->

# Câu lệnh "catch" trong Kotlin: Xử lý ngoại lệ hiệu quả

## Tóm tắt
Câu lệnh `catch` trong Kotlin được sử dụng để xử lý ngoại lệ, cho phép lập trình viên quản lý các lỗi có thể xảy ra trong quá trình thực thi chương trình một cách an toàn và hiệu quả.

## Tài liệu
Trong Kotlin, `catch` là một phần của khối `try-catch` được sử dụng để bắt và xử lý các ngoại lệ. Khi một ngoại lệ xảy ra trong khối `try`, việc xử lý sẽ chuyển đến khối `catch`, nơi bạn có thể định nghĩa hành động cần thực hiện để khắc phục lỗi hoặc thông báo cho người dùng.

### Cú pháp
```kotlin
try {
    // Mã có thể gây ra ngoại lệ
} catch (e: ExceptionType) {
    // Xử lý ngoại lệ
}
```

### Mục đích
Mục đích của câu lệnh `catch` là để bảo vệ chương trình khỏi việc bị dừng đột ngột khi xảy ra lỗi, cho phép lập trình viên thực hiện các hành động cần thiết để xử lý lỗi đó.

## Ví dụ
### Ví dụ 1: Bắt ngoại lệ đơn giản
```kotlin
fun main() {
    val number = "123a"
    try {
        val result = number.toInt()
    } catch (e: NumberFormatException) {
        println("Ngoại lệ: ${e.message}")
    }
}
```
Trong ví dụ này, khi cố gắng chuyển đổi chuỗi không phải số thành số nguyên, một ngoại lệ sẽ được ném ra và được bắt bởi khối `catch`.

### Ví dụ 2: Bắt nhiều loại ngoại lệ
```kotlin
fun main() {
    val numbers = listOf(1, 2, 3)
    try {
        println(numbers[5])
    } catch (e: IndexOutOfBoundsException) {
        println("Ngoại lệ: ${e.message}")
    } catch (e: Exception) {
        println("Ngoại lệ không xác định: ${e.message}")
    }
}
```
Trong ví dụ này, chúng ta đang bắt ngoại lệ `IndexOutOfBoundsException` khi cố gắng truy cập vào chỉ mục không hợp lệ trong danh sách.

## Giải thích
### Cạm bẫy thường gặp
- **Không bắt ngoại lệ cụ thể**: Khi sử dụng `catch`, nên bắt ngoại lệ cụ thể thay vì sử dụng `catch (e: Exception)` chung chung, vì điều này có thể dẫn đến việc bỏ qua các lỗi quan trọng khác.
- **Thiếu khối `finally`**: Nếu bạn cần thực hiện một số thao tác cuối cùng (như đóng tài nguyên), hãy sử dụng khối `finally` để đảm bảo rằng mã đó luôn được thực thi, bất kể có xảy ra ngoại lệ hay không.

## Tóm tắt một câu
Câu lệnh `catch` trong Kotlin cho phép lập trình viên xử lý các ngoại lệ một cách an toàn, giúp chương trình hoạt động ổn định hơn.