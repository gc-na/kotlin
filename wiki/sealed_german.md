<!--
Meta Description: # Sealed Classes in Kotlin: Eine umfassende Anleitung ## Synopsis Sealed Classes in Kotlin sind ein leistungsstarkes Konzept zur Definition geschlosse...
Meta Keywords: sealed, shape, von, class, eine
-->

# Sealed Classes in Kotlin: Eine umfassende Anleitung

## Synopsis
Sealed Classes in Kotlin sind ein leistungsstarkes Konzept zur Definition geschlossener Hierarchien von Klassen, die eine begrenzte Anzahl von Unterklassen zulassen und somit die Typensicherheit und Lesbarkeit des Codes erhöhen.

## Dokumentation
Sealed Classes sind ein wichtiges Feature in Kotlin, das es Entwicklern ermöglicht, eine Klasse zu definieren, deren Unterklassen begrenzt sind und nur im selben Dateikontext definiert werden können. Dieses Feature fördert die Sicherheit und Klarheit, indem es sicherstellt, dass alle möglichen Subtypen an einem Ort sichtbar sind.

### Zweck
Der Hauptzweck von Sealed Classes besteht darin, eine kontrollierte Hierarchie von Klassen zu schaffen, die den Umgang mit verschiedenen Typen von Daten erleichtert, insbesondere in Kombination mit `when`-Ausdrücken. Sie sind besonders nützlich in der funktionalen Programmierung und bei der Arbeit mit Zustandsmodellen.

### Verwendung
Um eine Sealed Class zu definieren, verwenden Sie das Schlüsselwort `sealed`, gefolgt von der Klassendeklaration. Alle Unterklassen müssen in derselben Datei definiert werden.

```kotlin
sealed class Result
data class Success(val data: String) : Result()
data class Error(val exception: Exception) : Result()
```

In diesem Beispiel haben wir eine `sealed class` namens `Result`, die zwei Unterklassen `Success` und `Error` hat.

## Beispiele
Hier sind einige einfache Beispiele zur Verwendung von Sealed Classes in Kotlin:

### Beispiel 1: Grundlegende Verwendung
```kotlin
sealed class Shape {
    data class Circle(val radius: Double) : Shape()
    data class Rectangle(val width: Double, val height: Double) : Shape()
}

fun describeShape(shape: Shape): String {
    return when (shape) {
        is Shape.Circle -> "Ein Kreis mit Radius: ${shape.radius}"
        is Shape.Rectangle -> "Ein Rechteck mit Breite: ${shape.width} und Höhe: ${shape.height}"
    }
}
```

### Beispiel 2: Verwendung mit `when`
```kotlin
fun handleResult(result: Result) {
    when (result) {
        is Success -> println("Erfolg: ${result.data}")
        is Error -> println("Fehler: ${result.exception.message}")
    }
}
```

## Erklärung
Bei der Verwendung von Sealed Classes gibt es einige häufige Stolpersteine:

- **Keine Unterklassen außerhalb der Datei**: Sie können keine Unterklassen einer Sealed Class in einer anderen Datei definieren, was die Modularität einschränken könnte.
- **Unvollständige `when`-Ausdrücke**: Wenn Sie einen `when`-Ausdruck verwenden, müssen Sie sicherstellen, dass alle möglichen Unterklassen behandelt werden. Andernfalls erhalten Sie eine Warnung, dass nicht alle Fälle abgedeckt sind.
- **Keine Instanziierung**: Eine Sealed Class selbst kann nicht instanziiert werden; sie dient lediglich als Basis für ihre Unterklassen.

## Ein-Satz-Zusammenfassung
Sealed Classes in Kotlin ermöglichen es Entwicklern, eine geschlossene Hierarchie von Klassen zu definieren, die die Typsicherheit erhöhen und die Handhabung von Daten durch kontrollierte Unterklassen erleichtern.