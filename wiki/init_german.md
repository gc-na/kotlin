<!--
Meta Description: # Init in Kotlin: Konstruktoren und Initialisierungsblöcke ## Synopsis In Kotlin ist das Schlüsselwort `init` ein wichtiger Bestandteil der Klassenstr...
Meta Keywords: der, init, wird, klasse, die
-->

# Init in Kotlin: Konstruktoren und Initialisierungsblöcke

## Synopsis
In Kotlin ist das Schlüsselwort `init` ein wichtiger Bestandteil der Klassenstruktur, das zur Initialisierung von Objekten verwendet wird. Es ermöglicht Entwicklern, Initialisierungslogik direkt innerhalb der Klasse zu definieren, was die Lesbarkeit und Wartbarkeit des Codes verbessert.

## Dokumentation
Das `init`-Schlüsselwort wird in Kotlin verwendet, um einen Initialisierungsblock innerhalb einer Klasse zu definieren. Dieser Block wird aufgerufen, wenn eine Instanz der Klasse erstellt wird. Dies ist besonders nützlich, um Standardwerte zu setzen oder notwendige Initialisierungen vorzunehmen, die nicht nur auf Konstruktorparameter angewiesen sind.

### Verwendung
Der `init`-Block wird in einer Klasse definiert, und es können mehrere `init`-Blöcke in einer Klasse vorhanden sein. Die Reihenfolge der Ausführung ist die Reihenfolge, in der sie im Code erscheinen. Der `init`-Block kann auch auf die Eigenschaften der Klasse zugreifen und diese verändern.

### Details
- Der `init`-Block wird immer aufgerufen, wenn die Klasse instanziiert wird, bevor der Konstruktor vollständig ausgeführt wird.
- Er kann verwendet werden, um Validierungen durchzuführen oder komplexe Initialisierungen vorzunehmen.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung des `init`-Schlüsselworts in Kotlin:

```kotlin
class Person(val name: String, val age: Int) {
    init {
        println("Person wurde erstellt: $name, $age Jahre alt")
    }
}

fun main() {
    val person = Person("Max", 25)
}
```

In diesem Beispiel gibt der `init`-Block eine Nachricht aus, wenn eine neue `Person`-Instanz erstellt wird.

Ein weiteres Beispiel mit mehreren `init`-Blöcken:

```kotlin
class Car(val model: String, val year: Int) {
    init {
        println("Erster Initialisierungsblock: Modell - $model")
    }

    init {
        println("Zweiter Initialisierungsblock: Jahr - $year")
    }
}

fun main() {
    val car = Car("Audi A4", 2020)
}
```

Hier werden beide `init`-Blöcke nacheinander ausgeführt, wenn das Auto erstellt wird.

## Erklärung
Ein häufiger Fallstrick bei der Verwendung von `init` ist das Verständnis der Reihenfolge, in der die Initialisierungsblöcke ausgeführt werden. Diese Reihenfolge entspricht der Reihenfolge der Definition im Code. Außerdem sollte man darauf achten, dass der `init`-Block keinen Rückgabewert hat und nicht explizit aufgerufen werden kann.

Ein weiterer Punkt ist, dass im `init`-Block keine Eigenschaften deklariert werden können; stattdessen sollten diese im Header der Klasse definiert werden.

## Ein-Satz-Zusammenfassung
Das `init`-Schlüsselwort in Kotlin ermöglicht die Durchführung von Initialisierungen und Validierungen innerhalb von Klassen, bevor der Konstruktor vollständig ausgeführt wird.