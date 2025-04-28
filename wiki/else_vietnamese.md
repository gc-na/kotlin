<!--
Meta Description: # Câu lệnh "else" trong Kotlin: Cách sử dụng và ví dụ ## Tóm tắt Câu lệnh "else" trong Kotlin là một phần quan trọng của cấu trúc điều kiện, cho phép ...
Meta Keywords: lệnh, else, câu, trong, điều
-->

# Câu lệnh "else" trong Kotlin: Cách sử dụng và ví dụ

## Tóm tắt
Câu lệnh "else" trong Kotlin là một phần quan trọng của cấu trúc điều kiện, cho phép lập trình viên xử lý các trường hợp khi điều kiện trước đó không được thỏa mãn.

## Tài liệu
Câu lệnh "else" trong Kotlin được sử dụng để xác định khối lệnh sẽ được thực thi khi điều kiện trong câu lệnh "if" là sai. Nó giúp tạo ra các nhánh logic trong mã nguồn, cho phép lập trình viên kiểm soát luồng thực thi của chương trình. Cú pháp cơ bản của câu lệnh "else" như sau:

```kotlin
if (điều_kiện) {
    // khối lệnh khi điều kiện đúng
} else {
    // khối lệnh khi điều kiện sai
}
```

### Sử dụng
Câu lệnh "else" thường được sử dụng kèm với câu lệnh "if" để xử lý các tình huống khác nhau trong chương trình. Có thể kết hợp nhiều câu lệnh "if" và "else" để tạo ra cấu trúc điều kiện phức tạp hơn.

### Chi tiết
- Nếu điều kiện trong câu lệnh "if" là đúng (true), khối lệnh trong "if" sẽ được thực thi và khối lệnh trong "else" sẽ bị bỏ qua.
- Nếu điều kiện là sai (false), khối lệnh trong "else" sẽ được thực thi.
- Có thể sử dụng "else if" để kiểm tra nhiều điều kiện khác nhau trước khi đi đến câu lệnh "else".

## Ví dụ
### Ví dụ cơ bản
```kotlin
fun main() {
    val điểm = 75

    if (điểm >= 80) {
        println("Xuất sắc")
    } else {
        println("Cần cải thiện")
    }
}
```
Kết quả của đoạn mã trên sẽ là: `Cần cải thiện`.

### Ví dụ với "else if"
```kotlin
fun main() {
    val điểm = 65

    if (điểm >= 80) {
        println("Xuất sắc")
    } else if (điểm >= 70) {
        println("Khá")
    } else {
        println("Cần cải thiện")
    }
}
```
Kết quả sẽ là: `Cần cải thiện`.

## Giải thích
Một số điểm cần lưu ý khi sử dụng câu lệnh "else":
- Câu lệnh "else" luôn phải đi kèm với câu lệnh "if" và không thể đứng một mình.
- Không thể có nhiều câu lệnh "else" trong cùng một cấu trúc điều kiện; nếu cần kiểm tra nhiều trường hợp, sử dụng "else if".
- Câu lệnh "else" không yêu cầu điều kiện, nó sẽ được thực hiện khi tất cả các điều kiện trước đó đều không thỏa mãn.

## Tóm tắt một dòng
Câu lệnh "else" trong Kotlin cho phép xử lý các trường hợp khi điều kiện trong câu lệnh "if" là sai, giúp kiểm soát luồng thực thi trong chương trình.