<!--
Meta Description: # Từ Khóa "protected" Trong Kotlin: Cách Sử Dụng và Ý Nghĩa ## Tóm tắt Từ khóa `protected` trong Kotlin được sử dụng để kiểm soát quyền truy cập của c...
Meta Keywords: protected, lớp, truy, cập, các
-->

# Từ Khóa "protected" Trong Kotlin: Cách Sử Dụng và Ý Nghĩa

## Tóm tắt
Từ khóa `protected` trong Kotlin được sử dụng để kiểm soát quyền truy cập của các thành viên trong lớp, cho phép truy cập từ lớp con nhưng không cho phép truy cập bên ngoài.

## Tài liệu
Từ khóa `protected` trong Kotlin xác định mức độ truy cập cho các thuộc tính và phương thức trong lớp. Khi một thành viên được khai báo là `protected`, nó có thể được truy cập từ lớp chính nó và tất cả các lớp con của nó, nhưng không thể được truy cập từ bên ngoài lớp.

### Mục đích
Mục đích chính của `protected` là để bảo vệ các thành viên của lớp, chỉ cho phép các lớp kế thừa truy cập mà không cho phép các đối tượng bên ngoài lớp truy cập trực tiếp vào chúng.

### Cách sử dụng
Để khai báo một thuộc tính hoặc phương thức là `protected`, bạn chỉ cần thêm từ khóa `protected` trước khai báo của thuộc tính hoặc phương thức đó. Ví dụ:

```kotlin
open class Parent {
    protected val secret: String = "This is protected"
    
    protected fun showSecret() {
        println(secret)
    }
}

class Child : Parent() {
    fun revealSecret() {
        showSecret() // Có thể gọi phương thức protected
    }
}
```

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng `protected` trong Kotlin:

```kotlin
open class Animal {
    protected fun makeSound() {
        println("Animal sound")
    }
}

class Dog : Animal() {
    fun bark() {
        makeSound() // Có thể gọi phương thức protected từ lớp cha
        println("Woof!")
    }
}

fun main() {
    val dog = Dog()
    dog.bark() // In ra "Animal sound" và "Woof!"
    // dog.makeSound() // Lỗi: makeSound() có độ truy cập protected
}
```

## Giải thích
Khi sử dụng `protected`, bạn cần lưu ý một số điểm sau:

1. **Khả năng truy cập**: Chỉ có lớp hiện tại và các lớp con mới có thể truy cập thành viên `protected`. Điều này có thể gây nhầm lẫn nếu bạn cố gắng gọi một thành viên `protected` từ một đối tượng của lớp cha.

2. **Không thể truy cập từ bên ngoài**: Các đối tượng từ lớp cha không thể truy cập trực tiếp vào các thành viên `protected`. Điều này có thể dẫn đến lỗi biên dịch nếu không được hiểu rõ.

3. **Khác biệt với `private`**: Khác với `private`, từ khóa `protected` cho phép các lớp con tiếp cận thành viên, trong khi `private` hoàn toàn giới hạn quyền truy cập cho lớp cha.

## Tóm tắt một dòng
Từ khóa `protected` trong Kotlin cho phép các thành viên của lớp được truy cập từ các lớp con, nhưng không từ bên ngoài lớp, nhằm bảo vệ dữ liệu và phương thức của lớp.