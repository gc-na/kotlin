<!--
Meta Description: # Kotlinにおける「protected」アクセス修飾子の解説 ## 概要 Kotlinの「protected」アクセス修飾子は、クラス内およびそのサブクラスからのアクセスを制限するために使用されます。これにより、クラスの内部実装を隠蔽しながら、継承関係にあるクラスの間でのデータ共有を可能にしま...
Meta Keywords: protected, child, protectedproperty, parent, fun
-->

# Kotlinにおける「protected」アクセス修飾子の解説

## 概要
Kotlinの「protected」アクセス修飾子は、クラス内およびそのサブクラスからのアクセスを制限するために使用されます。これにより、クラスの内部実装を隠蔽しながら、継承関係にあるクラスの間でのデータ共有を可能にします。

## ドキュメント
「protected」は、Kotlinにおけるアクセス修飾子の一つで、クラスのプロパティやメソッドがどのようにアクセスできるかを制御します。具体的には、以下のように機能します。

- **目的**: クラスの内部で使用されるプロパティやメソッドを保護し、外部からのアクセスを防ぎつつ、サブクラスからはアクセスできるようにします。
- **使用方法**: 「protected」を指定することで、クラス内およびそのクラスを継承したクラス内からのみアクセス可能なメンバーを定義できます。
- **詳細**: Kotlinでは、フィールドやメソッドに「protected」修飾子を付けることで、これらのメンバーはサブクラスからアクセス可能になりますが、外部のクラスからはアクセスできません。

## 例
以下は、Kotlinにおける「protected」の基本的な使用例です。

```kotlin
open class Parent {
    protected val protectedProperty: String = "親クラスのプロパティ"

    protected fun protectedMethod() {
        println("親クラスのメソッド")
    }
}

class Child : Parent() {
    fun display() {
        println(protectedProperty) // アクセス可能
        protectedMethod() // アクセス可能
    }
}

fun main() {
    val child = Child()
    child.display()
    // println(child.protectedProperty) // エラー: 'protectedProperty' は 'Parent' からのアクセスが必要です
}
```

## 説明
「protected」を使用する際の一般的な注意点やトラブルポイントを以下に示します。

- **アクセス制限**: 「protected」メンバーは、クラス外部からは直接アクセスできないため、サブクラスでのみ使用することを意識する必要があります。外部からアクセスしようとするとコンパイルエラーが発生します。
- **サブクラスのインスタンス**: サブクラスのインスタンスが親クラスの「protected」メンバーにアクセスできるのは、そのインスタンスが存在している間だけです。
- **インターフェースとの違い**: Kotlinのインターフェースでは、「protected」メンバーを持つことはできません。インターフェースのメンバーは常に「public」となります。

## 一文要約
Kotlinの「protected」アクセス修飾子は、クラス内およびそのサブクラスからのアクセスを許可し、外部からのアクセスを制限するために使用されます。