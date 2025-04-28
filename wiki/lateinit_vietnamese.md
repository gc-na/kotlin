<!--
Meta Description: # Tìm Hiểu Về `lateinit` Trong Kotlin: Cách Khai Báo Biến Không Khởi Tạo Ngay Lập Tức ## Tóm Tắt `lateinit` là một từ khóa trong Kotlin cho phép bạn k...
Meta Keywords: biến, lateinit, dụng, không, khởi
-->

# Tìm Hiểu Về `lateinit` Trong Kotlin: Cách Khai Báo Biến Không Khởi Tạo Ngay Lập Tức

## Tóm Tắt
`lateinit` là một từ khóa trong Kotlin cho phép bạn khai báo các biến không cần khởi tạo ngay lập tức. Điều này hữu ích khi bạn muốn đảm bảo rằng một biến sẽ được khởi tạo sau này, nhưng không muốn sử dụng giá trị null.

## Tài Liệu
### Mục Đích
`lateinit` được sử dụng để khai báo các biến không thể null mà không cần khởi tạo giá trị ngay lập tức. Điều này thường được áp dụng cho các biến trong lớp mà sẽ được khởi tạo trong các hàm khác hoặc trong vòng đời của lớp.

### Cách Sử Dụng
Để sử dụng `lateinit`, bạn cần:
1. Khai báo biến với từ khóa `lateinit`.
2. Đảm bảo rằng biến đó là một biến không null (không được sử dụng với kiểu dữ liệu nguyên thủy như Int, Double, v.v.).
3. Khởi tạo biến trước khi sử dụng.

Cú pháp khai báo như sau:
```kotlin
lateinit var name: String
```

### Chi Tiết
- Biến `lateinit` chỉ có thể được sử dụng với loại tham chiếu (reference type), không thể dùng với kiểu dữ liệu nguyên thủy.
- Nếu bạn cố gắng truy cập một biến `lateinit` mà chưa được khởi tạo, sẽ dẫn đến một ngoại lệ `UninitializedPropertyAccessException`.
- Bạn có thể kiểm tra xem một biến `lateinit` đã được khởi tạo hay chưa bằng cách sử dụng phương thức `::propertyName.isInitialized`.

## Ví Dụ
### Ví Dụ Cơ Bản
```kotlin
class User {
    lateinit var name: String

    fun initializeName() {
        name = "John Doe"
    }

    fun printName() {
        if (::name.isInitialized) {
            println(name)
        } else {
            println("Name is not initialized")
        }
    }
}

fun main() {
    val user = User()
    user.printName() // In ra: Name is not initialized
    user.initializeName()
    user.printName() // In ra: John Doe
}
```

### Ví Dụ Với Kiểm Tra Khởi Tạo
```kotlin
class Product {
    lateinit var productName: String

    fun setupProduct() {
        productName = "Laptop"
    }
}

fun main() {
    val product = Product()
    
    // Kiểm tra trước khi truy cập
    if (::product.productName.isInitialized) {
        println(product.productName)
    } else {
        println("Product name is not initialized yet.")
    }
    
    product.setupProduct()
    
    // Bây giờ đã khởi tạo
    println(product.productName) // In ra: Laptop
}
```

## Giải Thích
### Những Lỗi Thường Gặp
- **Quên Khởi Tạo:** Nếu bạn không khởi tạo biến `lateinit` trước khi truy cập nó, bạn sẽ nhận được `UninitializedPropertyAccessException`. Đảm bảo rằng biến được khởi tạo trong mọi trường hợp trước khi sử dụng.
- **Sử Dụng Với Kiểu Dữ Liệu Nguyên Thủy:** Không thể sử dụng `lateinit` với các kiểu dữ liệu như Int, Double, hay Boolean. Cần phải sử dụng loại tham chiếu.

### Ghi Chú Thêm
- `lateinit` không thể được sử dụng với các thuộc tính trong lớp dữ liệu (data class).
- Nếu bạn muốn một biến có thể nhận giá trị null mà không cần sử dụng `lateinit`, bạn có thể sử dụng kiểu nullable (ví dụ: `var name: String?`).

## Tóm Tắt Một Dòng
`lateinit` trong Kotlin cho phép khai báo biến không null mà không cần khởi tạo ngay lập tức, giúp quản lý biến một cách linh hoạt hơn trong các lớp.