<!--
Meta Description: # Uso de la Palabra Clave "break" en Kotlin: Guía Completa ## Sinopsis La palabra clave `break` en Kotlin se utiliza para salir de bucles o estructura...
Meta Keywords: break, bucle, kotlin, bucles, que
-->

# Uso de la Palabra Clave "break" en Kotlin: Guía Completa

## Sinopsis
La palabra clave `break` en Kotlin se utiliza para salir de bucles o estructuras de control de flujo, como `for`, `while` y `do-while`, antes de que finalicen su ejecución natural. Esta característica permite un control más preciso sobre la lógica de iteración.

## Documentación
La instrucción `break` tiene como propósito principal interrumpir un bucle en ejecución. Cuando se encuentra un `break`, el flujo de control sale inmediatamente del bucle en el que se encuentra, saltando cualquier código que siga después de la instrucción `break` dentro de ese mismo bucle.

### Uso
Para usar `break`, simplemente colócalo dentro del bloque de código del bucle que deseas interrumpir. 

**Sintaxis:**
```kotlin
break
```

### Detalles
- `break` se puede utilizar en bucles `for`, `while` y `do-while`.
- Si se utiliza dentro de bucles anidados, `break` solo interrumpe el bucle más interno.
- No se puede usar `break` fuera de un contexto de bucle, ya que esto generaría un error de compilación.

## Ejemplos
### Ejemplo Básico 1: Uso de break en un bucle for
```kotlin
for (i in 1..10) {
    if (i == 5) {
        break  // Sale del bucle cuando i es 5
    }
    println(i)
}
```
**Salida:**
```
1
2
3
4
```

### Ejemplo Básico 2: Uso de break en un bucle while
```kotlin
var i = 1
while (i <= 10) {
    if (i == 7) {
        break  // Sale del bucle cuando i es 7
    }
    println(i)
    i++
}
```
**Salida:**
```
1
2
3
4
5
6
```

### Ejemplo Básico 3: Uso de break en bucles anidados
```kotlin
outer@ for (i in 1..5) {
    for (j in 1..5) {
        if (i == 3 && j == 3) {
            break@outer  // Sale del bucle externo
        }
        println("i: $i, j: $j")
    }
}
```
**Salida:**
```
i: 1, j: 1
i: 1, j: 2
i: 1, j: 3
i: 1, j: 4
i: 1, j: 5
i: 2, j: 1
i: 2, j: 2
i: 2, j: 3
i: 2, j: 4
i: 2, j: 5
i: 3, j: 1
i: 3, j: 2
```

## Explicación
Un error común al usar `break` es intentar utilizarlo fuera de un contexto de bucle, lo que provocará un error de compilación. Además, es importante recordar que `break` solo afecta el bucle más interno en caso de bucles anidados. Para salir de bucles externos, se debe usar la etiqueta correspondiente, como se mostró en el último ejemplo.

## Resumen en una línea
La palabra clave `break` en Kotlin permite salir de bucles de forma anticipada, proporcionando un control eficiente sobre la ejecución del código.