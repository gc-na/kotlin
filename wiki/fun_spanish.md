<!--
Meta Description: # Uso de la palabra clave "fun" en Kotlin: Definición y Ejemplos ## Sinopsis La palabra clave `fun` en Kotlin se utiliza para definir funciones, que s...
Meta Keywords: kotlin, que, fun, funciones, función
-->

# Uso de la palabra clave "fun" en Kotlin: Definición y Ejemplos

## Sinopsis
La palabra clave `fun` en Kotlin se utiliza para definir funciones, que son bloques de código reutilizables que realizan una acción específica y pueden recibir parámetros y devolver valores.

## Documentación
La palabra clave `fun` es fundamental en Kotlin, ya que permite a los desarrolladores crear funciones, que son esenciales para la programación estructurada y orientada a objetos. Las funciones en Kotlin pueden ser definidas dentro de clases o de manera independiente. Cada función puede tener parámetros de entrada y un tipo de retorno.

### Propósito
El propósito de `fun` es facilitar la creación de funciones que encapsulan lógica, mejorando la legibilidad y la mantenibilidad del código.

### Uso
La sintaxis básica para definir una función en Kotlin es la siguiente:

```kotlin
fun nombreDeLaFuncion(parametro1: Tipo, parametro2: Tipo): TipoDeRetorno {
    // Cuerpo de la función
}
```

- `nombreDeLaFuncion`: Es el nombre que se le asigna a la función.
- `parametro1`, `parametro2`: Son los parámetros que la función recibe.
- `Tipo`: Es el tipo de dato del parámetro.
- `TipoDeRetorno`: Es el tipo de dato que devuelve la función.

## Ejemplos
### Ejemplo 1: Función sin parámetros
```kotlin
fun saludar() {
    println("¡Hola, mundo!")
}

saludar() // Salida: ¡Hola, mundo!
```

### Ejemplo 2: Función con parámetros
```kotlin
fun sumar(a: Int, b: Int): Int {
    return a + b
}

val resultado = sumar(5, 3) // resultado será 8
```

### Ejemplo 3: Función con un valor de retorno nulo
```kotlin
fun imprimirMensaje(mensaje: String?): Unit {
    if (mensaje != null) {
        println(mensaje)
    }
}

imprimirMensaje("¡Bienvenido a Kotlin!") // Salida: ¡Bienvenido a Kotlin!
```

## Explicación
Al usar `fun`, es importante recordar que:

- Las funciones pueden ser declaradas como `inline`, `tail-recursive`, y pueden tener parámetros con valores predeterminados.
- Las funciones en Kotlin pueden ser de primer nivel y no requieren ser declaradas dentro de una clase.
- Es común olvidar especificar el tipo de retorno al definir funciones, lo que puede llevar a errores de compilación.

Además, Kotlin permite la creación de funciones de extensión, lo que permite agregar nuevas funcionalidades a clases existentes sin modificarlas directamente.

## Resumen en una línea
La palabra clave `fun` en Kotlin se utiliza para definir funciones, que son bloques de código reutilizables que pueden recibir parámetros y devolver valores.