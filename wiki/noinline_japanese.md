<!--
Meta Description: # Kotlinのnoinlineキーワードの使い方と特徴 ## 概要 Kotlinの`noinline`は、高階関数のラムダ式を非インライン化するための修飾子です。これにより、特定のラムダ式をインライン化せず、通常の関数呼び出しとして扱うことができます。 ## ドキュメント `noinline`は...
Meta Keywords: noinline, inlined, unit, notinlined, println
-->

# Kotlinのnoinlineキーワードの使い方と特徴

## 概要
Kotlinの`noinline`は、高階関数のラムダ式を非インライン化するための修飾子です。これにより、特定のラムダ式をインライン化せず、通常の関数呼び出しとして扱うことができます。

## ドキュメント
`noinline`は、Kotlinにおける高階関数でラムダ式を引数として受け取る際に使用されます。デフォルトでは、Kotlinはラムダ式をインライン化してパフォーマンスを向上させようとしますが、特定のケースではインライン化が望ましくない場合があります。例えば、ラムダ式が再利用されたり、デフォルト引数を持つ場合、インライン化を避ける必要があります。

### 目的
- ラムダ式のインライン化を防ぎ、オブジェクトとして保持する。
- 再利用やクロージャの管理が必要な場合に便利。

### 使用法
以下のように、関数の引数に`noinline`を指定することで、そのラムダ式をインライン化しないように指定できます。

```kotlin
inline fun higherOrderFunction(inlined: () -> Unit, noinline notInlined: () -> Unit) {
    inlined() // これはインライン化される
    notInlined() // これはインライン化されない
}
```

## 例
以下は、`noinline`を使用した基本的な例です。

```kotlin
inline fun performAction(inlined: () -> Unit, noinline notInlined: () -> Unit) {
    println("Before inlined action")
    inlined()
    println("Before not inlined action")
    notInlined()
}

fun main() {
    performAction({
        println("This is inlined")
    }, {
        println("This is not inlined")
    })
}
```

この例では、`performAction`関数は2つのラムダ式を受け取ります。一方はインライン化され、もう一方は通常の関数呼び出しとして扱われます。

## 説明
`noinline`を使用する際の注意点として、以下の点が挙げられます：

- **性能の低下**: ラムダ式を非インライン化することで、性能が低下する場合があります。特に、頻繁に呼び出される関数では影響が顕著になります。
- **クロージャの取り扱い**: オブジェクトとして保持されるため、クロージャの状態を管理する方法に注意が必要です。
- **再利用の必要性**: ラムダ式が再利用される場合、`noinline`を用いることで、意図した通りにラムダを使うことができます。

## 一文要約
Kotlinの`noinline`は、高階関数内で特定のラムダ式をインライン化せずに通常の関数呼び出しとして扱うための修飾子です。