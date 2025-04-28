<!--
Meta Description: # Uso de `val` en Kotlin: Declaración de Variables Inmutables ## Sinopsis En Kotlin, `val` es una palabra clave utilizada para declarar variables inmu...
Meta Keywords: val, que, una, kotlin, variable
-->

# Uso de `val` en Kotlin: Declaración de Variables Inmutables

## Sinopsis
En Kotlin, `val` es una palabra clave utilizada para declarar variables inmutables, es decir, aquellas que no pueden ser reasignadas después de su inicialización. Esto mejora la seguridad del código y ayuda a evitar errores comunes relacionados con la mutabilidad.

## Documentación
La palabra clave `val` se utiliza para declarar variables que no deben cambiar su valor después de ser asignadas. A diferencia de `var`, que permite la reasignación, `val` garantiza que una vez que se le asigne un valor a una variable, no podrá ser modificado. Esto es especialmente útil en programación funcional y en la creación de aplicaciones más seguras y predecibles.

### Propósito
El propósito de `val` es proporcionar una forma de declarar constantes o variables que deben permanecer constantes a lo largo de su ciclo de vida, aumentando así la claridad del código y reduciendo la posibilidad de errores.

### Uso
Para declarar una variable con `val`, se sigue la siguiente sintaxis:

```kotlin
val nombreVariable: Tipo = valor
```

Donde:
- `nombreVariable` es el identificador de la variable.
- `Tipo` es el tipo de dato de la variable (opcional si se puede inferir).
- `valor` es el valor inicial que se le asigna a la variable.

## Ejemplos

### Ejemplo Básico
```kotlin
val nombre: String = "Juan"
println(nombre) // Salida: Juan
```

### Inferencia de Tipos
```kotlin
val edad = 25 // El tipo se infiere como Int
println(edad) // Salida: 25
```

### Uso en Funciones
```kotlin
fun areaCirculo(radio: Double): Double {
    val pi = 3.14
    return pi * radio * radio
}

println(areaCirculo(5.0)) // Salida: 78.5
```

## Explicación
Al utilizar `val`, es importante recordar que, aunque la referencia de la variable es inmutable, el objeto al que apunta puede ser mutable. Por ejemplo, si declaras un `val` que apunta a una lista, puedes modificar la lista, pero no puedes reasignar la variable a otra lista.

### Errores Comunes
- Tratar de reasignar un valor a una variable declarada con `val` resultará en un error de compilación.
  
```kotlin
val numero = 10
// número = 20 // Esto causará un error de compilación
```

- Utilizar `val` en situaciones donde se necesita mutabilidad puede llevar a confusiones, por lo que es esencial evaluar el contexto de uso.

## Resumen en una Línea
`val` es la palabra clave en Kotlin para declarar variables inmutables, garantizando que su valor no pueda ser cambiado una vez asignado.