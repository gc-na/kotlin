<!--
Meta Description: # `noinline` en Kotlin: Uso y Aplicaciones ## Sinopsis El modificador `noinline` en Kotlin permite pasar funciones como parámetros sin que el compilad...
Meta Keywords: noinline, que, lambda, inline, kotlin
-->

# `noinline` en Kotlin: Uso y Aplicaciones

## Sinopsis
El modificador `noinline` en Kotlin permite pasar funciones como parámetros sin que el compilador las convierta en funciones de orden superior. Esto es especialmente útil en contextos donde se utilizan lambdas y se desea evitar la inlining de una función específica.

## Documentación
En Kotlin, el modificador `noinline` se utiliza en parámetros de función que son lambdas. Por defecto, Kotlin intenta optimizar el rendimiento mediante la inlining de funciones, lo que significa que el cuerpo de la función se inserta directamente en el lugar donde se llama. Sin embargo, hay ocasiones en las que no se desea que una lambda se inline, por ejemplo, cuando se pasa como argumento a otra función que no es de orden superior.

### Propósito
El propósito de `noinline` es permitir que el compilador maneje una lambda de manera más flexible, evitando la inlining para ciertos casos donde se requiere preservar la referencia original de la función.

### Uso
Para utilizar `noinline`, se debe declarar en la firma de la función donde se pasa el lambda. Aquí hay un ejemplo básico de cómo se aplica:

```kotlin
inline fun exampleFunction(inlinedLambda: () -> Unit, noinline nonInlinedLambda: () -> Unit) {
    // Se puede llamar a la lambda inline
    inlinedLambda()
    
    // Se puede almacenar la lambda no inline
    val lambdaReference = nonInlinedLambda
    lambdaReference()
}
```

En este ejemplo, `inlinedLambda` se inlina mientras que `nonInlinedLambda` se mantiene como una referencia.

## Ejemplos
### Ejemplo 1: Uso básico de `noinline`

```kotlin
inline fun runWithLogging(inlined: () -> Unit, noinline nonInlined: () -> Unit) {
    println("Iniciando la ejecución...")
    inlined()
    println("Ejecutando lambda no inline...")
    nonInlined()
}

fun main() {
    runWithLogging(
        { println("Lambda inlined ejecutada") },
        { println("Lambda no inline ejecutada") }
    )
}
```

### Ejemplo 2: Uso en funciones de orden superior

```kotlin
inline fun executeWithCallbacks(crossinline success: () -> Unit, noinline failure: () -> Unit) {
    try {
        success()
    } catch (e: Exception) {
        failure()
    }
}

fun main() {
    executeWithCallbacks(
        { println("Éxito!") },
        { println("Fallido!") }
    )
}
```

## Explicación
### Errores comunes y notas adicionales
- **Uso incorrecto de `noinline`:** Si se intenta usar `noinline` en un parámetro que no es un lambda, se producirá un error de compilación.
- **Limitaciones en la inlining:** Aunque `noinline` evita la inlining, esto puede impactar el rendimiento si se utiliza incorrectamente, ya que la creación de referencias a funciones puede introducir una sobrecarga adicional.
- **Interacción con `crossinline`:** `crossinline` permite que una lambda se use dentro de una función inline sin que se inlina, y se puede combinar con `noinline` para obtener un comportamiento específico.

## Resumen en una línea
El modificador `noinline` en Kotlin permite evitar la inlining de lambdas en funciones inline, facilitando su uso como referencias sin perder la optimización de otras funciones.