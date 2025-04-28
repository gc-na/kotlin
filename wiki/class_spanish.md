<!--
Meta Description: # Clases en Kotlin: Guía Completa sobre el Uso y Funcionalidades ## Sinopsis Las clases en Kotlin son plantillas que definen la estructura de objetos,...
Meta Keywords: kotlin, que, clase, clases, propiedades
-->

# Clases en Kotlin: Guía Completa sobre el Uso y Funcionalidades

## Sinopsis
Las clases en Kotlin son plantillas que definen la estructura de objetos, permitiendo encapsular propiedades y métodos. Esta característica fundamental facilita la programación orientada a objetos, haciendo que el desarrollo sea más organizado y modular.

## Documentación
En Kotlin, una clase es una construcción que permite crear instancias de objetos, encapsulando su estado y comportamiento. Las clases pueden contener propiedades (atributos) y métodos (funciones) que operan sobre esas propiedades. 

### Propósito
Las clases se utilizan para modelar conceptos del mundo real, permitiendo crear objetos que representen entidades específicas en una aplicación. Esto promueve la reutilización del código y la organización de la lógica del programa.

### Uso
Para definir una clase en Kotlin, se utiliza la palabra clave `class` seguida del nombre de la clase. A continuación, se pueden declarar propiedades y métodos dentro del cuerpo de la clase.

#### Sintaxis Básica
```kotlin
class NombreClase {
    // Propiedades
    var propiedad: Tipo = valorInicial

    // Métodos
    fun metodo() {
        // Lógica aquí
    }
}
```

## Ejemplos
### Ejemplo 1: Clase Simple
```kotlin
class Persona(val nombre: String, var edad: Int) {
    fun saludar() {
        println("Hola, mi nombre es $nombre y tengo $edad años.")
    }
}

fun main() {
    val persona = Persona("Juan", 30)
    persona.saludar() // Salida: Hola, mi nombre es Juan y tengo 30 años.
}
```

### Ejemplo 2: Clase con Propiedad por Defecto
```kotlin
class Coche(val marca: String, var modelo: String = "Desconocido") {
    fun mostrarInfo() {
        println("Coche: $marca, Modelo: $modelo")
    }
}

fun main() {
    val coche = Coche("Toyota")
    coche.mostrarInfo() // Salida: Coche: Toyota, Modelo: Desconocido
}
```

## Explicación
### Errores Comunes
1. **Olvidar el Modificador de Visibilidad**: Por defecto, las propiedades son `public`, pero si se requiere un acceso diferente (como `private` o `protected`), es importante especificarlo.
   
2. **Uso Incorrecto de Instancias**: Al crear instancias de la clase, asegúrate de pasar los parámetros correctos al constructor. De lo contrario, recibirás un error de compilación.

3. **No Usar `val` y `var` Correctamente**: Recuerda que `val` define una propiedad de solo lectura (inmutable), mientras que `var` permite la modificación.

### Notas Adicionales
- Kotlin permite la herencia de clases, lo cual se logra utilizando la palabra clave `open` en la clase base.
- Las clases pueden implementar interfaces y pueden contener constructores primarios y secundarios.

## Resumen en una Línea
Las clases en Kotlin son estructuras que permiten crear objetos con propiedades y métodos, facilitando la programación orientada a objetos y la organización del código.