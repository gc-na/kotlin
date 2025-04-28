<!--
Meta Description: # Interfaces en Kotlin: Guía Completa ## Sinopsis Las interfaces en Kotlin son un componente fundamental de la programación orientada a objetos, que p...
Meta Keywords: que, las, interfaz, interfaces, kotlin
-->

# Interfaces en Kotlin: Guía Completa

## Sinopsis
Las interfaces en Kotlin son un componente fundamental de la programación orientada a objetos, que permiten definir contratos que las clases pueden implementar, facilitando así la reutilización de código y la creación de aplicaciones más flexibles y mantenibles.

## Documentación
En Kotlin, una interfaz es un tipo de declaración que puede contener métodos abstractos y propiedades. Las clases que implementan una interfaz deben proporcionar implementaciones para los métodos abstractos definidos en la interfaz. A diferencia de otros lenguajes, en Kotlin, las interfaces pueden contener implementaciones de métodos, lo que permite una mayor flexibilidad.

### Propósito
El propósito principal de las interfaces es definir un conjunto de métodos y propiedades que pueden ser implementados por cualquier clase. Esto permite a los desarrolladores garantizar que ciertas funcionalidades estén disponibles en las clases que implementan la interfaz.

### Uso
Para definir una interfaz en Kotlin, se utiliza la palabra clave `interface`, seguida del nombre de la interfaz. Las clases que implementan la interfaz utilizan la palabra clave `:`, seguida del nombre de la interfaz.

```kotlin
interface Vehiculo {
    val tipo: String
    fun acelerar()
    fun frenar() {
        println("Frenando el vehículo")
    }
}

class Coche : Vehiculo {
    override val tipo: String = "Coche"
    
    override fun acelerar() {
        println("Acelerando el coche")
    }
}
```

## Ejemplos

### Ejemplo Básico de Interfaz
```kotlin
interface Animal {
    fun hacerSonido()
}

class Perro : Animal {
    override fun hacerSonido() {
        println("Guau")
    }
}

class Gato : Animal {
    override fun hacerSonido() {
        println("Miau")
    }
}

fun main() {
    val miPerro: Animal = Perro()
    val miGato: Animal = Gato()

    miPerro.hacerSonido() // Imprime: Guau
    miGato.hacerSonido() // Imprime: Miau
}
```

### Interfaz con Propiedades
```kotlin
interface Persona {
    val nombre: String
    fun presentarse() {
        println("Hola, soy $nombre")
    }
}

class Estudiante(override val nombre: String) : Persona

fun main() {
    val estudiante = Estudiante("Juan")
    estudiante.presentarse() // Imprime: Hola, soy Juan
}
```

## Explicación
Al trabajar con interfaces en Kotlin, es importante tener en cuenta algunos aspectos:

- **Implementación de métodos**: Las clases que implementan una interfaz deben proporcionar la implementación de todos los métodos abstractos. Si no se proporciona una implementación, la clase se considera abstracta y no se puede instanciar.
  
- **Múltiples interfaces**: Una clase en Kotlin puede implementar múltiples interfaces, lo que permite una mayor flexibilidad en el diseño del software.

- **Propiedades en interfaces**: Las propiedades en interfaces son abstractas por defecto y deben ser implementadas en la clase que las implementa.

- **Métodos con implementación**: Las interfaces pueden contener métodos con implementación, lo que permite que las clases que implementan la interfaz utilicen esos métodos directamente.

## Resumen en una línea
Las interfaces en Kotlin son esenciales para definir contratos que las clases pueden implementar, promoviendo la reutilización de código y la flexibilidad en el diseño de aplicaciones.