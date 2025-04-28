<!--
Meta Description: # Uso de "const" en Kotlin: Declaraciones de Constantes ## Sinopsis En Kotlin, la palabra clave `const` se utiliza para declarar constantes en tiempo ...
Meta Keywords: const, constantes, kotlin, que, tipo
-->

# Uso de "const" en Kotlin: Declaraciones de Constantes

## Sinopsis
En Kotlin, la palabra clave `const` se utiliza para declarar constantes en tiempo de compilación, lo que permite que ciertos valores sean inmutables y optimizados para su uso en el código.

## Documentación
La palabra clave `const` se usa para definir propiedades de tipo `String` y valores primitivos que son constantes en tiempo de compilación. Estas constantes son evaluadas y asignadas en el momento de la compilación, lo que hace que sean más eficientes en comparación con las variables normales.

### Propósito
El propósito principal de `const` es mejorar la eficiencia y la legibilidad del código al permitir que los valores constantes sean utilizados de manera segura y optimizada.

### Uso
Para declarar una constante usando `const`, se debe seguir la siguiente sintaxis:

```kotlin
const val NOMBRE_DE_LA_CONSTANTE: TIPO = VALOR
```

Las constantes declaradas con `const` deben ser:

- De tipo primitivo (como `Int`, `Double`, `Boolean`, etc.) o de tipo `String`.
- Inicializadas al momento de la declaración.

## Ejemplos
### Ejemplo 1: Declaración de una constante de tipo `Int`

```kotlin
const val MAX_INTENTOS: Int = 5

fun main() {
    println("El número máximo de intentos es: $MAX_INTENTOS")
}
```

### Ejemplo 2: Declaración de una constante de tipo `String`

```kotlin
const val BIENVENIDA: String = "¡Bienvenido a Kotlin!"

fun main() {
    println(BIENVENIDA)
}
```

### Ejemplo 3: Uso de constantes en una clase

```kotlin
class Configuracion {
    companion object {
        const val URL_API: String = "https://api.ejemplo.com"
    }
}

fun main() {
    println("La URL de la API es: ${Configuracion.URL_API}")
}
```

## Explicación
Al usar `const`, es importante tener en cuenta los siguientes puntos:

- **Limitaciones de tipo**: `const` solo se puede usar con tipos primitivos y `String`. No se puede usar con otros tipos de datos como listas, mapas o cualquier otro objeto.
- **Alcance**: Las constantes declaradas con `const` deben ser `val` y no pueden ser variables `var`. Esto asegura que su valor no cambie durante la ejecución del programa.
- **Uso en objetos compañeros**: `const` es más comúnmente utilizado en objetos compañeros (`companion objects`) para definir constantes que se relacionan con la clase.

## Resumen en una línea
La palabra clave `const` en Kotlin permite la declaración de constantes en tiempo de compilación, optimizando el uso de valores inmutables.