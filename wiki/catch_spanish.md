<!--
Meta Description: # Uso de "catch" en Kotlin: Manejo de Excepciones ## Sinopsis El bloque `catch` en Kotlin se utiliza para manejar excepciones que pueden ocurrir duran...
Meta Keywords: catch, excepciones, bloque, que, kotlin
-->

# Uso de "catch" en Kotlin: Manejo de Excepciones

## Sinopsis
El bloque `catch` en Kotlin se utiliza para manejar excepciones que pueden ocurrir durante la ejecución de un programa. Permite a los desarrolladores interceptar errores y mantener la estabilidad de la aplicación.

## Documentación
En Kotlin, el manejo de excepciones se realiza utilizando la estructura `try-catch`. El bloque `try` contiene el código que puede lanzar excepciones, mientras que el bloque `catch` captura y maneja esas excepciones. Esta es una práctica fundamental para garantizar que el programa no se detenga abruptamente en caso de errores.

### Sintaxis
```kotlin
try {
    // Código que puede lanzar una excepción
} catch (e: ExceptionType) {
    // Manejo de la excepción
}
```

### Propósito
El propósito del bloque `catch` es permitir que los desarrolladores respondan a errores y excepciones de manera controlada, proporcionando una forma de gestionar situaciones inesperadas y mantener la funcionalidad de la aplicación.

### Uso
El bloque `catch` se utiliza junto con `try`. Es común ver varios bloques `catch` para manejar diferentes tipos de excepciones o un bloque `finally` que ejecuta código independientemente de si se lanzó o no una excepción.

## Ejemplos
### Ejemplo 1: Manejo Simple de Excepciones
```kotlin
fun division(a: Int, b: Int) {
    try {
        val resultado = a / b
        println("El resultado es $resultado")
    } catch (e: ArithmeticException) {
        println("Error: División por cero no permitida.")
    }
}

fun main() {
    division(10, 0)
}
```

### Ejemplo 2: Varios bloques `catch`
```kotlin
fun leerArchivo(nombre: String) {
    try {
        val contenido = File(nombre).readText()
        println(contenido)
    } catch (e: FileNotFoundException) {
        println("Error: El archivo no fue encontrado.")
    } catch (e: IOException) {
        println("Error: Ocurrió un error de entrada/salida.")
    }
}
```

## Explicación
Al utilizar el bloque `catch`, es importante tener en cuenta lo siguiente:
- **Excepciones específicas**: Es recomendable capturar excepciones específicas en lugar de usar `catch (e: Exception)` para evitar la captura de excepciones no deseadas y hacer más difícil el diagnóstico de problemas.
- **Múltiples bloques**: Puedes tener múltiples bloques `catch` para manejar diferentes tipos de excepciones. El orden de los bloques `catch` es importante; el bloque más específico debe ir primero.
- **Bloque `finally`**: Puedes agregar un bloque `finally` para ejecutar código que debe ejecutarse siempre, ya sea que se lance una excepción o no.

## Resumen en una línea
El bloque `catch` en Kotlin permite manejar excepciones, proporcionando control y estabilidad en la ejecución del programa.