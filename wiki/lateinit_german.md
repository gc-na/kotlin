<!--
Meta Description: # Kotlin `lateinit`: Verzögerte Initialisierung von Variablen ## Synopsis In Kotlin ermöglicht das `lateinit`-Schlüsselwort die verzögerte Initialisie...
Meta Keywords: lateinit, die, kotlin, nicht, werden
-->

# Kotlin `lateinit`: Verzögerte Initialisierung von Variablen

## Synopsis
In Kotlin ermöglicht das `lateinit`-Schlüsselwort die verzögerte Initialisierung von nicht-nullbaren Variablen, wodurch die Notwendigkeit für nullbare Typen entfällt und die Codequalität verbessert wird.

## Documentation
Das `lateinit`-Schlüsselwort wird in Kotlin verwendet, um die Initialisierung von nicht-nullbaren Variablen aufzuschieben. Dies ist besonders nützlich in Situationen, in denen eine Variable nicht sofort einen Wert zugewiesen bekommt, wie beispielsweise in Dependency Injection oder bei der Verwendung von Views in Android.

### Zweck
Der Hauptzweck von `lateinit` besteht darin, zu vermeiden, dass Variablen als nullable deklariert werden müssen, wenn man sicher ist, dass sie vor ihrer Verwendung initialisiert werden. Dies fördert die Typensicherheit und reduziert die Wahrscheinlichkeit von NullPointerExceptions.

### Verwendung
`lateinit` kann nur mit Variablen verwendet werden, die als `var` deklariert sind. Es kann nicht mit `val` verwendet werden, da `val` eine sofortige Initialisierung erfordert.

### Details
- `lateinit` kann nur für primitive Typen (z.B. `Int`, `Boolean`) verwendet werden, wenn sie in einer Wrapper-Klasse (z.B. `Integer`, `Boolean`) deklariert sind.
- Eine `lateinit`-Variable muss initialisiert werden, bevor sie verwendet wird. Andernfalls wirft der Compiler eine `UninitializedPropertyAccessException`.
- Man kann den Status einer `lateinit`-Variable mit der `::variableName.isInitialized`-Syntax überprüfen.

## Examples
Hier sind einige grundlegende Beispiele zur Verwendung von `lateinit` in Kotlin:

### Beispiel 1: Verwendung in einer Klasse
```kotlin
class Beispiel {
    lateinit var name: String

    fun initName(n: String) {
        name = n
    }

    fun printName() {
        if (::name.isInitialized) {
            println("Name: $name")
        } else {
            println("Name wurde noch nicht initialisiert.")
        }
    }
}

fun main() {
    val beispiel = Beispiel()
    beispiel.printName() // Ausgabe: Name wurde noch nicht initialisiert.
    beispiel.initName("Kotlin")
    beispiel.printName() // Ausgabe: Name: Kotlin
}
```

### Beispiel 2: Verwendung in Android
```kotlin
class MainActivity : AppCompatActivity() {
    lateinit var textView: TextView

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        textView = findViewById(R.id.textView)
        textView.text = "Hallo Kotlin"
    }
}
```

## Explanation
Ein häufiger Fehler beim Arbeiten mit `lateinit` ist, zu versuchen, auf die Variable zuzugreifen, bevor sie initialisiert wurde. Dies führt zu einer `UninitializedPropertyAccessException`. Um dies zu vermeiden, sollte immer überprüft werden, ob die Variable initialisiert ist, bevor sie verwendet wird.

Zudem ist es wichtig zu beachten, dass `lateinit` nicht für primitive Datentypen verwendet werden kann. Stattdessen müssen die entsprechenden Wrapper-Klassen verwendet werden. Dies kann zu Verwirrung führen, wenn Entwickler nicht mit dem Konzept vertraut sind.

## One Line Summary
`lateinit` in Kotlin ermöglicht die verzögerte Initialisierung von nicht-nullbaren Variablen, fördert die Typensicherheit und reduziert NullPointerExceptions.