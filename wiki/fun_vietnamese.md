<!--
Meta Description: # Từ Khóa "fun" Trong Kotlin: Cách Định Nghĩa Hàm ## Tóm Tắt Từ khóa `fun` trong Kotlin được sử dụng để định nghĩa hàm, cho phép lập trình viên tạo ra...
Meta Keywords: hàm, kotlin, tham, fun, kiểu
-->

# Từ Khóa "fun" Trong Kotlin: Cách Định Nghĩa Hàm

## Tóm Tắt
Từ khóa `fun` trong Kotlin được sử dụng để định nghĩa hàm, cho phép lập trình viên tạo ra các hàm với cú pháp đơn giản và rõ ràng.

## Tài Liệu
### Mục Đích
Từ khóa `fun` là một phần cốt lõi trong ngôn ngữ lập trình Kotlin, giúp bạn định nghĩa các hàm một cách dễ dàng. Hàm trong Kotlin có thể nhận tham số và trả về giá trị, cho phép tái sử dụng mã và tổ chức logic của chương trình một cách hiệu quả.

### Cách Sử Dụng
Cú pháp cơ bản để định nghĩa một hàm trong Kotlin như sau:

```kotlin
fun tenHàm(thamSố1: Kiểu, thamSố2: Kiểu): KiểuKếtQuả {
    // Thân hàm
}
```

- `fun`: Từ khóa để bắt đầu định nghĩa hàm.
- `tenHàm`: Tên của hàm.
- `thamSố1`, `thamSố2`: Các tham số đầu vào của hàm, có thể có nhiều tham số hoặc không có tham số nào.
- `Kiểu`: Kiểu dữ liệu của tham số.
- `KiểuKếtQuả`: Kiểu dữ liệu mà hàm sẽ trả về, có thể bỏ qua nếu hàm không trả về giá trị.

### Ví Dụ
#### Ví dụ 1: Hàm không tham số và không trả về giá trị
```kotlin
fun inThongDiep() {
    println("Xin chào, Kotlin!")
}
```

#### Ví dụ 2: Hàm có tham số và trả về giá trị
```kotlin
fun cộng(a: Int, b: Int): Int {
    return a + b
}
```

#### Ví dụ 3: Hàm có tham số mặc định
```kotlin
fun chào(tên: String = "Thế giới") {
    println("Xin chào, $tên!")
}
```

## Giải Thích
### Những Lỗi Thường Gặp
1. **Quên từ khóa `fun`**: Nếu bạn quên không sử dụng từ khóa `fun`, trình biên dịch sẽ báo lỗi.
2. **Thiếu kiểu trả về**: Khi định nghĩa hàm mà không chỉ định kiểu trả về, Kotlin sẽ tự động cho rằng hàm đó có kiểu `Unit` (tương tự như `void` trong Java).
3. **Tham số không đúng kiểu**: Việc truyền tham số không đúng kiểu sẽ dẫn đến lỗi biên dịch.

### Ghi Chú Thêm
- Hàm trong Kotlin có thể được định nghĩa bên ngoài hoặc bên trong lớp (class).
- Bạn có thể sử dụng hàm cấp cao (higher-order functions) để truyền hàm như một tham số cho các hàm khác.

## Tóm Tắt Một Dòng
Từ khóa `fun` trong Kotlin là cú pháp dùng để định nghĩa hàm, cho phép lập trình viên tạo ra các hàm với tham số và kiểu trả về một cách dễ dàng và hiệu quả.