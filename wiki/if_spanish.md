<!--
Meta Description: # Uso de la sentencia "if" en Kotlin: Guía Completa ## Sinopsis La sentencia "if" en Kotlin es una estructura de control que permite ejecutar bloques ...
Meta Keywords: kotlin, una, else, código, ejecutar
-->

# Uso de la sentencia "if" en Kotlin: Guía Completa

## Sinopsis
La sentencia "if" en Kotlin es una estructura de control que permite ejecutar bloques de código condicionalmente, dependiendo del resultado de una expresión booleana. Es una herramienta fundamental que permite a los desarrolladores tomar decisiones en el flujo de ejecución de sus programas.

## Documentación
La sentencia "if" es una de las estructuras de control más utilizadas en Kotlin. Su propósito es evaluar una condición y, en función del resultado (verdadero o falso), ejecutar un bloque de código específico. La sintaxis básica es la siguiente:

```kotlin
if (condición) {
    // Código a ejecutar si la condición es verdadera
} else {
    // Código a ejecutar si la condición es falsa
}
```

### Uso
Además del uso básico, Kotlin permite combinar múltiples condiciones utilizando `else if`. La sintaxis se vería así:

```kotlin
if (condición1) {
    // Código a ejecutar si condición1 es verdadera
} else if (condición2) {
    // Código a ejecutar si condición2 es verdadera
} else {
    // Código a ejecutar si ninguna de las condiciones anteriores es verdadera
}
```

Kotlin también permite usar "if" como una expresión, lo que significa que puede devolver un valor. Esto se puede utilizar para asignar un valor a una variable dependiendo del resultado de una condición:

```kotlin
val resultado = if (condición) {
    valorSiVerdadero
} else {
    valorSiFalso
}
```

## Ejemplos
### Ejemplo 1: Uso básico de "if"
```kotlin
val numero = 10
if (numero > 0) {
    println("El número es positivo")
} else {
    println("El número es negativo o cero")
}
```

### Ejemplo 2: Uso de "if" como expresión
```kotlin
val numero = 5
val tipo = if (numero % 2 == 0) {
    "Par"
} else {
    "Impar"
}
println("El número es $tipo")
```

### Ejemplo 3: Uso de "else if"
```kotlin
val nota = 85
if (nota >= 90) {
    println("Excelente")
} else if (nota >= 75) {
    println("Bueno")
} else {
    println("Necesita mejorar")
}
```

## Explicación
Un error común al usar "if" en Kotlin es olvidar las llaves `{}` cuando se tiene un solo bloque de código. Aunque Kotlin permite omitir las llaves en este caso, es recomendable usarlas para mejorar la legibilidad y evitar errores en el futuro.

Otro punto a tener en cuenta es que, al usar "if" como expresión, es necesario asegurarse de que ambas ramas (verdadera y falsa) devuelvan valores del mismo tipo. De no ser así, el compilador generará un error.

## Resumen en una línea
La sentencia "if" en Kotlin permite tomar decisiones en el flujo del programa evaluando condiciones booleanas, pudiendo ser utilizada tanto como una declaración como una expresión.