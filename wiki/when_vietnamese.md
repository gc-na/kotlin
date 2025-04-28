<!--
Meta Description: # Khi nào sử dụng lệnh "when" trong Kotlin: Hướng dẫn chi tiết ## Tóm Tắt Lệnh "when" trong Kotlin là một cấu trúc điều kiện mạnh mẽ cho phép kiểm tra...
Meta Keywords: lệnh, when, điều, kiện, println
-->

# Khi nào sử dụng lệnh "when" trong Kotlin: Hướng dẫn chi tiết

## Tóm Tắt
Lệnh "when" trong Kotlin là một cấu trúc điều kiện mạnh mẽ cho phép kiểm tra nhiều điều kiện cùng một lúc và thực hiện các hành động tương ứng. Nó có thể được coi là một cách thay thế cho câu lệnh "switch" trong các ngôn ngữ lập trình khác.

## Tài Liệu
Lệnh "when" được sử dụng để kiểm tra giá trị của một biểu thức và thực hiện các nhánh khác nhau dựa trên giá trị đó. Cú pháp của lệnh "when" rất linh hoạt và có thể sử dụng với nhiều loại điều kiện khác nhau.

### Cú pháp cơ bản
```kotlin
when (biểu_thức) {
    giá_trị_1 -> hành_động_1
    giá_trị_2 -> hành_động_2
    else -> hành_động_mặc_định
}
```

### Mục đích
Lệnh "when" giúp cải thiện tính rõ ràng và dễ đọc của mã nguồn so với nhiều câu lệnh điều kiện lồng nhau. Nó cho phép bạn xử lý nhiều trường hợp mà không cần viết nhiều câu lệnh "if".

### Sử dụng
- **Kiểm tra giá trị cụ thể**: Có thể so sánh trực tiếp với các giá trị.
- **Kiểm tra điều kiện**: Có thể sử dụng các điều kiện phức tạp hơn.
- **Làm việc với kiểu dữ liệu khác nhau**: Hỗ trợ kiểu dữ liệu khác nhau như Int, String, hay các kiểu dữ liệu tùy chỉnh.

## Ví Dụ
### Ví dụ 1: Kiểm tra giá trị
```kotlin
val số = 2
when (số) {
    1 -> println("Một")
    2 -> println("Hai")
    3 -> println("Ba")
    else -> println("Khác")
}
```

### Ví dụ 2: Sử dụng điều kiện
```kotlin
val điểm = 85
when {
    điểm >= 90 -> println("Xuất sắc")
    điểm >= 75 -> println("Giỏi")
    điểm >= 60 -> println("Khá")
    else -> println("Yếu")
}
```

### Ví dụ 3: Kiểm tra nhiều giá trị
```kotlin
val màu = "Đỏ"
when (màu) {
    "Đỏ", "Xanh" -> println("Màu nóng")
    "Xanh lá" -> println("Màu lạnh")
    else -> println("Màu khác")
}
```

## Giải Thích
- **Cách sử dụng lệnh "when"**: Khi sử dụng "when", đảm bảo rằng bạn đã kiểm tra đầy đủ các nhánh có thể xảy ra để tránh trường hợp không xử lý được.
- **Nhầm lẫn với lệnh "if"**: Mặc dù cả hai đều là các cấu trúc điều kiện, "when" thường dễ đọc hơn khi có nhiều điều kiện.
- **Chạy nhiều câu lệnh**: Bạn có thể chạy nhiều câu lệnh trong một nhánh bằng cách sử dụng dấu ngoặc nhọn `{}`.

## Tóm Tắt Một Dòng
Lệnh "when" trong Kotlin là một cấu trúc điều kiện linh hoạt và dễ đọc, cho phép kiểm tra nhiều giá trị và điều kiện khác nhau trong một khối mã duy nhất.