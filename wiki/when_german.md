<!--
Meta Description: # Verwendung von "when" in Kotlin – Ein umfassender Leitfaden ## Synopsis Der `when` Ausdruck in Kotlin ist eine leistungsstarke Kontrollstruktur, die...
Meta Keywords: when, ist, kotlin, println, eine
-->

# Verwendung von "when" in Kotlin – Ein umfassender Leitfaden

## Synopsis
Der `when` Ausdruck in Kotlin ist eine leistungsstarke Kontrollstruktur, die es ermöglicht, Werte zu vergleichen und basierend auf dem Ergebnis unterschiedliche Aktionen auszuführen. Er bietet eine elegante Alternative zu herkömmlichen `switch`-Anweisungen in anderen Programmiersprachen.

## Dokumentation
Der `when` Ausdruck wird verwendet, um mehrere Bedingungen zu überprüfen und zu entscheiden, welche Aktion ausgeführt werden soll. Er kann sowohl als Ausdruck als auch als Anweisung verwendet werden. Der `when` Ausdruck ist besonders nützlich, wenn mehrere mögliche Werte für eine Variable oder einen Ausdruck geprüft werden müssen.

### Zweck
Der Hauptzweck des `when` Ausdrucks ist es, die Lesbarkeit des Codes zu verbessern und komplexe bedingte Logik einfacher zu handhaben. Er kann beliebige Ausdrücke, Typen und sogar Bedingungen verwenden.

### Verwendung
Die allgemeine Syntax des `when` Ausdrucks ist wie folgt:

```kotlin
when (variable) {
    wert1 -> // Aktion für wert1
    wert2 -> // Aktion für wert2
    else -> // Standardaktion
}
```

Der `when` Ausdruck kann auch ohne eine Variable verwendet werden, um Bedingungen zu prüfen:

```kotlin
when {
    bedingung1 -> // Aktion für bedingung1
    bedingung2 -> // Aktion für bedingung2
    else -> // Standardaktion
}
```

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung des `when` Ausdrucks in Kotlin:

### Beispiel 1: Einfache Verwendung

```kotlin
val zahl = 3
when (zahl) {
    1 -> println("Eins")
    2 -> println("Zwei")
    3 -> println("Drei")
    else -> println("Eine andere Zahl")
}
```

### Beispiel 2: Verwendung ohne Wert

```kotlin
val temperatur = 25
when {
    temperatur < 0 -> println("Es ist kalt")
    temperatur in 0..20 -> println("Es ist mild")
    else -> println("Es ist warm")
}
```

### Beispiel 3: Typprüfung

```kotlin
fun beschreibe(objekt: Any) {
    when (objekt) {
        is String -> println("Es ist ein String mit Länge ${objekt.length}")
        is Int -> println("Es ist eine ganze Zahl: $objekt")
        else -> println("Unbekannter Typ")
    }
}
```

## Erklärung
Ein häufiger Fehler beim Einsatz des `when` Ausdrucks ist das Vergessen des `else` Zweigs. Wenn keine der Bedingungen erfüllt wird und kein `else` vorhanden ist, wirft die Anwendung eine `NoWhenBranchMatchedException`. 

Ein weiterer wichtiger Punkt ist, dass der `when` Ausdruck als Wert verwendet werden kann, was bedeutet, dass er einer Variablen zugewiesen werden kann:

```kotlin
val ergebnis = when (zahl) {
    1 -> "Eins"
    2 -> "Zwei"
    else -> "Eine andere Zahl"
}
```

Zusätzlich unterstützt `when` auch die Verwendung von Bereichsprüfungen und Typprüfungen, was seine Flexibilität erhöht.

## Ein Satz Zusammenfassung
Der `when` Ausdruck in Kotlin ist eine vielseitige und lesbare Kontrollstruktur, die Vergleiche und bedingte Logik effizient handhabt.