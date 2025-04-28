<!--
Meta Description: # Kotlin "external": Verwendung und Bedeutung in der Kotlin-Programmierung ## Synopsis Das Schlüsselwort `external` in Kotlin ermöglicht die Deklarati...
Meta Keywords: kotlin, external, die, der, ist
-->

# Kotlin "external": Verwendung und Bedeutung in der Kotlin-Programmierung

## Synopsis
Das Schlüsselwort `external` in Kotlin ermöglicht die Deklaration von Funktionen und Eigenschaften, die in einer externen Bibliothek oder in einer anderen Programmiersprache definiert sind, typischerweise in C oder C++. Diese Funktionalität erlaubt es, Kotlin mit nativen Code-Bibliotheken zu verbinden und deren Funktionen zu nutzen.

## Documentation
In Kotlin wird das Schlüsselwort `external` verwendet, um anzugeben, dass eine Funktion oder Eigenschaft nicht im aktuellen Kotlin-Code implementiert ist, sondern extern definiert wird. Diese externen Implementierungen sind häufig in nativen Sprachen oder in Plattform-spezifischen Code-Basen geschrieben. 

### Zweck
Der Hauptzweck von `external` ist es, mit nativen Bibliotheken zu interagieren, insbesondere im Kontext der Kotlin/Native-Plattform, wo Kotlin-Code in Maschinensprache kompiliert wird und direkten Zugriff auf native APIs erforderlich ist.

### Verwendung
Um eine externe Funktion oder Eigenschaft zu deklarieren, wird das `external`-Schlüsselwort vor der Funktions- oder Eigenschaftsdeklaration platziert. Es erfordert keine Implementierung im Kotlin-Code selbst. Stattdessen wird erwartet, dass die Implementierung in der externen Bibliothek zur Laufzeit verfügbar ist.

```kotlin
external fun nativeFunction(param: Int): String
```

## Examples
Hier sind einige grundlegende Beispiele für die Verwendung des `external`-Schlüsselworts in Kotlin:

### Beispiel 1: Externe Funktion
```kotlin
external fun sqrt(x: Double): Double

fun main() {
    val number = 16.0
    println("Die Quadratwurzel von $number ist ${sqrt(number)}")
}
```

### Beispiel 2: Externe Eigenschaft
```kotlin
external val externalValue: Int

fun main() {
    println("Der Wert der externen Eigenschaft ist $externalValue")
}
```

## Explanation
Ein häufiger Stolperstein bei der Verwendung von `external` ist sicherzustellen, dass die externe Implementierung zur Verfügung steht, wenn der Kotlin-Code ausgeführt wird. Dies kann bedeuten, dass die entsprechenden nativen Bibliotheken korrekt verlinkt und geladen werden müssen. 

Ein weiterer Punkt ist, dass die Typen in den externen Deklarationen korrekt angegeben werden müssen, um Komplikationen und Laufzeitfehler zu vermeiden. Es ist auch wichtig zu beachten, dass `external` nur in bestimmten Kontexten sinnvoll ist, hauptsächlich bei der Arbeit mit Kotlin/Native.

## One Line Summary
Das `external`-Schlüsselwort in Kotlin ermöglicht die Deklaration von Funktionen und Eigenschaften, die in externen Bibliotheken oder in anderen Programmiersprachen definiert sind, und erleichtert so die Interoperabilität mit nativen APIs.