<!--
Meta Description: # "when" en Kotlin: Estructura de Control de Flujo ## Sinopsis La expresión `when` en Kotlin es una poderosa estructura de control de flujo que permit...
Meta Keywords: when, expresión, println, una, kotlin
-->

# "when" en Kotlin: Estructura de Control de Flujo

## Sinopsis
La expresión `when` en Kotlin es una poderosa estructura de control de flujo que permite evaluar una variable contra múltiples condiciones, proporcionando una forma concisa y legible de manejar múltiples casos.

## Documentación
La expresión `when` se utiliza para reemplazar las instrucciones `switch` de otros lenguajes, ofreciendo una forma más flexible de realizar múltiples comparaciones. Puede funcionar tanto como una expresión que devuelve un valor como una declaración que ejecuta un bloque de código basado en la coincidencia.

### Propósito
El propósito principal de `when` es simplificar la lógica de control de flujo, permitiendo realizar múltiples comprobaciones en una variable de manera clara y eficiente.

### Uso
La sintaxis básica de `when` es la siguiente:

```kotlin
when (expresión) {
    valor1 -> { // Código a ejecutar si expresión == valor1 }
    valor2 -> { // Código a ejecutar si expresión == valor2 }
    else -> { // Código a ejecutar si no coincide con ningún valor }
}
```

También se puede utilizar sin una expresión:

```kotlin
when {
    condición1 -> { // Código a ejecutar si condición1 es verdadera }
    condición2 -> { // Código a ejecutar si condición2 es verdadera }
    else -> { // Código a ejecutar si ninguna condición anterior es verdadera }
}
```

## Ejemplos

### Ejemplo 1: Uso básico de `when`
```kotlin
val numero = 3
when (numero) {
    1 -> println("Uno")
    2 -> println("Dos")
    3 -> println("Tres")
    else -> println("Número desconocido")
}
```

### Ejemplo 2: Uso sin expresión
```kotlin
val mes = 5
when {
    mes == 12 || mes == 1 || mes == 2 -> println("Invierno")
    mes in 3..5 -> println("Primavera")
    mes in 6..8 -> println("Verano")
    mes in 9..11 -> println("Otoño")
    else -> println("Mes inválido")
}
```

### Ejemplo 3: Asignación de valor
```kotlin
val resultado = when (numero) {
    1 -> "Uno"
    2 -> "Dos"
    3 -> "Tres"
    else -> "Número desconocido"
}
println(resultado)
```

## Explicación
Al usar `when`, es importante tener en cuenta que:

- **Tipo de dato**: La expresión puede ser de cualquier tipo de dato, no solo de enteros. Puedes usar cadenas, booleanos, y más.
- **Rango y condiciones**: Puedes combinar condiciones usando rangos (`in`) y expresiones booleanas.
- **Caso `else`**: Es recomendable incluir un caso `else` para manejar situaciones no previstas, evitando así errores en tiempo de ejecución.
- **No se puede usar `when` como expresión de control de flujo anidada**: Asegúrate de que cada bloque sea independiente, ya que anidar `when` puede causar confusión.

## Resumen en una línea
La expresión `when` en Kotlin permite gestionar múltiples condiciones de manera sencilla y legible, reemplazando la tradicional instrucción `switch`.