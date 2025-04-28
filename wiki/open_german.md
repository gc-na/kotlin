<!--
Meta Description: # Das Schlüsselwort "open" in Kotlin: Verwendung und Bedeutung ## Synopsis Das Schlüsselwort "open" in Kotlin ermöglicht es Entwicklern, Klassen und F...
Meta Keywords: open, und, das, kotlin, klassen
-->

# Das Schlüsselwort "open" in Kotlin: Verwendung und Bedeutung

## Synopsis
Das Schlüsselwort "open" in Kotlin ermöglicht es Entwicklern, Klassen und Funktionen für die Vererbung zu öffnen. Standardmäßig sind alle Klassen und Funktionen in Kotlin final, was bedeutet, dass sie nicht erweitert oder überschrieben werden können.

## Documentation
In Kotlin ist das Schlüsselwort „open“ entscheidend für die objektorientierte Programmierung, da es Entwicklern die Möglichkeit gibt, Klassen und deren Mitglieder (Methoden und Eigenschaften) für die Vererbung zu kennzeichnen. Dies steht im Gegensatz zu vielen anderen Programmiersprachen, in denen alles standardmäßig veränderbar ist.

### Zweck
Das Hauptziel des „open“-Schlüsselworts ist es, eine kontrollierte Vererbung zu ermöglichen. Entwickler können gezielt entscheiden, welche Klassen und Funktionen in Unterklassen überschrieben werden können.

### Verwendung
Um eine Klasse oder Funktion als „open“ zu deklarieren, wird das Schlüsselwort direkt vor der Klasse oder Funktion verwendet. 

**Beispiel für eine offene Klasse:**
```kotlin
open class Fahrzeug {
    open fun fahren() {
        println("Das Fahrzeug fährt.")
    }
}
```

In diesem Beispiel ist die Klasse `Fahrzeug` offen, und die Methode `fahren()` kann in einer Unterklasse überschrieben werden.

## Examples
### Beispiel 1: Offene Klasse und Methode
```kotlin
open class Tier {
    open fun geräuschMachen() {
        println("Das Tier macht ein Geräusch.")
    }
}

class Hund : Tier() {
    override fun geräuschMachen() {
        println("Der Hund bellt.")
    }
}

fun main() {
    val meinHund = Hund()
    meinHund.geräuschMachen() // Ausgabe: Der Hund bellt.
}
```

### Beispiel 2: Offene Eigenschaften
```kotlin
open class Computer {
    open var preis: Double = 1000.0
}

class Laptop : Computer() {
    override var preis: Double = 800.0
}

fun main() {
    val meinLaptop = Laptop()
    println(meinLaptop.preis) // Ausgabe: 800.0
}
```

## Explanation
Ein häufiges Missverständnis ist, dass alle Klassen und Funktionen in Kotlin standardmäßig veränderbar sind. Tatsächlich sind sie jedoch final, es sei denn, sie werden ausdrücklich als open deklariert. Dies kann dazu führen, dass Entwickler versuchen, Methoden oder Klassen ohne das „open“-Schlüsselwort zu überschreiben, was zu Kompilierungsfehlern führt.

Ein weiterer wichtiger Punkt ist, dass das „open“-Schlüsselwort nur für Klassen und Funktionen verwendet werden kann, die nicht bereits als final deklariert sind. Wenn eine Klasse als final deklariert ist, kann sie nicht mehr geändert werden.

## One Line Summary
Das Schlüsselwort „open“ in Kotlin ermöglicht die Vererbung von Klassen und Funktionen, indem es diese für Unterklassen zugänglich macht.