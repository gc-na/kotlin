<!--
Meta Description: # Uso del Bucle "while" en Kotlin: Estructura y Ejemplos ## Sinopsis El bucle "while" en Kotlin es una estructura de control que permite ejecutar un b...
Meta Keywords: bucle, que, while, condición, contador
-->

# Uso del Bucle "while" en Kotlin: Estructura y Ejemplos

## Sinopsis
El bucle "while" en Kotlin es una estructura de control que permite ejecutar un bloque de código repetidamente mientras se cumpla una condición específica. Es fundamental para la programación basada en condiciones y es ampliamente utilizado en diversas aplicaciones.

## Documentación
El bucle "while" se utiliza para repetir un bloque de código siempre que una condición sea verdadera. Su estructura básica es la siguiente:

```kotlin
while (condición) {
    // Bloque de código a ejecutar
}
```

### Propósito
El propósito del bucle "while" es permitir que un programa ejecute un conjunto de instrucciones de manera repetitiva sin necesidad de definir un número específico de iteraciones de antemano. Esto es especialmente útil en situaciones donde el número de repeticiones depende de condiciones que pueden cambiar en tiempo de ejecución.

### Uso
- **Condición**: La condición se evalúa antes de cada iteración. Si es verdadera, se ejecuta el bloque de código. Si es falsa, el bucle se detiene.
- **Bloque de código**: Contiene las instrucciones que se ejecutarán mientras la condición sea verdadera.

## Ejemplos

### Ejemplo 1: Contador Simple
```kotlin
var contador = 0
while (contador < 5) {
    println("Contador: $contador")
    contador++
}
```
En este ejemplo, el bucle imprime el valor del contador desde 0 hasta 4.

### Ejemplo 2: Lectura de Datos
```kotlin
var entrada: String?
do {
    println("Ingresa un número (o 'salir' para terminar):")
    entrada = readLine()
    if (entrada != "salir") {
        println("Has ingresado: $entrada")
    }
} while (entrada != "salir")
```
En este caso, el bucle solicita al usuario que ingrese un número y continúa hasta que se ingresa "salir".

## Explicación
Al utilizar el bucle "while", es crucial asegurarse de que la condición eventualmente se vuelva falsa para evitar bucles infinitos. Un bucle infinito puede causar que el programa se congele o consuma recursos excesivos. 

### Errores Comunes
- **Condiciones que nunca cambian**: Asegúrate de actualizar la variable de control dentro del bucle.
- **Bucle infinito**: Verifica que la condición tenga un camino claro hacia la falsedad.

## Resumen en una línea
El bucle "while" en Kotlin permite ejecutar un bloque de código repetidamente mientras una condición especificada sea verdadera.