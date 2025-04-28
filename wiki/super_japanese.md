<!--
Meta Description: # Kotlinにおける「super」キーワードの使い方 ## 概要 Kotlinの「super」キーワードは、親クラスのメンバー（プロパティやメソッド）にアクセスするために使用されます。このキーワードは、オブジェクト指向プログラミングにおける継承機能を利用する際に非常に重要です。 ## ドキュメン...
Meta Keywords: super, fun, greet, println, sound
-->

# Kotlinにおける「super」キーワードの使い方

## 概要
Kotlinの「super」キーワードは、親クラスのメンバー（プロパティやメソッド）にアクセスするために使用されます。このキーワードは、オブジェクト指向プログラミングにおける継承機能を利用する際に非常に重要です。

## ドキュメント
「super」キーワードは、クラスの継承関係において親クラスの機能を利用するための手段を提供します。Kotlinでは、クラスが他のクラスを継承する際に、親クラスのメンバーを呼び出す必要がある場合に「super」を使用します。

### 使用目的
- 親クラスのメソッドをオーバーライドする際に、元の実装を呼び出す。
- プロパティやメソッドが親クラスから継承されている場合にアクセスする。

### 使用方法
親クラスのメソッドやプロパティを参照するには、次のように「super」を使用します。

```kotlin
open class Parent {
    open fun greet() {
        println("Hello from Parent")
    }
}

class Child : Parent() {
    override fun greet() {
        super.greet() // 親クラスのメソッドを呼び出す
        println("Hello from Child")
    }
}
```

## 例
以下は「super」を用いた基本的な使用例です。

```kotlin
open class Animal {
    open fun sound() {
        println("Animal sound")
    }
}

class Dog : Animal() {
    override fun sound() {
        super.sound() // Animalクラスのsoundメソッドを呼び出す
        println("Bark")
    }
}

fun main() {
    val dog = Dog()
    dog.sound() // 出力: "Animal sound" と "Bark"
}
```

## 説明
「super」を使用する際の一般的な注意点として、以下があります。

- **親クラスのメソッドがオーバーライドされていない場合**: 親クラスのメソッドにアクセスするために「super」を使っても、実行時には親クラスのメソッドが呼び出されます。
- **多重継承**: Kotlinではクラスの多重継承はサポートされていませんが、インターフェースの多重実装は可能です。この場合、どのインターフェースのメソッドを呼び出すかを明示する必要があります。
  
```kotlin
interface First {
    fun greet() { println("Hello from First") }
}

interface Second {
    fun greet() { println("Hello from Second") }
}

class Third : First, Second {
    override fun greet() {
        super<First>.greet() // Firstのgreetメソッドを呼び出す
        super<Second>.greet() // Secondのgreetメソッドを呼び出す
    }
}
```

## 一文サマリー
Kotlinの「super」キーワードは、親クラスのメンバーにアクセスするために使用され、オブジェクト指向プログラミングにおける継承の重要な要素です。