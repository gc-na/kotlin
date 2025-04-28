<!--
Meta Description: # Sử Dụng "val" Trong Kotlin: Khai Báo Biến Không Thay Đổi ## Tóm Tắt "val" là từ khóa trong Kotlin được sử dụng để khai báo biến không thay đổi, tức ...
Meta Keywords: val, biến, kotlin, không, báo
-->

# Sử Dụng "val" Trong Kotlin: Khai Báo Biến Không Thay Đổi

## Tóm Tắt
"val" là từ khóa trong Kotlin được sử dụng để khai báo biến không thay đổi, tức là biến có giá trị chỉ được gán một lần và không thể thay đổi sau khi đã được khởi tạo.

## Tài Liệu
Trong Kotlin, "val" (viết tắt của "value") cho phép lập trình viên khai báo một biến mà không cần phải lo lắng về việc thay đổi giá trị của nó sau này. Khi một biến được khai báo với "val", giá trị của nó sẽ được cố định tại thời điểm khởi tạo và không thể gán lại bất kỳ giá trị nào khác.

### Mục Đích
- **Bảo mật và ổn định:** Việc sử dụng "val" giúp đảm bảo rằng giá trị của biến không bị thay đổi, giúp bảo vệ tính toàn vẹn của dữ liệu trong chương trình.
- **Tối ưu hóa hiệu suất:** Các biến "val" có thể được tối ưu hóa tốt hơn bởi trình biên dịch vì biết rằng chúng không thay đổi.

### Cách Sử Dụng
Để khai báo một biến với "val", bạn chỉ cần sử dụng cú pháp sau:

```kotlin
val tenBien: Kiểu = GiáTrị
```

Trong đó:
- `tenBien` là tên của biến.
- `Kiểu` là kiểu dữ liệu (có thể được bỏ qua nếu sử dụng loại suy diễn).
- `GiáTrị` là giá trị ban đầu được gán cho biến.

## Ví Dụ
### Ví Dụ Cơ Bản
Khai báo một biến "val" trong Kotlin:

```kotlin
val soNguyen: Int = 10
val ten: String = "Kotlin"
```

### Ví Dụ Với Loại Suy Diễn
Kotlin cho phép loại suy diễn kiểu dữ liệu:

```kotlin
val soThuc = 3.14
val danhSach = listOf(1, 2, 3)
```

## Giải Thích
Khi sử dụng "val", có một số điều cần lưu ý:
- **Không thể gán lại:** Nếu bạn cố gắng gán một giá trị mới cho biến đã khai báo bằng "val", trình biên dịch sẽ báo lỗi. Ví dụ:

```kotlin
val soNguyen = 5
soNguyen = 10 // Lỗi biên dịch: Không thể gán lại cho 'soNguyen'
```

- **Biến tham chiếu:** Nếu biến "val" tham chiếu đến một đối tượng (như danh sách hay đối tượng tùy chỉnh), bạn vẫn có thể thay đổi nội dung của đối tượng đó, nhưng không thể thay đổi biến tham chiếu.

```kotlin
val danhSach = mutableListOf(1, 2, 3)
danhSach.add(4) // Hợp lệ
// danhSach = mutableListOf(5, 6, 7) // Lỗi biên dịch
```

## Tóm Tắt Một Dòng
"val" trong Kotlin là từ khóa dùng để khai báo biến không thay đổi, giúp bảo vệ tính toàn vẹn của dữ liệu trong lập trình.