<!--
Meta Description: # Override en Kotlin: Guía Completa y Ejemplos Prácticos ## Sinopsis El modificador `override` en Kotlin se utiliza para indicar que una función o pro...
Meta Keywords: una, override, open, clase, que
-->

# Override en Kotlin: Guía Completa y Ejemplos Prácticos

## Sinopsis
El modificador `override` en Kotlin se utiliza para indicar que una función o propiedad en una clase hija está sobrescribiendo una función o propiedad de una clase padre. Este mecanismo es fundamental para la programación orientada a objetos, permitiendo la personalización del comportamiento de las clases derivadas.

## Documentación
En Kotlin, el modificador `override` es esencial para implementar el polimorfismo. Al declarar una función o propiedad en una subclase que tiene el mismo nombre y tipo que una en su superclase, se debe utilizar `override` para señalar que se está modificando el comportamiento original.

### Propósito
El propósito de `override` es garantizar que el desarrollador sea explícito sobre la intención de sobrescribir una función o propiedad. Esto ayuda a prevenir errores sutiles que podrían surgir al intentar sobrescribir métodos que no están marcados como `open` en la clase padre.

### Uso
Para utilizar `override`, primero asegúrate de que la función o propiedad en la clase padre esté marcada como `open`. Luego, en la clase hija, utiliza la palabra clave `override` antes de la declaración del método o propiedad.

#### Sintaxis básica:
```kotlin
open class ClasePadre {
    open fun mostrarMensaje() {
        println("Mensaje desde ClasePadre")
    }
}

class ClaseHija : ClasePadre() {
    override fun mostrarMensaje() {
        println("Mensaje desde ClaseHija")
    }
}
```

## Ejemplos
### Ejemplo 1: Sobrescribiendo un Método
```kotlin
open class Animal {
    open fun hacerSonido() {
        println("Sonido de animal")
    }
}

class Perro : Animal() {
    override fun hacerSonido() {
        println("Guau")
    }
}

fun main() {
    val miPerro = Perro()
    miPerro.hacerSonido() // Imprime: Guau
}
```

### Ejemplo 2: Sobrescribiendo una Propiedad
```kotlin
open class Persona {
    open val nombre: String = "Desconocido"
}

class Estudiante : Persona() {
    override val nombre: String = "Juan"
}

fun main() {
    val estudiante = Estudiante()
    println(estudiante.nombre) // Imprime: Juan
}
```

## Explicación
Algunos puntos importantes a considerar al usar `override` en Kotlin:

- **Función `open`**: Si no declaras un método o propiedad como `open` en la clase padre, no podrás sobrescribirlo en la clase hija. Esto ayuda a evitar cambios no deseados en la jerarquía de clases.
  
- **Errores comunes**: Un error común es olvidar marcar la función o propiedad en la clase padre como `open`, lo que resultará en un error de compilación.

- **Sobrescritura de múltiples funciones**: En Kotlin, puedes sobrescribir múltiples funciones en una clase hija, siempre que estén marcadas como `open` en la clase padre.

## Resumen en una línea
El modificador `override` en Kotlin es utilizado para sobrescribir funciones y propiedades de una clase padre en una subclase, permitiendo la personalización del comportamiento.