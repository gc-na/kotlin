<!--
Meta Description: # Lệnh "return" trong Kotlin: Cách Sử Dụng và Những Điều Cần Lưu Ý ## Tóm tắt Lệnh `return` trong Kotlin được sử dụng để thoát khỏi một hàm và trả về ...
Meta Keywords: hàm, return, trả, lệnh, trong
-->

# Lệnh "return" trong Kotlin: Cách Sử Dụng và Những Điều Cần Lưu Ý

## Tóm tắt
Lệnh `return` trong Kotlin được sử dụng để thoát khỏi một hàm và trả về giá trị cho nơi gọi hàm đó. Đây là một phần quan trọng trong việc điều khiển luồng chương trình và quản lý các giá trị trả về từ hàm.

## Tài liệu
Lệnh `return` trong Kotlin có vai trò quan trọng trong việc kết thúc một hàm và trả về kết quả. Khi sử dụng lệnh `return`, bạn có thể chỉ định một giá trị để hàm đó trả về. Nếu hàm được định nghĩa với kiểu trả về cụ thể (ví dụ: `Int`, `String`), bạn cần đảm bảo rằng giá trị bạn trả về tương thích với kiểu đó.

### Cách sử dụng
- Để sử dụng lệnh `return`, bạn chỉ cần viết `return` theo sau là giá trị bạn muốn trả về.
- Nếu hàm không cần trả về giá trị, bạn có thể sử dụng `return` mà không cần kèm theo giá trị.

```kotlin
fun sum(a: Int, b: Int): Int {
    return a + b
}
```

### Chi tiết
- Lệnh `return` có thể được sử dụng trong các hàm có kiểu trả về cụ thể và trong các hàm không có kiểu trả về (được gọi là hàm `Unit`).
- Trong một hàm, bạn có thể sử dụng nhiều lệnh `return`, nhưng một khi một lệnh `return` được thực thi, các lệnh phía sau nó sẽ không được thực hiện.

## Ví dụ
### Ví dụ 1: Hàm đơn giản
```kotlin
fun multiply(x: Int, y: Int): Int {
    return x * y
}

fun main() {
    val result = multiply(4, 5)
    println(result) // Kết quả: 20
}
```

### Ví dụ 2: Sử dụng trong hàm không trả về giá trị
```kotlin
fun printMessage(message: String) {
    if (message.isEmpty()) return
    println(message)
}

fun main() {
    printMessage("") // Không in gì
    printMessage("Xin chào, Kotlin!") // In: Xin chào, Kotlin!
}
```

## Giải thích
Một số lưu ý khi sử dụng lệnh `return`:
- Nếu bạn quên trả về giá trị trong một hàm có kiểu trả về cụ thể, trình biên dịch sẽ báo lỗi.
- Khi sử dụng trong các hàm lồng nhau hoặc các lambda, bạn cần chú ý đến phạm vi của lệnh `return`. Lệnh `return` sẽ thoát khỏi hàm gần nhất mà nó thuộc về.
- Trong các hàm lặp hoặc cấu trúc điều kiện, `return` có thể được sử dụng để thoát khỏi hàm sớm nếu điều kiện nhất định được thỏa mãn.

## Tóm tắt một dòng
Lệnh `return` trong Kotlin được sử dụng để thoát khỏi một hàm và trả về giá trị cho nơi gọi hàm đó.