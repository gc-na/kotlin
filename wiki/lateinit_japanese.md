<!--
Meta Description: # Kotlinの「lateinit」：遅延初期化プロパティの使い方 ## 概要 Kotlinにおける「lateinit」は、クラスのプロパティを遅延初期化するための修飾子です。これにより、プロパティが宣言された時点ではなく、後で初期化することが可能になります。 ## ドキュメンテーション 「lat...
Meta Keywords: lateinit, user, name, fun, printname
-->

# Kotlinの「lateinit」：遅延初期化プロパティの使い方

## 概要
Kotlinにおける「lateinit」は、クラスのプロパティを遅延初期化するための修飾子です。これにより、プロパティが宣言された時点ではなく、後で初期化することが可能になります。

## ドキュメンテーション
「lateinit」は、非ヌル型のプロパティに対して使用される修飾子です。通常、Kotlinのプロパティは初期化時に値を持たなければなりませんが、特定のケースでは初期化が後で行われる場合があります。例えば、依存性注入やテスト環境での使用などです。

### 使用方法
- **宣言**: プロパティの型は非ヌル型である必要があります。
- **初期化**: プロパティは、使用する前に必ず初期化しなければなりません。
- **アクセス**: 初期化されていない状態でアクセスすると、`UninitializedPropertyAccessException`がスローされます。

### 詳細
- `lateinit`を使用することで、初期化が遅れるプロパティを定義できます。
- `lateinit`は基本的に、`var`プロパティにのみ使用可能で、`val`プロパティには使用できません。
- `lateinit`プロパティが初期化されたかどうかを確認するためには、`::プロパティ名.isInitialized`を使用します。

## 例
以下は、`lateinit`を使用した基本的な例です。

```kotlin
class User {
    lateinit var name: String

    fun initializeName() {
        name = "田中"
    }

    fun printName() {
        if (::name.isInitialized) {
            println("名前: $name")
        } else {
            println("名前は初期化されていません。")
        }
    }
}

fun main() {
    val user = User()
    user.printName()  // 出力: 名前は初期化されていません。
    user.initializeName()
    user.printName()  // 出力: 名前: 田中
}
```

## 説明
`lateinit`を使用する際の一般的な落とし穴は、初期化されていないプロパティにアクセスすることです。この場合、`UninitializedPropertyAccessException`が発生します。したがって、プロパティが初期化されているかどうかを確認することが重要です。また、`lateinit`は、基本データ型（Int、Booleanなど）には使用できません。これらの型は、初期値を持つ必要があります。

## 一文の要約
Kotlinの「lateinit」は、非ヌル型のプロパティを遅延初期化するための便利な修飾子です。