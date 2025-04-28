<!--
Meta Description: # Operatoren in Kotlin: Ein umfassender Leitfaden ## Synopsis Operatoren in Kotlin sind spezielle Symbole oder Schlüsselwörter, die bestimmte Operatio...
Meta Keywords: kotlin, und, val, operatoren, true
-->

# Operatoren in Kotlin: Ein umfassender Leitfaden

## Synopsis
Operatoren in Kotlin sind spezielle Symbole oder Schlüsselwörter, die bestimmte Operationen auf Variablen und Werten ausführen. Sie ermöglichen eine klare und prägnante Syntax zur Durchführung grundlegender und komplexer Berechnungen sowie zur Manipulation von Objekten.

## Dokumentation
In Kotlin sind Operatoren in verschiedene Kategorien unterteilt, darunter arithmetische, logische, Vergleichs- und Zuweisungsoperatoren. Diese Operatoren ermöglichen Entwicklern, auf einfache Weise mit Daten zu interagieren.

### Arithmetische Operatoren
- **Addition (+)**: Addiert zwei Zahlen.
- **Subtraktion (-)**: Subtrahiert eine Zahl von einer anderen.
- **Multiplikation (*)**: Multipliziert zwei Zahlen.
- **Division (/)**: Teilt eine Zahl durch eine andere.
- **Modulo (%)**: Gibt den Rest einer Division zurück.

### Vergleichsoperatoren
- **Gleich (==)**: Überprüft, ob zwei Werte gleich sind.
- **Ungleich (!=)**: Überprüft, ob zwei Werte ungleich sind.
- **Größer als (>)**: Überprüft, ob der linke Operand größer ist als der rechte.
- **Kleiner als (<)**: Überprüft, ob der linke Operand kleiner ist als der rechte.

### Logische Operatoren
- **Und (&&)**: Gibt true zurück, wenn beide Operanden true sind.
- **Oder (||)**: Gibt true zurück, wenn mindestens einer der Operanden true ist.
- **Negation (!)**: Kehrt den Wahrheitswert eines Ausdrucks um.

### Zuweisungsoperatoren
- **Zuweisung (=)**: Weist einen Wert einer Variablen zu.
- **Erhöhen (+=)**: Addiert einen Wert zur Variablen und weist das Ergebnis derselben zu.

## Beispiele
**Arithmetische Operationen:**
```kotlin
val a = 10
val b = 5
val summe = a + b // Ergebnis: 15
val differenz = a - b // Ergebnis: 5
```

**Vergleichsoperationen:**
```kotlin
val x = 10
val y = 20
println(x == y) // Ausgabe: false
println(x < y)  // Ausgabe: true
```

**Logische Operationen:**
```kotlin
val istWahr = true
val istFalsch = false
println(istWahr && istFalsch) // Ausgabe: false
println(istWahr || istFalsch) // Ausgabe: true
```

## Erklärung
Ein häufiges Missverständnis ist die Verwendung von `==` und `===`. In Kotlin wird `==` verwendet, um den Inhalt zweier Objekte zu vergleichen (strukturelle Gleichheit), während `===` die Referenzgleichheit überprüft (ob beide Variablen auf dasselbe Objekt im Speicher verweisen).

Ein weiterer wichtiger Punkt ist, dass die Division von zwei Ganzzahlen in Kotlin eine Ganzzahldivision ergibt. Um das Ergebnis als Fließkommazahl zu erhalten, muss einer der Operanden vom Typ `Double` oder `Float` sein.

## Einzeilenzusammenfassung
Operatoren in Kotlin sind essenzielle Werkzeuge zur Durchführung von Berechnungen und logischen Operationen in einer klaren und effizienten Syntax.