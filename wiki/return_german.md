<!--
Meta Description: # Rückgabewerte in Kotlin: Die Verwendung des "return"-Befehls ## Synopsis Der "return"-Befehl in Kotlin ermöglicht es Entwicklern, den Wert einer Fun...
Meta Keywords: der, return, funktion, kotlin, einer
-->

# Rückgabewerte in Kotlin: Die Verwendung des "return"-Befehls

## Synopsis
Der "return"-Befehl in Kotlin ermöglicht es Entwicklern, den Wert einer Funktion zurückzugeben und somit das Ergebnis einer Berechnung oder Operation an den Aufrufer der Funktion zu übermitteln. 

## Dokumentation
In Kotlin ist der "return"-Befehl ein zentraler Bestandteil der Funktionsdefinition. Er beendet die Ausführung einer Funktion und gibt den angegebenen Wert zurück. Dies ist besonders nützlich, um Ergebnisse aus Funktionen zu kommunizieren oder um Bedingungen innerhalb der Funktion zu steuern.

### Zweck
Der Hauptzweck des "return"-Befehls ist es, das Ende einer Funktion zu kennzeichnen und einen Wert an den Aufrufer zurückzugeben. Die Verwendung von "return" ist entscheidend für die Funktionalität von Programmen, die auf Berechnungen oder Entscheidungslogik basieren.

### Verwendung
Der "return"-Befehl wird innerhalb einer Funktion verwendet und kann nur einmal pro Funktionsaufruf eingesetzt werden. Der zurückgegebene Wert muss mit dem Rückgabetyp der Funktion übereinstimmen. In Kotlin können Funktionen auch ohne Rückgabewert definiert werden, indem der Rückgabetyp als `Unit` angegeben wird, was dem `void` in anderen Programmiersprachen entspricht.

### Details
- **Rückgabewert**: Der Typ des Wertes, der zurückgegeben wird, muss im Funktionsheader angegeben werden.
- **Mehrere Rückgaben**: Es ist nicht möglich, mehrere Werte gleichzeitig mit "return" zurückzugeben. Um mehrere Werte zurückzugeben, kann ein Datenklasse oder ein Pair verwendet werden.
- **Rückgabe in Lambda-Ausdrücken**: In Kotlin können auch in Lambda-Ausdrücken Rückgaben mit "return" verwendet werden, wobei die Syntax leicht abweicht.

## Beispiele
### Einfaches Beispiel
```kotlin
fun addiere(a: Int, b: Int): Int {
    return a + b
}

fun main() {
    val ergebnis = addiere(5, 3)
    println(ergebnis) // Ausgabe: 8
}
```

### Verwendung in Lambda-Ausdrücken
```kotlin
val liste = listOf(1, 2, 3, 4, 5)
val gefilterteListe = liste.filter {
    if (it % 2 == 0) return@filter true else return@filter false
}
println(gefilterteListe) // Ausgabe: [2, 4]
```

## Erklärung
Ein häufiger Stolperstein beim Einsatz von "return" ist, dass der Befehl nur innerhalb des Funktionskontexts verwendet werden kann. Versucht man, "return" außerhalb einer Funktion zu verwenden, führt dies zu einem Compilerfehler. Zudem kann der Missbrauch von "return" in komplexen Kontrollstrukturen zu Verwirrung führen, insbesondere wenn es in verschachtelten Funktionen oder Lambda-Ausdrücken eingesetzt wird.

Ein weiterer Punkt ist, dass der Rückgabewert der Funktion mit dem im Funktionskopf deklarierten Rückgabetyp übereinstimmen muss. Ein Mismatch kann ebenfalls zu Kompilierungsfehlern führen.

## Einzeiliger Überblick
Der "return"-Befehl in Kotlin gibt den Wert einer Funktion zurück und beendet deren Ausführung.