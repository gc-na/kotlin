<!--
Meta Description: # Verwendung des "super"-Schlüsselworts in Kotlin: Eine umfassende Anleitung ## Synopsis Das "super"-Schlüsselwort in Kotlin ermöglicht den Zugriff au...
Meta Keywords: der, super, auf, kotlin, von
-->

# Verwendung des "super"-Schlüsselworts in Kotlin: Eine umfassende Anleitung

## Synopsis
Das "super"-Schlüsselwort in Kotlin ermöglicht den Zugriff auf Mitglieder der übergeordneten Klasse, insbesondere in Fällen von Vererbung. Es spielt eine entscheidende Rolle bei der Implementierung von Polymorphismus und der Erweiterung von Funktionalitäten in abgeleiteten Klassen.

## Dokumentation
In Kotlin wird das "super"-Schlüsselwort verwendet, um auf Mitglieder (Methoden oder Eigenschaften) der übergeordneten Klasse zuzugreifen. Dies ist besonders nützlich in einer Vererbungshierarchie, wo eine Unterklasse die Implementierung einer Methode der Oberklasse überschreibt und dennoch auf die ursprüngliche Methode zugreifen möchte.

### Zweck
- **Zugriff auf übergeordnete Klassenmitglieder**: Ermöglicht es, Methoden oder Eigenschaften der übergeordneten Klasse innerhalb einer abgeleiteten Klasse zu verwenden.
- **Polymorphismus**: Unterstützt die Implementierung von polymorphen Verhalten, indem es dynamische Bindung ermöglicht.

### Verwendung
Das Schlüsselwort "super" wird vor dem Aufruf einer Methode oder dem Zugriff auf eine Eigenschaft verwendet. Hier ist die allgemeine Syntax:

```kotlin
super.methodName()
super.propertyName
```

## Beispiele

### Beispiel 1: Zugriff auf eine Methode der Oberklasse

```kotlin
open class Tier {
    open fun lautGeben() {
        println("Das Tier gibt einen Laut von sich.")
    }
}

class Hund : Tier() {
    override fun lautGeben() {
        super.lautGeben() // Aufruf der Methode der Oberklasse
        println("Der Hund bellt.")
    }
}

fun main() {
    val meinHund = Hund()
    meinHund.lautGeben()
}
```

**Ausgabe:**
```
Das Tier gibt einen Laut von sich.
Der Hund bellt.
```

### Beispiel 2: Zugriff auf eine Eigenschaft der Oberklasse

```kotlin
open class Fahrzeug {
    open val geschwindigkeit: Int = 0
}

class Auto : Fahrzeug() {
    override val geschwindigkeit: Int = 100

    fun info() {
        println("Die maximale Geschwindigkeit ist ${super.geschwindigkeit} km/h.")
    }
}

fun main() {
    val meinAuto = Auto()
    meinAuto.info()
}
```

**Ausgabe:**
```
Die maximale Geschwindigkeit ist 0 km/h.
```

## Erklärung
Ein häufiges Missverständnis beim Einsatz von "super" ist, dass es nicht nur für Methoden verwendet werden kann, sondern auch für Eigenschaften. Ein weiteres häufiges Problem tritt auf, wenn Entwickler versuchen, "super" in einem Kontext zu verwenden, in dem es nicht sinnvoll ist, z. B. außerhalb einer Methode oder einer Initialisierungsblock. 

Zusätzlich sei darauf hingewiesen, dass "super" in einer Mehrfachvererbungssituation (z. B. bei Interfaces) eine spezielle Behandlung benötigt, da Kotlin keine klassische Mehrfachvererbung unterstützt, sondern stattdessen Interfaces verwendet.

## Einzeiler-Zusammenfassung
Das "super"-Schlüsselwort in Kotlin ermöglicht den Zugriff auf Methoden und Eigenschaften der übergeordneten Klasse, um die Funktionalität von abgeleiteten Klassen zu erweitern und Polymorphismus zu unterstützen.