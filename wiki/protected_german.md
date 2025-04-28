<!--
Meta Description: # Das Schlüsselwort "protected" in Kotlin: Ein umfassender Leitfaden ## Synopsis Das Schlüsselwort "protected" in Kotlin ist ein Zugriffsmodifizierer,...
Meta Keywords: protected, der, und, ist, die
-->

# Das Schlüsselwort "protected" in Kotlin: Ein umfassender Leitfaden

## Synopsis
Das Schlüsselwort "protected" in Kotlin ist ein Zugriffsmodifizierer, der den Zugriff auf Klassenmitglieder steuert. Es erlaubt den Zugriff auf bestimmte Eigenschaften und Methoden nur innerhalb der Klasse selbst und ihren Unterklassen.

## Documentation
In Kotlin können Zugriffsmodifizierer verwendet werden, um zu definieren, wie und wo Klassenmitglieder (Eigenschaften und Methoden) zugänglich sind. Der Modifizierer "protected" ist speziell dafür gedacht, dass ein Klassenmitglied nur innerhalb der Klasse und in ihren abgeleiteten Klassen sichtbar ist. Dies trägt zur Kapselung und zum Schutz der Datenintegrität bei.

### Zweck
Der Zweck von "protected" ist es, die Sichtbarkeit von Klassenmitgliedern zu beschränken und gleichzeitig die Vererbung zu ermöglichen. Dies ermöglicht es Unterklassen, auf die geschützten Mitglieder ihrer Superklassen zuzugreifen, während der Zugriff von außen auf diese Mitglieder verhindert wird.

### Verwendung
Das Schlüsselwort "protected" wird in der Deklaration von Eigenschaften und Methoden verwendet. Hier ist die allgemeine Syntax:

```kotlin
open class Superklasse {
    protected val geschuetzteEigenschaft: Int = 42

    protected fun geschuetzteMethode() {
        // Methode, die nur in diesen und abgeleiteten Klassen aufgerufen werden kann
    }
}

class Unterklasse : Superklasse() {
    fun beispiel() {
        println(geschuetzteEigenschaft) // Zugriff auf die geschützte Eigenschaft
        geschuetzteMethode() // Zugriff auf die geschützte Methode
    }
}
```

## Examples
### Beispiel 1: Verwendung von "protected" in einer Superklasse
```kotlin
open class Fahrzeug {
    protected val maxGeschwindigkeit: Int = 200

    protected fun beschleunigen() {
        println("Das Fahrzeug beschleunigt.")
    }
}

class Auto : Fahrzeug() {
    fun fahren() {
        println("Maximale Geschwindigkeit: $maxGeschwindigkeit km/h")
        beschleunigen()
    }
}
```

### Beispiel 2: Fehler beim Zugriff von außen
```kotlin
class Motorrad : Fahrzeug() {
    fun fahren() {
        // println(maxGeschwindigkeit) // Fehler: 'maxGeschwindigkeit' ist geschützt
        // beschleunigen() // Fehler: 'beschleunigen' ist geschützt
    }
}
```

## Explanation
Ein häufiger Stolperstein bei der Verwendung von "protected" ist das Missverständnis über den Zugriff von außerhalb der Klasse. Geschützte Mitglieder sind nicht für Instanzen der Klasse zugänglich, sondern nur innerhalb der Klasse selbst und ihrer Unterklassen. Ein weiterer Punkt ist, dass "protected" in Kotlin nicht für top-level Funktionen oder Eigenschaften verwendet werden kann, da diese keinen Zusammenhang zu einer Klasse haben.

Es ist wichtig, "protected" mit Bedacht einzusetzen, um die Wartbarkeit des Codes zu gewährleisten. Übermäßiger Gebrauch kann zu einem schwer verständlichen Code führen, insbesondere wenn viele geschützte Mitglieder in einer Vererbungshierarchie vorhanden sind.

## One Line Summary
Das Schlüsselwort "protected" in Kotlin ermöglicht den Zugriff auf Klassenmitglieder nur innerhalb der Klasse und deren Unterklassen, wodurch die Datenkapselung gefördert wird.