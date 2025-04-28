<!--
Meta Description: # Từ Khóa "external" trong Kotlin: Định Nghĩa và Cách Sử Dụng ## Tóm Tắt Từ khóa "external" trong Kotlin được sử dụng để khai báo các hàm hoặc thuộc t...
Meta Keywords: kotlin, external, trong, hàm, định
-->

# Từ Khóa "external" trong Kotlin: Định Nghĩa và Cách Sử Dụng

## Tóm Tắt
Từ khóa "external" trong Kotlin được sử dụng để khai báo các hàm hoặc thuộc tính mà được định nghĩa bên ngoài mã nguồn của ứng dụng, thường là trong thư viện C hoặc C++. Điều này cho phép Kotlin giao tiếp với mã nguồn C/C++ một cách dễ dàng.

## Tài Liệu
### Mục Đích
Từ khóa "external" cho phép lập trình viên Kotlin kết nối với mã nguồn bên ngoài, giúp tận dụng các thư viện đã có hoặc thực hiện các thao tác mà Kotlin không hỗ trợ trực tiếp.

### Cách Sử Dụng
Khi khai báo một hàm hoặc thuộc tính với từ khóa "external", bạn cần chỉ định rằng nó không có thân hàm trong Kotlin. Thay vào đó, thân hàm sẽ được định nghĩa trong mã bên ngoài. 

#### Cú Pháp
```kotlin
external fun functionName(param: Type): ReturnType
```

### Chi Tiết
- **Hàm**: Khi bạn khai báo một hàm là "external", bạn cần đảm bảo rằng hàm này đã được định nghĩa trong mã C/C++ mà bạn đang liên kết.
- **Thuộc Tính**: Tương tự như hàm, các thuộc tính "external" cũng không có thân trong Kotlin và cần được định nghĩa bên ngoài.
- **Liên Kết**: Để sử dụng các hàm hoặc thuộc tính "external", bạn cần phải cấu hình liên kết với mã C/C++ thông qua Gradle hoặc công cụ build khác.

## Ví Dụ
### Ví Dụ 1: Khai Báo Hàm External
```kotlin
external fun nativeFunction(param: Int): String
```

### Ví Dụ 2: Khai Báo Thuộc Tính External
```kotlin
external var nativeProperty: Int
```

## Giải Thích
### Cạm Bẫy Thường Gặp
- **Thiếu Định Nghĩa**: Nếu bạn không định nghĩa hàm hoặc thuộc tính trong mã C/C++, khi gọi chúng trong Kotlin sẽ gây ra lỗi biên dịch.
- **Quản lý bộ nhớ**: Khi làm việc với mã C/C++, bạn cần cẩn thận với việc quản lý bộ nhớ vì Kotlin không tự động quản lý bộ nhớ cho các đối tượng từ mã C/C+.
- **Tính tương thích**: Đảm bảo rằng kiểu dữ liệu được sử dụng trong Kotlin tương thích với kiểu dữ liệu trong C/C++ để tránh lỗi runtime.

## Tóm Tắt Một Câu
Từ khóa "external" trong Kotlin cho phép khai báo các hàm và thuộc tính được định nghĩa bên ngoài, giúp kết nối dễ dàng với mã C/C++.