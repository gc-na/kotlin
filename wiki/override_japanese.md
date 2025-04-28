<!--
Meta Description: # Kotlinの「override」キーワードについて ## 概要 Kotlinにおける「override」は、スーパークラスのメソッドやプロパティをサブクラスで再定義するためのキーワードです。この機能はオブジェクト指向プログラミングの重要な要素であり、ポリモーフィズムを実現します。 ## ドキュ...
Meta Keywords: override, open, val, kotlin, class
-->

# Kotlinの「override」キーワードについて

## 概要
Kotlinにおける「override」は、スーパークラスのメソッドやプロパティをサブクラスで再定義するためのキーワードです。この機能はオブジェクト指向プログラミングの重要な要素であり、ポリモーフィズムを実現します。

## ドキュメンテーション
### 目的
「override」キーワードは、スーパークラスで定義されたメソッドやプロパティをサブクラスで変更または拡張するために使用されます。これにより、サブクラスはスーパークラスの機能を再利用しつつ、特定の動作を変更することができます。

### 使用方法
「override」キーワードは、スーパークラスでオーバーライド可能なメソッドやプロパティに対して使用します。スーパークラスのメソッドには「open」修飾子を付ける必要があります。

#### メソッドのオーバーライド
```kotlin
open class Animal {
    open fun sound() {
        println("Animal sound")
    }
}

class Dog : Animal() {
    override fun sound() {
        println("Bark")
    }
}
```

#### プロパティのオーバーライド
```kotlin
open class Shape {
    open val area: Double
        get() = 0.0
}

class Circle(val radius: Double) : Shape() {
    override val area: Double
        get() = Math.PI * radius * radius
}
```

## 例
以下は、メソッドとプロパティのオーバーライドの基本的な使用例です。

### メソッドのオーバーライドの例
```kotlin
fun main() {
    val dog = Dog()
    dog.sound()  // 出力: Bark
}
```

### プロパティのオーバーライドの例
```kotlin
fun main() {
    val circle = Circle(2.0)
    println(circle.area)  // 出力: 12.566370614359172
}
```

## 説明
### 一般的な落とし穴
- **スーパークラスのメソッドに「open」修飾子がない場合**: オーバーライドを試みるとコンパイルエラーが発生します。
- **メソッドのシグネチャが異なる場合**: 引数の数や型、戻り値の型が異なる場合はオーバーライドとは見なされず、別のメソッドとして定義されます。

### 注意事項
- Kotlinでは、基本的にすべてのクラスはデフォルトでファイナル（オーバーライド不可）です。オーバーライドを許可するためには、クラスに「open」を付ける必要があります。
- プロパティの場合、ゲッターやセッターのオーバーライドも可能ですが、オーバーライド時には「get」または「set」キーワードを使用しなければなりません。

## 一文の要約
Kotlinの「override」キーワードは、スーパークラスのメソッドやプロパティをサブクラスで再定義するために不可欠な機能です。