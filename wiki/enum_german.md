<!--
Meta Description: # Kotlin Enum: Eine umfassende Anleitung zur Verwendung von Aufzählungen in Kotlin ## Synopsis Enums in Kotlin sind eine spezielle Art von Klasse, die...
Meta Keywords: enum, kotlin, von, eine, enums
-->

# Kotlin Enum: Eine umfassende Anleitung zur Verwendung von Aufzählungen in Kotlin

## Synopsis
Enums in Kotlin sind eine spezielle Art von Klasse, die eine Gruppe von konstanten Werten definiert. Diese Datenstruktur ermöglicht es Entwicklern, benannte Werte zu erstellen, die typensicher sind und die Lesbarkeit des Codes erhöhen.

## Documentation
In Kotlin ist ein Enum (kurz für Enumerations) eine Klasse, die eine festgelegte Menge von Werten beschreibt. Enums sind besonders nützlich, wenn eine Variable nur eine begrenzte Anzahl von Werten annehmen kann, wie z.B. Wochentage, Statusanzeigen oder Kategorien.

### Zweck
Enums bieten eine strukturierte Möglichkeit, benannte Konstanten zu definieren, die typensicher sind. Anstatt magische Zahlen oder Strings zu verwenden, können Entwickler enums verwenden, um den Code klarer und wartbarer zu gestalten.

### Verwendung
Ein Enum wird in Kotlin mit dem Schlüsselwort `enum class` deklariert. Hier ist eine grundlegende Struktur:

```kotlin
enum class Farbe {
    ROT, GRÜN, BLAU
}
```

Jede Konstante in einem Enum ist ein Singleton. Enums können auch Eigenschaften und Methoden enthalten, was ihre Funktionalität erweitert.

### Details
Enums in Kotlin können:
- Eigenschaften und Methoden haben.
- Implementierungen von Interfaces bereitstellen.
- Mit `when`-Ausdrücken verwendet werden, um die Verarbeitung der verschiedenen Enum-Werte zu erleichtern.

## Examples
Hier sind einige grundlegende Beispiele zur Verwendung von Enums in Kotlin:

### Beispiel 1: Einfache Enum-Deklaration
```kotlin
enum class Wochentag {
    MONTAG, DIENSTAG, MITTWOCH, DONNERSTAG, FREITAG, SAMSTAG, SONNTAG
}
```

### Beispiel 2: Enum mit Eigenschaften
```kotlin
enum class Status(val code: Int) {
    AKTIV(1),
    INAKTIV(0),
    GESPERRT(-1);
    
    fun istAktiv() = this == AKTIV
}
```

### Beispiel 3: Verwendung in einer Funktion
```kotlin
fun beschreibeStatus(status: Status) {
    when (status) {
        Status.AKTIV -> println("Der Status ist aktiv.")
        Status.INAKTIV -> println("Der Status ist inaktiv.")
        Status.GESPERRT -> println("Der Status ist gesperrt.")
    }
}
```

## Explanation
Bei der Verwendung von Enums in Kotlin gibt es einige häufige Fallstricke:

- **Vergessen von `when`-Anweisungen**: Wenn Sie einen `when`-Ausdruck verwenden, um Enum-Werte zu verarbeiten, stellen Sie sicher, dass Sie alle möglichen Werte abdecken, um eine `NoWhenBranchMatchedException` zu vermeiden.
  
- **Enums und Vererbung**: Enums können nicht von anderen Klassen erben, da sie implizit von der Klasse `Enum` erben.

- **Leistung**: Da jeder Enum-Wert ein Singleton ist, kann die Verwendung von Enums im Vergleich zu regulären Klassen weniger Speicher benötigen, aber es ist wichtig, die Anzahl der Enum-Werte zu berücksichtigen, da dies die Leistung beeinflussen kann.

## One Line Summary
Enums in Kotlin sind eine mächtige Möglichkeit, eine festgelegte Gruppe von konstanten Werten zu definieren, die typensicher und leicht verständlich sind.