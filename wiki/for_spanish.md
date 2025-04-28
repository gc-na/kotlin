<!--
Meta Description: # Uso del bucle "for" en Kotlin: Guía Completa ## Sinopsis El bucle `for` en Kotlin es una estructura de control fundamental que permite iterar sobre ...
Meta Keywords: kotlin, bucle, una, iterar, colección
-->

# Uso del bucle "for" en Kotlin: Guía Completa

## Sinopsis
El bucle `for` en Kotlin es una estructura de control fundamental que permite iterar sobre colecciones, arrays y rangos de manera eficiente y sencilla, facilitando la ejecución de un bloque de código múltiples veces.

## Documentación
El bucle `for` en Kotlin se utiliza para iterar sobre elementos de una colección, un array o un rango de valores. Su sintaxis es clara y concisa, lo que lo convierte en una herramienta esencial para desarrollar aplicaciones.

### Propósito
El propósito principal del bucle `for` es permitir la ejecución repetida de un bloque de código para cada elemento de una colección o cada valor dentro de un rango. Esto es especialmente útil para procesar listas de datos, realizar cálculos repetidos o ejecutar acciones en secuencia.

### Uso
La sintaxis básica del bucle `for` en Kotlin es la siguiente:

```kotlin
for (element in collection) {
    // Código a ejecutar por cada elemento
}
```

Donde `element` es el nombre de la variable que representará cada elemento de la colección `collection`.

### Detalles
- **Colecciones**: Puedes usar `for` con cualquier tipo de colección, incluyendo listas, conjuntos y mapas.
- **Arrays**: También se puede utilizar para iterar elementos de un array.
- **Rangos**: Puedes definir rangos utilizando la sintaxis `start..end` o `start until end`.

## Ejemplos

### Iterar sobre una lista
```kotlin
val frutas = listOf("Manzana", "Banana", "Naranja")
for (fruta in frutas) {
    println(fruta)
}
```

### Iterar sobre un array
```kotlin
val numeros = arrayOf(1, 2, 3, 4, 5)
for (numero in numeros) {
    println(numero)
}
```

### Usar rangos
```kotlin
for (i in 1..5) {
    println(i)
}
```

### Iterar con un índice
```kotlin
val colores = listOf("Rojo", "Verde", "Azul")
for (i in colores.indices) {
    println("Índice $i: ${colores[i]}")
}
```

## Explicación
Al utilizar el bucle `for`, es importante tener en cuenta algunos aspectos:

- **Rango Inclusivo/Exclusivo**: Al usar rangos, ten en cuenta que `..` incluye el valor final, mientras que `until` lo excluye.
- **Tipo de colección**: Asegúrate de que la colección no sea nula. Si necesitas iterar sobre una colección que puede ser nula, considera usar el operador seguro `?.`.
- **Mutabilidad**: Si necesitas modificar los elementos de una colección mientras iteras, considera usar un bucle `forEach` o un bucle `while`.

## Resumen en una línea
El bucle `for` en Kotlin permite iterar eficazmente sobre colecciones, arrays y rangos, facilitando la ejecución de código repetitivo.