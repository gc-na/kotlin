<!--
Meta Description: # init en Kotlin: Inicialización de Clases y Objetos ## Sinopsis El modificador `init` en Kotlin es una característica fundamental que permite inicial...
Meta Keywords: init, clase, que, bloque, kotlin
-->

# init en Kotlin: Inicialización de Clases y Objetos

## Sinopsis
El modificador `init` en Kotlin es una característica fundamental que permite inicializar propiedades de una clase y ejecutar código adicional en el momento de la creación de instancias de dicha clase. Este bloque se ejecuta cada vez que se crea un objeto de la clase.

## Documentación
El bloque `init` se utiliza dentro de la declaración de una clase en Kotlin y es especialmente útil para realizar la configuración inicial de las propiedades de la clase. Cuando se define una clase, se pueden tener múltiples bloques `init`, y estos se ejecutan en el orden en que aparecen en el código.

### Propósito
El propósito principal del bloque `init` es permitir la inicialización de variables y la ejecución de lógica adicional que deba tener lugar antes de que la instancia esté completamente creada.

### Uso
Un bloque `init` se define dentro de una clase y puede acceder a las propiedades de la clase. Este bloque se ejecuta automáticamente cada vez que se crea un objeto de la clase.

#### Sintaxis
```kotlin
class NombreDeLaClase(parametro: Tipo) {
    // Propiedades de la clase
    var propiedad: Tipo = valorInicial

    // Bloque init
    init {
        // Código de inicialización
    }
}
```

## Ejemplos
A continuación se presentan ejemplos que ilustran cómo se utiliza el bloque `init` en Kotlin.

### Ejemplo 1: Inicialización simple
```kotlin
class Persona(nombre: String) {
    var nombreCompleto: String

    init {
        nombreCompleto = nombre.toUpperCase()
    }
}

fun main() {
    val persona = Persona("Juan")
    println(persona.nombreCompleto) // Salida: JUAN
}
```

### Ejemplo 2: Múltiples bloques init
```kotlin
class Coche(marca: String, modelo: String) {
    var descripcion: String

    init {
        descripcion = "$marca $modelo"
        println("Coche creado: $descripcion")
    }

    init {
        println("Listo para conducir.")
    }
}

fun main() {
    val coche = Coche("Toyota", "Corolla")
    // Salida:
    // Coche creado: Toyota Corolla
    // Listo para conducir.
}
```

## Explicación
Algunas consideraciones importantes al usar el bloque `init` en Kotlin:

- **Orden de Ejecución**: Si hay múltiples bloques `init`, se ejecutan en el orden en que están definidos en la clase.
- **Acceso a Propiedades**: Puedes acceder y modificar propiedades de la clase dentro del bloque `init`.
- **Lógica Compleja**: Evita la lógica compleja dentro del bloque `init`, ya que puede dificultar la legibilidad del código.

### Errores Comunes
- **Olvidar Inicializar Propiedades**: Si una propiedad no se inicializa correctamente, Kotlin lanzará un error en tiempo de compilación.
- **Uso Incorrecto de Bloques**: No se deben usar bloques `init` para lógica que dependa de datos externos, ya que esto podría comprometer la integridad del objeto creado.

## Resumen en Una Línea
El bloque `init` en Kotlin permite la inicialización de propiedades y la ejecución de lógica adicional en el momento de crear instancias de una clase.