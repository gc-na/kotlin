<!--
Meta Description: # الاستخدامات المتقدمة لـ "Companion" في كوتلن ## ملخص تعتبر خاصية "Companion Object" في لغة كوتلن أداة قوية تُستخدم لإنشاء كائنات مرتبطة بالفئة (clas...
Meta Keywords: companion, object, يمكن, myclass, user
-->

# الاستخدامات المتقدمة لـ "Companion" في كوتلن

## ملخص
تعتبر خاصية "Companion Object" في لغة كوتلن أداة قوية تُستخدم لإنشاء كائنات مرتبطة بالفئة (class) بحيث يمكن الوصول إليها دون الحاجة لإنشاء مثيل (instance) من الفئة.

## الوثائق
تم تصميم "Companion Object" لتوفير سلوك مشابه لما يُعرف بـ "static members" في لغات البرمجة الأخرى. يُستخدم الكائن المرافق لتخزين العناصر الثابتة أو الوظائف التي تتعلق بالفئة نفسها بدلاً من مثيل محدد.

### الغرض
- يوفر طريقة للوصول إلى الأعضاء الثابتة للفئة.
- يمكن أن يحتوي على وظائف ومتحولات ثابتة.
- يُستخدم في تطبيقات متعددة مثل أنماط التصميم، والتحقق من القيم الفريدة.

### الاستخدام
يمكن تعريف "Companion Object" داخل الفئة باستخدام الكلمة الرئيسية `companion object`. يمكن أن يحتوي على متغيرات أو دوال ثابتة. إليك مثال على كيفية تعريفه:

```kotlin
class MyClass {
    companion object {
        const val CONSTANT_VALUE = 42
        
        fun create(): MyClass {
            return MyClass()
        }
    }
}
```

يمكنك الوصول إلى العناصر الموجودة في "Companion Object" باستخدام اسم الفئة مباشرة:

```kotlin
fun main() {
    println(MyClass.CONSTANT_VALUE) // يطبع: 42
    val instance = MyClass.create() // ينشئ مثيل جديد من MyClass
}
```

## الأمثلة
### مثال 1: تعريف متغير ثابت
```kotlin
class Circle {
    companion object {
        const val PI = 3.14
    }
}

fun main() {
    println(Circle.PI) // يطبع: 3.14
}
```

### مثال 2: دالة لإنشاء مثيل
```kotlin
class User(val name: String) {
    companion object {
        fun createUser(name: String): User {
            return User(name)
        }
    }
}

fun main() {
    val user = User.createUser("Ali")
    println(user.name) // يطبع: Ali
}
```

## الشرح
### المخاطر الشائعة والملاحظات
- "Companion Objects" ليست ثابتة تمامًا مثل "static members" في Java، حيث يمكن أن تحتوي على منطق برمجي. 
- يمكن أن تُستخدم عدة "Companion Objects" داخل فئة واحدة، ولكن من الأفضل الحفاظ على واحد فقط لأغراض الوضوح.
- يجب الانتباه إلى أن "Companion Object" يمكن أن يعيد استخدام الأسماء، لذا من المهم تسمية العناصر داخلها بشكل واضح لتفادي التداخل.

## ملخص بسط
"Companion Object" في كوتلن يوفر وسيلة لإنشاء أعضاء ثابتة ترتبط بفئة معينة، مما يسهل الوصول إليها دون الحاجة لإنشاء مثيل.