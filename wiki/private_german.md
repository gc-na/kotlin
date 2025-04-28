<!--
Meta Description: # Private in Kotlin: Zugriffskontrolle für Klassen und Mitglieder ## Synopsis Das Schlüsselwort `private` in Kotlin wird verwendet, um den Zugriff auf...
Meta Keywords: private, der, klasse, kotlin, die
-->

# Private in Kotlin: Zugriffskontrolle für Klassen und Mitglieder

## Synopsis
Das Schlüsselwort `private` in Kotlin wird verwendet, um den Zugriff auf Klassenmitglieder und -methoden zu steuern. Es ist ein wichtiges Konzept zur Kapselung, das hilft, den Zugriff auf Daten und Funktionen in einer Klasse zu beschränken.

## Documentation
In Kotlin ermöglicht das Schlüsselwort `private` die Einschränkung des Zugriffs auf Klassenmitglieder (Eigenschaften und Funktionen) innerhalb der Klasse selbst. Dies bedeutet, dass andere Klassen oder Objekte außerhalb der definierten Klasse nicht auf diese Mitglieder zugreifen können. 

### Zweck
Der Hauptzweck von `private` ist die Kapselung von Daten, was zu einem besseren Design und einer höheren Wartbarkeit des Codes führt. Durch die Verwendung von `private` kann der Entwickler sicherstellen, dass sensible Daten nicht versehentlich von außen verändert werden.

### Verwendung
Um ein Klassenmitglied als `private` zu deklarieren, fügen Sie einfach das Schlüsselwort `private` vor der Deklaration hinzu. Hier ist die grundlegende Syntax:

```kotlin
class MyClass {
    private var secret: String = "Geheimnis"

    private fun revealSecret() {
        println(secret)
    }
}
```

In diesem Beispiel können sowohl die Eigenschaft `secret` als auch die Funktion `revealSecret` nur innerhalb der Klasse `MyClass` aufgerufen werden.

### Details
- `private` gilt nicht nur für Eigenschaften und Funktionen, sondern auch für Konstruktoren, die als `private` deklariert werden können, um die Instanziierung der Klasse von außerhalb zu verhindern.
- Kotlin unterstützt auch `private` für Nested Classes, sodass Mitglieder innerhalb einer äußeren Klasse den Zugriff auf private Mitglieder einer inneren Klasse haben.

## Examples
Hier sind einige einfache Beispiele zur Verwendung des `private`-Schlüsselworts in Kotlin:

### Beispiel 1: Private Eigenschaft
```kotlin
class User {
    private var password: String = "passwort123"

    fun showPassword() {
        println(password) // Zugriff innerhalb der Klasse erlaubt
    }
}

fun main() {
    val user = User()
    user.showPassword() // Gibt "passwort123" aus
    // user.password // Fehler: Cannot access 'password': it is private in 'User'
}
```

### Beispiel 2: Private Methode
```kotlin
class Calculator {
    private fun add(a: Int, b: Int): Int {
        return a + b
    }

    fun calculate(a: Int, b: Int): Int {
        return add(a, b) // Zugriff auf private Methode erlaubt
    }
}

fun main() {
    val calc = Calculator()
    println(calc.calculate(5, 3)) // Gibt 8 aus
    // calc.add(5, 3) // Fehler: Cannot access 'add': it is private in 'Calculator'
}
```

## Explanation
Ein häufiger Fehler bei der Verwendung von `private` ist das Missverständnis darüber, wo der Zugriff erlaubt ist. Es ist wichtig zu beachten, dass `private` nur innerhalb der Klasse gilt und nicht in Subklassen oder anderen Klassen, selbst wenn diese im selben Paket sind.

Ein weiteres Missverständnis kann auftreten, wenn `private` in inneren Klassen verwendet wird. Ein privates Mitglied einer äußeren Klasse kann von der inneren Klasse aus aufgerufen werden, jedoch nicht von anderen Klassen im selben Paket.

## One Line Summary
Das Schlüsselwort `private` in Kotlin ermöglicht die Kapselung von Klassenmitgliedern und -methoden, um den Zugriff auf sie außerhalb der Klasse zu verhindern.