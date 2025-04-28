<!--
Meta Description: # Uso de la declaración "continue" en Kotlin: Comando para el Control de Flujo ## Sinopsis La declaración `continue` en Kotlin se utiliza para omitir ...
Meta Keywords: continue, bucle, que, para, kotlin
-->

# Uso de la declaración "continue" en Kotlin: Comando para el Control de Flujo

## Sinopsis
La declaración `continue` en Kotlin se utiliza para omitir el resto de la iteración actual en un bucle y pasar a la siguiente iteración. Es una herramienta útil para controlar el flujo de ejecución en estructuras de repetición como `for`, `while` y `do-while`.

## Documentación
La declaración `continue` permite a los desarrolladores saltar a la siguiente iteración de un bucle. Se puede utilizar en ciclos repetitivos para evitar la ejecución de código que no es necesario bajo ciertas condiciones. Esto es especialmente útil en situaciones donde se quiere evitar la ejecución de un bloque de código específico sin salir completamente del bucle.

### Uso
La sintaxis básica de `continue` es la siguiente:

```kotlin
continue
```

Cuando se encuentra una declaración `continue`, el control del programa salta inmediatamente a la siguiente iteración del bucle que se esté ejecutando.

### Detalles
- `continue` se puede usar en bucles `for`, `while` y `do-while`.
- En bucles anidados, `continue` afecta solo al bucle más interno en el que se encuentra.
- Es importante asegurarse de que la condición para el `continue` sea clara, para no generar un bucle infinito.

## Ejemplos

### Ejemplo 1: Uso básico de `continue`
```kotlin
for (i in 1..5) {
    if (i == 3) {
        continue // Salta el número 3
    }
    println(i)
}
```
**Salida:**
```
1
2
4
5
```

### Ejemplo 2: Usando `continue` en un bucle `while`
```kotlin
var i = 0
while (i < 5) {
    i++
    if (i == 2) {
        continue // Salta la impresión del número 2
    }
    println(i)
}
```
**Salida:**
```
1
3
4
5
```

## Explicación
Es común que los desarrolladores se encuentren con algunos problemas cuando utilizan `continue`, especialmente en bucles anidados. Un error común es asumir que `continue` afectará a un bucle externo. Recuerda que `continue` solo afecta al bucle en el que se encuentra directamente.

Además, asegúrate de que la condición para la cual estás utilizando `continue` sea clara y esté bien definida. Esto ayudará a evitar situaciones en las que un bucle se repita indefinidamente o se salten elementos de forma inesperada.

## Resumen en una línea
La declaración `continue` en Kotlin permite omitir el resto de la iteración actual en un bucle, facilitando el control del flujo de ejecución.