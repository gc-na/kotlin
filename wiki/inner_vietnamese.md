<!--
Meta Description: # Từ khóa "inner" trong Kotlin: Cách sử dụng và ý nghĩa ## Tóm tắt Từ khóa `inner` trong Kotlin được sử dụng để định nghĩa lớp bên trong (inner class)...
Meta Keywords: lớp, bên, trong, inner, một
-->

# Từ khóa "inner" trong Kotlin: Cách sử dụng và ý nghĩa

## Tóm tắt
Từ khóa `inner` trong Kotlin được sử dụng để định nghĩa lớp bên trong (inner class), cho phép lớp bên trong có thể truy cập vào các thuộc tính và phương thức của lớp bên ngoài. 

## Tài liệu
### Mục đích
Lớp bên trong (inner class) trong Kotlin giúp tổ chức mã nguồn tốt hơn và cho phép sử dụng các thuộc tính của lớp bên ngoài một cách dễ dàng.

### Cách sử dụng
Để định nghĩa một lớp bên trong, bạn sử dụng từ khóa `inner` trước từ khóa `class`. Khi lớp bên trong được tạo ra, nó sẽ có một tham chiếu đến một thể hiện của lớp bên ngoài.

### Chi tiết
- **Định nghĩa**: Một lớp bên trong được khai báo bên trong một lớp khác và có thể truy cập các thuộc tính và phương thức của lớp ngoài.
- **Cú pháp**:
  ```kotlin
  class Outer {
      private val outerProperty = "Outer Property"

      inner class Inner {
          fun accessOuter() {
              println(outerProperty) // Truy cập thuộc tính của lớp bên ngoài
          }
      }
  }
  ```
- **Tạo thể hiện**: Để tạo một thể hiện của lớp bên trong, bạn cần phải có một thể hiện của lớp bên ngoài:
  ```kotlin
  val outer = Outer()
  val inner = outer.Inner()
  inner.accessOuter() // In ra: Outer Property
  ```

## Ví dụ
```kotlin
class Car(val name: String) {
    inner class Engine(val type: String) {
        fun engineInfo() {
            println("Car: $name, Engine type: $type")
        }
    }
}

fun main() {
    val myCar = Car("Toyota")
    val myEngine = myCar.Engine("V6")
    myEngine.engineInfo() // In ra: Car: Toyota, Engine type: V6
}
```

## Giải thích
### Những cạm bẫy thường gặp
- **Quá tải**: Nếu không cần thiết phải truy cập thuộc tính của lớp bên ngoài, bạn nên xem xét việc sử dụng lớp tĩnh (static) để tránh tạo ra sự phụ thuộc không cần thiết.
- **Hiệu suất**: Lớp bên trong tạo ra một tham chiếu đến lớp bên ngoài, điều này có thể dẫn đến việc tiêu tốn bộ nhớ nếu không được quản lý đúng cách.

## Tóm tắt một dòng
Từ khóa `inner` trong Kotlin cho phép lớp bên trong truy cập vào các thuộc tính và phương thức của lớp bên ngoài, giúp tổ chức mã nguồn hiệu quả hơn.