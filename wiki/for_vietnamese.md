<!--
Meta Description: # Câu lệnh "for" trong Kotlin: Cách Sử Dụng và Ví Dụ Cơ Bản ## Tóm tắt Câu lệnh "for" trong Kotlin cho phép lặp qua các phần tử trong một tập hợp hoặc...
Meta Keywords: lặp, qua, một, kotlin, các
-->

# Câu lệnh "for" trong Kotlin: Cách Sử Dụng và Ví Dụ Cơ Bản

## Tóm tắt
Câu lệnh "for" trong Kotlin cho phép lặp qua các phần tử trong một tập hợp hoặc một dãy số, giúp lập trình viên dễ dàng thực hiện các thao tác lặp mà không cần phải quản lý chỉ số như trong một số ngôn ngữ lập trình khác.

## Tài liệu
Câu lệnh "for" trong Kotlin là một công cụ mạnh mẽ để lặp qua các phần tử của các kiểu dữ liệu như mảng, danh sách, và tập hợp. Cú pháp cơ bản của câu lệnh "for" là:

```kotlin
for (item in collection) {
    // Thực hiện một số thao tác với item
}
```

### Mục đích
Câu lệnh "for" giúp lập trình viên:
- Lặp qua từng phần tử trong một cấu trúc dữ liệu.
- Thực hiện các thao tác một cách dễ dàng và hiệu quả.

### Cách sử dụng
- **Lặp qua mảng**: Bạn có thể sử dụng câu lệnh "for" để lặp qua từng phần tử trong một mảng.
- **Lặp qua danh sách**: Tương tự, bạn có thể lặp qua từng phần tử trong một danh sách.
- **Lặp qua dãy số**: Kotlin hỗ trợ lặp qua một dãy số bằng cách sử dụng hàm `range`.

## Ví dụ
### Ví dụ 1: Lặp qua mảng
```kotlin
val numbers = arrayOf(1, 2, 3, 4, 5)
for (number in numbers) {
    println(number)
}
```

### Ví dụ 2: Lặp qua danh sách
```kotlin
val fruits = listOf("Táo", "Cam", "Chuối")
for (fruit in fruits) {
    println(fruit)
}
```

### Ví dụ 3: Lặp qua dãy số
```kotlin
for (i in 1..5) {
    println(i)
}
```

### Ví dụ 4: Lặp ngược
```kotlin
for (i in 5 downTo 1) {
    println(i)
}
```

## Giải thích
Một số điểm cần lưu ý khi sử dụng câu lệnh "for":
- **Không kiểm soát chỉ số**: Khác với một số ngôn ngữ như C hay Java, Kotlin không yêu cầu bạn phải quản lý chỉ số khi lặp qua các phần tử.
- **Tính linh hoạt**: Bạn có thể lặp qua các dãy số với các bước cụ thể, ví dụ `for (i in 1..10 step 2)`.
- **Tính an toàn**: Khi lặp qua các cấu trúc dữ liệu, Kotlin tự động xử lý các trường hợp như rỗng mà không gây ra lỗi.

## Tóm tắt một câu
Câu lệnh "for" trong Kotlin cho phép bạn lặp qua các phần tử của tập hợp một cách đơn giản và hiệu quả.