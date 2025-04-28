<!--
Meta Description: # Tính Năng "tailrec" Trong Kotlin: Tối Ưu Hóa Đệ Quy ## Tóm Tắt Tính năng `tailrec` trong Kotlin cho phép tối ưu hóa các hàm đệ quy bằng cách chuyển ...
Meta Keywords: hàm, tailrec, quy, kotlin, int
-->

# Tính Năng "tailrec" Trong Kotlin: Tối Ưu Hóa Đệ Quy

## Tóm Tắt
Tính năng `tailrec` trong Kotlin cho phép tối ưu hóa các hàm đệ quy bằng cách chuyển đổi chúng thành vòng lặp, giúp tránh lỗi tràn ngăn xếp.

## Tài Liệu
Từ khóa `tailrec` là một tính năng quan trọng trong Kotlin, được sử dụng để đánh dấu một hàm là hàm đệ quy đuôi. Khi một hàm được đánh dấu là `tailrec`, trình biên dịch Kotlin sẽ tự động chuyển đổi hàm đệ quy thành một vòng lặp, nhằm cải thiện khả năng sử dụng bộ nhớ và hiệu suất.

### Mục Đích
Mục đích chính của `tailrec` là ngăn chặn lỗi tràn ngăn xếp (Stack Overflow) thường xảy ra khi gọi đệ quy quá nhiều lần. Điều này đặc biệt hữu ích khi xử lý các thuật toán có thể gọi đệ quy sâu như tính toán giai thừa, số Fibonacci, hay duyệt cây.

### Cách Sử Dụng
Để sử dụng `tailrec`, bạn chỉ cần thêm từ khóa này vào trước định nghĩa hàm. Hàm phải đạt được một số điều kiện nhất định để có thể được tối ưu hóa:

1. Hàm phải gọi chính nó ở vị trí cuối cùng (có thể là trong một biểu thức khác).
2. Không có bất kỳ phép toán nào xảy ra sau lời gọi hàm.

### Cú Pháp
```kotlin
tailrec fun functionName(parameters): ReturnType {
    // Thân hàm
}
```

## Ví Dụ
### Ví Dụ 1: Tính Giai Thừa
```kotlin
tailrec fun factorial(n: Int, acc: Int = 1): Int {
    return if (n == 0) acc else factorial(n - 1, n * acc)
}

fun main() {
    println(factorial(5))  // Kết quả: 120
}
```

### Ví Dụ 2: Số Fibonacci
```kotlin
tailrec fun fibonacci(n: Int, a: Int = 0, b: Int = 1): Int {
    return if (n == 0) a else fibonacci(n - 1, b, a + b)
}

fun main() {
    println(fibonacci(10))  // Kết quả: 55
}
```

## Giải Thích
### Những Cạm Bẫy Thường Gặp
- **Không Đạt Điều Kiện Đệ Quy Đuôi:** Nếu bạn gọi hàm đệ quy không ở vị trí cuối cùng, hàm đó sẽ không được tối ưu hóa với `tailrec`. Ví dụ:
  ```kotlin
  tailrec fun example(n: Int): Int {
      return if (n == 0) 1 else example(n - 1) + 1  // Không phải đệ quy đuôi
  }
  ```
- **Truyền Tham Số:** Cần chú ý rằng các tham số cần được truyền đúng cách để đảm bảo tính chính xác của hàm.

### Các Ghi Chú Khác
- `tailrec` chỉ hoạt động với hàm có kiểu trả về đơn giản, không thể sử dụng với các hàm có kiểu trả về là `Unit` (tương tự `void` trong Java).
- Không phải tất cả các hàm đệ quy đều cần hoặc có thể sử dụng `tailrec`. Việc sử dụng nó chỉ nên được áp dụng khi cần thiết để tối ưu hóa hiệu suất.

## Tóm Tắt Một Dòng
`tailrec` là tính năng trong Kotlin cho phép tối ưu hóa hàm đệ quy đuôi, giúp ngăn ngừa lỗi tràn ngăn xếp và cải thiện hiệu suất.