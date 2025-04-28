<!--
Meta Description: # Kotlinの「return」文：基本と活用法 ## 概要 Kotlinにおける「return」文は、関数の実行を終了し、指定した値を呼び出し元に返すための重要な構文です。この機能は、プログラムの制御フローを管理する上で不可欠です。 ## ドキュメンテーション 「return」文は、Kotlin...
Meta Keywords: return, int, fun, kotlin, println
-->

# Kotlinの「return」文：基本と活用法

## 概要
Kotlinにおける「return」文は、関数の実行を終了し、指定した値を呼び出し元に返すための重要な構文です。この機能は、プログラムの制御フローを管理する上で不可欠です。

## ドキュメンテーション
「return」文は、Kotlinの関数内で使用され、関数から値を返すために使われます。関数が実行されると、return文に到達した時点で実行が終了し、指定した値が呼び出し元のコードに戻されます。

### 使用目的
- 関数からの結果を返す。
- 条件に応じて早期に関数を終了させる。

### 詳細
Kotlinでは、関数は戻り値の型を指定する必要があります。戻り値の型は、関数の定義時に指定し、return文で返す値もこの型と一致しなければなりません。

```kotlin
fun sum(a: Int, b: Int): Int {
    return a + b
}
```

上記の例では、関数`sum`は二つの整数を受け取り、その合計を返します。戻り値の型は`Int`として指定されています。

## 例
### 基本的な使用例
```kotlin
fun multiply(x: Int, y: Int): Int {
    return x * y
}

fun main() {
    val result = multiply(3, 4)
    println(result)  // 出力: 12
}
```

### 条件による早期リターン
```kotlin
fun checkPositive(number: Int): String {
    if (number < 0) return "負の数です"
    return "正の数です"
}

fun main() {
    println(checkPositive(-5))  // 出力: 負の数です
    println(checkPositive(10))   // 出力: 正の数です
}
```

## 説明
「return」文を使用する際の一般的な注意点や落とし穴には、以下のようなものがあります。

- **戻り値の型の不一致**: return文で返す値の型は、関数の戻り値と一致している必要があります。型が異なる場合、コンパイルエラーが発生します。
  
- **中断とその後の処理**: return文が実行されると、関数の残りの部分は実行されません。これは、条件によって異なる処理を行いたい場合には注意が必要です。

- **ラムダ式におけるreturn**: ラムダ式内でreturnを使用する場合、呼び出し元の関数に対するreturnと区別するために、`return@label`を使用することがあります。

## 一文要約
Kotlinの「return」文は、関数から値を返し、実行を終了させるための基本的な構文です。