<!--
Meta Description: # Câu Lệnh "break" Trong Kotlin: Cách Dừng Vòng Lặp Một Cách Hiệu Quả ## Tóm Tắt Câu lệnh `break` trong Kotlin được sử dụng để thoát khỏi vòng lặp một...
Meta Keywords: vòng, lặp, break, một, trong
-->

# Câu Lệnh "break" Trong Kotlin: Cách Dừng Vòng Lặp Một Cách Hiệu Quả

## Tóm Tắt
Câu lệnh `break` trong Kotlin được sử dụng để thoát khỏi vòng lặp một cách nhanh chóng, giúp kiểm soát luồng chương trình một cách dễ dàng.

## Tài Liệu
Câu lệnh `break` trong Kotlin cho phép bạn dừng một vòng lặp (bao gồm vòng lặp `for`, `while`, và `do...while`) ngay khi điều kiện được xác định là đúng. Khi `break` được thực thi, chương trình sẽ tiếp tục thực hiện các câu lệnh ngay sau vòng lặp đó.

### Cú Pháp
```kotlin
break
```

### Mục Đích
- Dừng vòng lặp khi một điều kiện cụ thể được thỏa mãn.
- Tăng tính linh hoạt và điều khiển luồng chương trình.

### Cách Sử Dụng
Câu lệnh `break` có thể được sử dụng trong bất kỳ vòng lặp nào. Nó thường được kết hợp với các câu lệnh điều kiện như `if` để quyết định khi nào thì nên thoát khỏi vòng lặp.

## Ví Dụ
### Ví Dụ Cơ Bản 1: Sử Dụng Trong Vòng Lặp `for`
```kotlin
for (i in 1..10) {
    if (i == 5) {
        break
    }
    println(i)
}
```
**Kết quả:**  
1  
2  
3  
4  

### Ví Dụ Cơ Bản 2: Sử Dụng Trong Vòng Lặp `while`
```kotlin
var count = 1
while (count <= 10) {
    if (count == 7) {
        break
    }
    println(count)
    count++
}
```
**Kết quả:**  
1  
2  
3  
4  
5  
6  

## Giải Thích
Một số điểm cần lưu ý khi sử dụng `break`:
- `break` chỉ thoát ra khỏi vòng lặp gần nhất mà nó được gọi, không ảnh hưởng đến các vòng lặp bên ngoài.
- Nếu sử dụng `break` trong một vòng lặp lồng nhau, nó chỉ dừng vòng lặp đang chạy mà không ảnh hưởng đến vòng lặp bên ngoài.
- Nên cẩn thận khi sử dụng `break`, vì việc dừng vòng lặp quá sớm có thể dẫn đến việc bỏ lỡ các giá trị quan trọng.

## Tóm Tắt Một Dòng
Câu lệnh `break` trong Kotlin cho phép người lập trình dừng vòng lặp một cách hiệu quả khi một điều kiện cụ thể được thỏa mãn.