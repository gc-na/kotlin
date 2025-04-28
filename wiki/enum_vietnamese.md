<!--
Meta Description: # Enum trong Kotlin: Lập Trình Hướng Đối Tượng ## Tóm tắt Enum (Enumerations) trong Kotlin là một kiểu dữ liệu đặc biệt cho phép định nghĩa một tập hợ...
Meta Keywords: enum, một, trong, định, nghĩa
-->

# Enum trong Kotlin: Lập Trình Hướng Đối Tượng

## Tóm tắt
Enum (Enumerations) trong Kotlin là một kiểu dữ liệu đặc biệt cho phép định nghĩa một tập hợp các hằng số có liên quan. Enum giúp cải thiện tính rõ ràng và an toàn của mã nguồn khi làm việc với các giá trị cố định.

## Tài Liệu
Enum trong Kotlin cho phép lập trình viên định nghĩa một loại dữ liệu riêng biệt với một tập hợp các hằng số. Mỗi giá trị trong enum là một đối tượng duy nhất của lớp enum đó. Bạn có thể định nghĩa các thuộc tính và phương thức cho enum giống như với các lớp thông thường.

### Cú pháp
Để định nghĩa một enum, bạn sử dụng từ khóa `enum class`, theo sau là tên của enum và danh sách các hằng số. Dưới đây là cú pháp cơ bản:

```kotlin
enum class TênEnum {
    HằngSố1,
    HằngSố2,
    HằngSố3
}
```

### Ví dụ
Dưới đây là ví dụ về việc sử dụng enum trong Kotlin:

```kotlin
enum class Màu {
    ĐỎ,
    XANH,
    VÀNG
}

fun main() {
    val màuYêuThích = Màu.XANH
    println("Màu yêu thích của tôi là: $màuYêuThích")
}
```

Trong ví dụ trên, chúng ta định nghĩa một enum mang tên `Màu` với ba hằng số: ĐỎ, XANH và VÀNG. Chúng ta sau đó sử dụng enum này để lưu trữ và in ra màu yêu thích.

## Giải Thích
Khi sử dụng enum, bạn cần lưu ý một số điểm sau:

1. **Giá trị duy nhất**: Mỗi hằng số trong enum là một đối tượng duy nhất. Điều này có nghĩa là bạn không thể định nghĩa hai hằng số có giá trị giống nhau trong cùng một enum.
  
2. **Có thể có thuộc tính và phương thức**: Enum không chỉ là những hằng số đơn giản; bạn có thể thêm thuộc tính và phương thức vào enum. Ví dụ:

   ```kotlin
   enum class Ngày(val sốThứTự: Int) {
       THỨ_HAI(1),
       THỨ_BA(2),
       THỨ_TƯ(3)
   }
   ```

3. **So sánh**: Bạn có thể so sánh các hằng số enum bằng toán tử `==`, vì chúng được định nghĩa là các đối tượng duy nhất.

## Tóm tắt một dòng
Enum trong Kotlin cho phép định nghĩa tập hợp các hằng số có liên quan, giúp mã nguồn an toàn và rõ ràng hơn.