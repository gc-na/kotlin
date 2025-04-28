<!--
Meta Description: # Reified en Kotlin: Entendiendo su Uso y Aplicaciones ## Sinopsis El modificador `reified` en Kotlin permite mantener la información de tipo en tiemp...
Meta Keywords: reified, tipo, que, inline, modificador
-->

# Reified en Kotlin: Entendiendo su Uso y Aplicaciones

## Sinopsis
El modificador `reified` en Kotlin permite mantener la información de tipo en tiempo de ejecución, facilitando la implementación de funciones genéricas que requieren conocer el tipo específico de los parámetros.

## Documentación
El modificador `reified` se utiliza en funciones genéricas para conservar el tipo de un parámetro en tiempo de ejecución. Esto es especialmente útil en situaciones donde se necesita realizar operaciones de reflexión o trabajar con tipos genéricos que de otro modo serían eliminados en tiempo de compilación (es decir, el tipo se convierte en `Any`). 

### Propósito
El propósito principal de `reified` es simplificar el trabajo con tipos genéricos, permitiendo acceder al tipo concreto sin necesidad de pasar una clase como parámetro. Esto resulta en un código más limpio y legible.

### Uso
Para usar `reified`, debes declarar una función genérica con el modificador `inline`. La combinación de `inline` y `reified` permite que el compilador inserte el código en el lugar de la llamada, lo que significa que la información de tipo estará disponible.

```kotlin
inline fun <reified T> obtenerTipo(): String {
    return T::class.simpleName ?: "Desconocido"
}
```

## Ejemplos

### Ejemplo Básico
A continuación se muestra un ejemplo básico del uso de `reified` en una función genérica:

```kotlin
inline fun <reified T> imprimirTipo() {
    println("El tipo es: ${T::class.simpleName}")
}

fun main() {
    imprimirTipo<String>()  // Salida: El tipo es: String
    imprimirTipo<Int>()     // Salida: El tipo es: Int
}
```

### Uso en Funciones de Filtro
Un caso común del uso de `reified` es en funciones que filtran listas de objetos:

```kotlin
inline fun <reified T> List<Any>.filtrarPorTipo(): List<T> {
    return this.filterIsInstance<T>()
}

fun main() {
    val lista: List<Any> = listOf(1, "Hola", 2, "Mundo")
    val enteros: List<Int> = lista.filtrarPorTipo()
    println(enteros)  // Salida: [1, 2]
}
```

## Explicación
Al usar `reified`, es importante recordar que solo se puede utilizar en funciones marcadas como `inline`. Esto se debe a que el compilador necesita ser capaz de sustituir el código en tiempo de compilación para que la información del tipo esté disponible en tiempo de ejecución. 

### Errores Comunes
1. **Olvidar el Modificador `inline`:** Si no declaras la función como `inline`, el modificador `reified` no tendrá efecto y generará un error de compilación.
2. **Uso de `reified` en Clases o Propiedades:** El modificador `reified` solo es aplicable a funciones, no a clases ni a propiedades.

## Resumen en Una Línea
El modificador `reified` en Kotlin permite el acceso a la información del tipo en funciones genéricas, mejorando la flexibilidad y legibilidad del código.