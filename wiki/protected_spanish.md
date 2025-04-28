<!--
Meta Description: # Uso de "protected" en Kotlin: Acceso Controlado en la Programación Orientada a Objetos ## Sinopsis El modificador de acceso "protected" en Kotlin pe...
Meta Keywords: protected, que, clase, kotlin, acceso
-->

# Uso de "protected" en Kotlin: Acceso Controlado en la Programación Orientada a Objetos

## Sinopsis
El modificador de acceso "protected" en Kotlin permite que las propiedades y métodos de una clase sean accesibles solo dentro de la misma clase y en las clases que heredan de ella, favoreciendo la encapsulación en la programación orientada a objetos.

## Documentación
En Kotlin, "protected" es un modificador de acceso que restringe la visibilidad de miembros (propiedades y métodos) a la clase donde se definen y a sus subclases. Esto es crucial para mantener la integridad de los datos y la lógica de la clase, permitiendo que solo las partes del código que realmente necesitan acceso a esos miembros puedan interactuar con ellos.

### Propósito
- **Encapsulación**: Protege los miembros de una clase de accesos no autorizados desde fuera de la jerarquía de herencia.
- **Herencia**: Facilita la creación de subclases que pueden acceder a los miembros protegidos de su clase base, fomentando la reutilización de código.

### Uso
Para declarar un miembro como "protected", se antepone la palabra clave a la declaración de la propiedad o método. Por ejemplo:

```kotlin
open class Animal {
    protected var nombre: String = "Desconocido"

    protected fun hacerSonido() {
        println("Sonido del animal")
    }
}

class Perro : Animal() {
    fun ladrar() {
        println("El perro se llama $nombre")
        hacerSonido()
    }
}
```

En este ejemplo, tanto la propiedad `nombre` como el método `hacerSonido` son accesibles en la clase `Perro`, pero no pueden ser accedidos desde fuera de la jerarquía de herencia.

## Ejemplos
### Ejemplo 1: Uso básico de "protected"

```kotlin
open class Vehiculo {
    protected var velocidad: Int = 0

    protected fun acelerar(incremento: Int) {
        velocidad += incremento
    }
}

class Coche : Vehiculo() {
    fun mostrarVelocidad() {
        acelerar(20)
        println("La velocidad del coche es: $velocidad km/h")
    }
}

fun main() {
    val coche = Coche()
    coche.mostrarVelocidad() // La velocidad del coche es: 20 km/h
}
```

### Ejemplo 2: Acceso restringido

```kotlin
open class Persona {
    protected var edad: Int = 0

    protected fun establecerEdad(nuevaEdad: Int) {
        edad = nuevaEdad
    }
}

class Estudiante : Persona() {
    fun definirEdad(edadEstudiante: Int) {
        establecerEdad(edadEstudiante)
        println("Edad del estudiante: $edad")
    }
}

fun main() {
    val estudiante = Estudiante()
    estudiante.definirEdad(21) // Edad del estudiante: 21
}
```

## Explicación
### Problemas Comunes
- **Acceso desde fuera de la jerarquía**: Intentar acceder a miembros "protected" desde una instancia de la clase base fuera de la jerarquía de clases resultará en un error de compilación. Esto es intencional y forma parte del diseño de encapsulación.
- **Herencia**: Las subclases pueden acceder a miembros "protected", pero si se intenta acceder a ellos desde un contexto que no sea la clase o sus subclases, se producirá un error.

### Notas Adicionales
- A diferencia de "private", que limita el acceso a la clase misma, "protected" permite que las subclases accedan a los miembros, lo que puede ser útil para extender la funcionalidad de las clases base.
- Kotlin no permite que los miembros "protected" sean visibles desde otras clases que no sean parte de la jerarquía de herencia.

## Resumen en una Línea
El modificador de acceso "protected" en Kotlin permite a las clases y sus subclases acceder a propiedades y métodos restringidos, promoviendo la encapsulación y la herencia en la programación orientada a objetos.